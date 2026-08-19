# Android App 去廣告

這裡放 **LINE 以外**的 Android App 去廣告、靜態 patch、AdGuard / DNS / Local VPN 類阻擋，以及可重現修改流程。LINE 自己放 `LINE-Root-Patches`。

## 這個專案要幹嘛

目標不是收一堆改好的 APK，而是把「哪個 App、哪個版本、怎麼把廣告拿掉、改完有沒有壞功能」留成之後能重做的紀錄。

## 目前進度

**狀態：JMComic3 已有成功靜態 patch；Smart Life 用 AdGuard 已成功去廣告，但全域過濾有 App 相容性副作用。**

### JMComic3

目前已實測：

- 可以直接進首頁，不用先按原本的 X。
- 測過的頁面廣告都沒了。
- 漫畫正常看。
- 小問題：從「個人中心」回首頁時，可能要再選一次線路。

所以「去廣告後能不能正常看漫畫」這一層算**已完成驗證**；但原本到底改了哪些 resource / smali、完整 rebuild recipe 還沒回收，所以可重現 recipe 還沒完整封箱。

### Smart Life

Smart Life 最後實際日用不是靠前面規劃的 KernelSU 規則 module，而是：

> **安裝 AdGuard 後，Smart Life 廣告消失。**

這條目前可以視為已解的實用方案。

但延伸出另一個問題：**AdGuard 全域套用不是完全透明的。** 目前至少已發現 ChatGPT 的外掛／連接功能會因此失效；把 ChatGPT 從 AdGuard 的 App 過濾範圍排除後，功能恢復。

所以後面整理 AdGuard 類方案時，不能只寫「全域打開就好」，要一起留：

- 哪些 App 需要排除。
- 排除後廣告／功能是否正常。
- 問題是 DNS、HTTPS filtering、Local VPN 還是個別規則造成。

## 這裡怎麼留成果

靜態 APK patch：

- 目標 APK 版本 / hash
- 改了哪些 resource / smali
- rebuild 怎麼跑
- 怎麼簽章
- 改完要測哪些功能

AdGuard / DNS / VPN 類：

- 使用模式（Local VPN / Root / DNS 等）
- App exclusion / whitelist
- 會壞掉的功能
- 實際去廣告結果
- App 更新後要不要重新調規則

## 更新後怎麼看

只要 APK、遠端 data package、ad SDK、AdGuard 規則或 App 網路行為有變，就重新驗證。

**沒有廣告 ≠ App 所有功能都正常。** Smart Life 這次反而證明全域網路過濾要一起測其他 App 的副作用。

## 這是 Public repo

不要直接 commit 原始 APK、重簽 APK、私人 signing key、帳號資料或沒去識別的 log。這裡主要留 patch recipe、網路阻擋配置方向和驗證結果，不拿來當 APK 分發站。

說明用繁中；AdGuard、apktool、smali、package、method、resource name、檔名、hash、指令保留原文。

---

> **附註：** 內容由 AI 按指定格式上傳整理，有錯、缺漏或其他問題請直接私訊。

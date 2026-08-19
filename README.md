# Android App 去廣告

這裡放 **LINE 以外**的 Android App 去廣告、靜態 patch、APK 重建和可重現修改流程。LINE 自己放 `LINE-Root-Patches`。

## 這個專案要幹嘛

目標不是收一堆改好的 APK，而是把「哪個 App、哪個版本、怎麼把廣告拿掉、改完有沒有壞功能」留成之後能重做的紀錄。

## 目前進度

**狀態：JMComic3 的功能結果已驗證成功，但可重現 patch recipe 還沒完整找回；其他 App 持續補。**

### JMComic3

目前已實測：

- 可以直接進首頁，不用先按原本的 X。
- 測過的頁面廣告都沒了。
- 漫畫正常看。
- 小問題：從「個人中心」回首頁時，可能要再選一次線路。

所以「去廣告後能不能正常看漫畫」這一層算**已完成驗證**；但原本到底改了哪些 resource / smali、完整 rebuild recipe 還沒回收，所以這個項目還不能算完整封箱。

### Smart Life

以前也做過 `com.tuya.smartlife` 的去廣告研究，包含 KernelSU / 規則式阻擋方向；目前能回收到 App / Activity 環境和研究脈絡，但**完整 module source 和最後效果還沒重新核對**，所以先列歷史實驗，不寫成完成方案。

整個 repo 不是放棄狀態，後面每找回一個可重現 recipe 就補一個。

## 這裡怎麼留成果

不直接拿 patched APK 當成果保存。比較有用的是把**怎麼改出來**留下來：

- 目標 APK 版本 / hash
- 改了哪些 resource / smali
- rebuild 怎麼跑
- 怎麼簽章
- 改完要測哪些功能

## 常用方向

- apktool / resource editing
- smali static patch
- 必要時處理 network / ad SDK 路徑
- APK rebuild / signing
- version / hash gate，避免新版 App 硬套舊 patch

## 更新後怎麼看

只要 APK、遠端 data package 或 ad SDK 有變，就重新驗證。

**能安裝、能開 App，不代表舊 patch 在新版還正常。**

## 這是 Public repo

不要直接 commit 原始 APK、重簽 APK、私人 signing key、帳號資料或沒去識別的 log。這裡主要留 patch recipe 和驗證結果，不拿來當 APK 分發站。

說明用繁中；apktool、smali、package、method、resource name、檔名、hash、指令保留原文。

---

> **附註：** 內容由 AI 按指定格式上傳整理，有錯、缺漏或其他問題請直接私訊。

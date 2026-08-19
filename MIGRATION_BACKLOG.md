# Android 去廣告舊資料回收清單

## JMComic3

- [x] 已記錄實測結果：可直接進首頁、已測廣告消失、漫畫正常、個人中心回首頁可能要重選線路。
- [ ] 找回目標 APK 精確版本。
- [ ] 找回 APK SHA-256。
- [ ] 找回完整 patch recipe。
- [ ] 找回 resource / smali 修改點。
- [ ] 找回 rebuild / signing 工具版本與步驟。
- [ ] 補 patch 前後功能 checklist。
- [ ] 補上游 data package／強制更新後怎麼重新驗證。

## Smart Life

- [x] **Smart Life 去廣告目前已解，實用方案是 AdGuard。**
- [x] 安裝 AdGuard 後 Smart Life 廣告消失。
- [x] 已記錄全域 AdGuard 的相容性副作用：ChatGPT 外掛／連接功能會失效，ChatGPT 需要排除 AdGuard App 過濾。
- [x] `SmartLife/README.md` 已改成目前真實日用狀態。
- [~] `SmartLife-AdBlock.zip` / `smartlife_adblock`：歷史 KernelSU 規則式方案，名稱與設計已回收，完整 source 尚未找到。
- [ ] 找回歷史 6 條規則精確內容；這是備用／研究線，不影響 Smart Life 目前已解結論。
- [ ] 後面若再遇到其他 App 被 AdGuard 影響，補 App exclusion / whitelist 矩陣。
- [ ] 有需要時再拆 DNS / HTTPS filtering / Local VPN 到底是哪一層造成相容性問題。

## 其他 App

- [ ] 以前有做過的靜態 APK patch 逐一回收；找得到完整 recipe 才收成正式方案。

## Public repo 原則

- 不直接上原始 APK 或修改後 proprietary APK。
- 不上私人 signing key。
- log、帳號資料先去識別。
- 最重要的是留下「怎麼重現」跟「怎麼驗證」，不是只留成品。

> **附註：** 內容由 AI 按指定格式上傳整理，有錯、缺漏或其他問題請直接私訊。

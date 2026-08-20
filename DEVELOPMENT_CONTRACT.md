# Development Contract — Android Ad Removal

本 repo 的核心不是「看不到廣告」，而是可重現 patch 與功能完整性。每個 App 都必須能回答：改了什麼、哪個版本、是否破壞功能、更新後是否失效。

## Source of truth

實機功能回歸 > patched/stock SHA 與 patch recipe > source/smali/resource diff > README 摘要 > 推論。

## 靜態 patch 規則

每個 App 至少保存：

- package / version / versionCode；
- stock APK SHA-256；
- patch method、resource/smali 修改點；
- rebuild / signing 工具版本；
- patched artifact SHA / signer（若可公開）；
- 功能 regression matrix；
- 已知副作用；
- App/data package 更新後是否必須重做。

Public repo 不提交 proprietary 原 APK、重簽 APK、私人 signing key、帳號資料。

## Network / AdGuard 規則

DNS / VPN / HTTPS filtering 與靜態 patch 分開記，不得把兩種方案的成功/副作用混在一起。

任何規則更新至少測：登入、WebView、OAuth、第三方連接、同步、裝置控制等與該 App 有關的網路功能。

## 新測試門檻

- 先查 `TEST_LEDGER.md`；同 App、同版本、同 patch/rule 已測過則不重跑。
- 新測試必須有版本/規則/patch 變更或新的 regression 回報。
- 「廣告消失」只能證明 ad surface 被移除，不能直接標記 App 功能完整。

## Offline-first

先做 APK diff、resource/smali callsite、network endpoint/rule diff、Git history。能離線確認的 patch 不先丟給使用者盲測。

## Artifact discipline

confirmed-working recipe 必須與結果一起保存；不能只留「某版 APK 成功」而沒有修改點。若 artifact 因版權不適合提交，至少保存 hash + recipe + verification matrix。

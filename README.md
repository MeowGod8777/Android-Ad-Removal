# Android App 去廣告

LINE 以外的 Android App 去廣告、靜態 patch、AdGuard / DNS / Local VPN 類方案整理。

## 先看這裡

### 這是什麼

這裡不拿「改好的 APK」當唯一成果，而是記：**哪個 App、怎麼去廣告、最後有沒有壞功能、更新後還要不要重做。**

### 進行時間

- **主要實測／整理：2026-08。**
- Smart Life + AdGuard、JMComic3 靜態 patch 都是在這段時間形成比較完整的日用結果。
- GitHub 系統化整理：2026-08 起。

### 目前做到哪

**🟢 有兩條已經能實際用的結果：JMComic3 靜態 patch、Smart Life + AdGuard。**

#### JMComic3

- ✅ 可以直接進首頁，不用先按 X。
- ✅ 已測頁面廣告消失。
- ✅ 漫畫正常看。
- ⚠️ 從「個人中心」回首頁時，可能要再選一次線路。
- 📦 完整 patch recipe / resource / smali 修改點還沒全部回收。

#### Smart Life

- ✅ 安裝 AdGuard 後，Smart Life 廣告消失。
- ✅ 裝置控制目前可正常用。
- ⚠️ **AdGuard 全域過濾不是零副作用。**
- ⚠️ 目前已確認 ChatGPT 外掛／連接功能會受影響，所以 ChatGPT 要排除 AdGuard App 過濾。

### 最重要的結論

**沒有廣告 ≠ App 所有功能都正常。**

靜態 patch 要做功能回歸；AdGuard / VPN / DNS 類方案要一起測登入、WebView、OAuth、外掛、第三方服務等網路功能。

### Public repo 注意

這個 repo 是 Public。

不要放：原始 APK、重簽 APK、私人 signing key、帳號資料、未去識別 log。

---

## 玩機／技術細節

### JMComic3

目前保存方向：

- 目標 APK 版本 / SHA-256。
- resource / smali 修改點。
- apktool / rebuild。
- signing。
- patch 前後功能 checklist。
- App / data package 更新後重新驗證。

目前功能結果已驗證，但完整 recipe 還沒回收，所以不是完整封箱。

### Smart Life

目標：

`com.tuya.smartlife`

當時版本：7.9.3，targetSdk 36。

現在主要方案：**AdGuard**。

歷史上也研究過 KernelSU 規則式 module：

- `SmartLife-AdBlock.zip`
- module ID：`smartlife_adblock`
- 約 6 條規則

但最後日用不靠這條，所以它現在只留 historical；完整 source 找到後再補。

### AdGuard 相容性

後面每次整理要記：

- Local VPN / Root / DNS / HTTPS filtering 模式。
- 哪些 App 要 exclusion / whitelist。
- 哪個功能壞掉。
- 排除後是否恢復。
- App 更新後是否還需要同樣規則。

目前已知：ChatGPT 外掛／連接功能需要排除 AdGuard 過濾。

### 靜態 patch 的固定欄位

每個 App 最好都有：

1. App / package / version。
2. APK hash。
3. 修改點。
4. rebuild / signing 工具版本。
5. 功能回歸。
6. 已知副作用。
7. 更新後是否要重做。

### 快速入口

- `COMPATIBILITY.md`：目前方案相容性表。
- `SmartLife/`：Smart Life + AdGuard / 歷史 module。
- `JMComic3/`：JMComic3 patch 結果與後續 recipe。
- `MIGRATION_BACKLOG.md`：還沒找回的舊資料。

---

> **附註：** 內容由 AI 按指定格式上傳整理，有錯、缺漏或其他問題請直接私訊。

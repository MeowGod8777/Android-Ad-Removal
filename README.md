# Android App 去廣告研究

這個 repository 用來整理 **LINE 以外**的 Android App 去廣告、靜態 patch、APK 重建與可重現修改流程。

## 已知專案：JMComic3

過去實測已驗證：

- App 可以直接進首頁，不再需要先按原本的關閉 X。
- 已測試頁面的廣告消失。
- 漫畫閱讀功能仍可正常使用。
- 已知小回歸：從「個人中心」回首頁時，可能需要重新選一次內容線路。

這裡**不把重新散布的受版權保護 patched APK 當作 source of truth**。正式保存的應該是可重現的 patch recipe，包括：

- 目標 APK 版本與 hash。
- 修改過的 resource / smali。
- rebuild 步驟。
- signing 步驟。
- patch 後的功能驗證。

## 通用工具與方法

- apktool / resource editing。
- smali-level static patch。
- 必要時停用 network / ad SDK 路徑。
- APK rebuild 與簽章流程。
- 版本／hash gate，避免上游 App 更新後仍錯套舊 patch。

## 更新規則

只要上游 APK、遠端 data package 或廣告 SDK 行為改變，就要重新驗證相關 patch。**不能只因為 APK 安裝成功，就直接判定 patch 與新版本相容。**

## 公開 repository 規則

此 repository 目前為 Public。原始 APK、重簽後 APK、私人 signing key、帳號資料、未去識別 log 或其他不適合公開的檔案不得直接 commit。這裡優先保存「怎麼重現修改」與「如何驗證結果」，而不是散布 App binary。

## 分類原則

- LINE 專屬去廣告與功能精簡 → `LINE-Root-Patches`。
- 其他 App 的去廣告與通用 APK patch 方法 → 本 repository。

## 語言規則

README、patch 說明、驗證結果與已知副作用以繁體中文為主；apktool、smali、package、method、resource name、檔名、hash 與指令維持原文。

---

> **附註：** 本專案資料由 AI 透過 GitHub 外掛協助整理；若內容有誤、缺漏或其他問題，請私訊聯絡。

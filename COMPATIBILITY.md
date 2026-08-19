# 去廣告方案相容性表

這份把「廣告有沒有消失」和「App 功能有沒有壞」分開看。

| App / 方案 | 去廣告 | 功能狀態 | 已知問題 |
|---|---|---|---|
| JMComic3 / 靜態 APK patch | ✅ | 🟢 漫畫正常 | 個人中心回首頁可能要重選線路 |
| Smart Life / AdGuard | ✅ | 🟢 裝置控制正常 | 全域 AdGuard 可能影響其他 App |
| ChatGPT / AdGuard 全域過濾 | 不適用 | ⚠️ 外掛／連接功能受影響 | 目前要排除 ChatGPT App 過濾 |
| Smart Life / 歷史 KernelSU 規則 module | 🟡 歷史研究 | 未完整回收 | 6 條規則 source 尚未找到 |

## AdGuard 新增 App 時怎麼測

不要只看廣告：

1. App 能不能啟動。
2. 登入／OAuth。
3. WebView。
4. 圖片／影片／檔案。
5. 第三方連接／外掛。
6. 推播／背景同步。
7. 裝置控制／即時連線。

如果出問題，再測 App exclusion 後是否恢復。

## 靜態 patch 新版本怎麼測

1. 先核對 APK version / hash。
2. 不直接把舊 patch 套新版。
3. rebuild 後測核心功能。
4. 記錄副作用。
5. 遠端 data package / ad SDK 有改也要重測。

## 狀態標記

- ✅ 已驗證。
- 🟢 可日用。
- 🟡 資料不足／按版本驗證。
- ⚠️ 有已知副作用。
- ❌ 不可用。

> **附註：** 內容由 AI 按指定格式上傳整理，有錯、缺漏或其他問題請直接私訊。

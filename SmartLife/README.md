# Smart Life 去廣告

目標 App：Smart Life

- package：`com.tuya.smartlife`
- 當時版本：7.9.3
- targetSdk：36

## 要解什麼

把 Smart Life 首頁／App 內廣告拿掉，但除濕機等正常裝置控制不能壞。

## 最後實際結果

**狀態：已解，現在實用方案是 AdGuard。**

實際安裝 AdGuard 後，Smart Life 廣告已消失，正常裝置控制可繼續用。

前面曾研究過一條 KernelSU / 規則式阻擋路線：

- `SmartLife-AdBlock.zip`
- module ID：`smartlife_adblock`
- 約 6 條規則

但最後日用結果不需要靠這條當主方案，所以它現在只留歷史研究，不再把「完整 module source 沒找到」寫成 Smart Life 去廣告仍未解。

## AdGuard 的副作用

這次也抓到一個比較重要的延伸問題：

**AdGuard 全域過濾會讓某些 App 的網路功能不正常。**

目前已確認 ChatGPT 的外掛／連接功能會受影響。處理方式是：

> 在 AdGuard 的 App 過濾範圍裡排除 ChatGPT，不讓 ChatGPT 走這套過濾。

排除後再用 Smart Life 維持 AdGuard 去廣告。

所以這裡不建議把「全域開 AdGuard」當成零副作用方案。之後每次新增 App 都要注意：

- App 本身能不能正常登入／連線。
- 外掛、第三方服務、OAuth / WebView 流程有沒有壞。
- HTTPS filtering / DNS / Local VPN 哪一層造成問題。
- 哪些 App 要加入 exclusion。

## 歷史 KernelSU 路線

以前研究過不用改 APK、也不要求 LSPosed / Frida 的規則式 module。這條還是值得保存，因為之後如果不想用全域 AdGuard，可能可以重新拿來做 per-App 方案。

但在完整 6 條規則和 source 找回以前，只標 historical，不拿殘缺內容重建成 original。

## 目前進度

- Smart Life 去廣告：**已完成**。
- 日用方式：**AdGuard**。
- 已知副作用：全域過濾可能影響其他 App；ChatGPT 外掛／連接功能目前需要排除 AdGuard。
- KernelSU 6 條規則 module：**歷史研究，待回收 source**。

> **附註：** 內容由 AI 按指定格式上傳整理，有錯、缺漏或其他問題請直接私訊。

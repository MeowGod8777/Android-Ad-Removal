# Smart Life 去廣告研究

目標 App：Smart Life

- package：`com.tuya.smartlife`
- 當時版本：7.9.3
- targetSdk：36

## 當時要解什麼

主要是把 Smart Life 首頁／App 內廣告拿掉，但不要影響除濕機等正常裝置控制。

當時研究過一條 **KernelSU / 規則式阻擋** 路線，概念上是用 module 放規則，不直接改 APK，也不要求 LSPosed / Frida。

曾經規劃過：

- module：`SmartLife-AdBlock.zip`
- module ID：`smartlife_adblock`
- 約 6 條規則

## 現在能確認什麼

舊資料能確認這台 Root / ColorOS 16 環境裡確實有：

`com.tuya.smartlife/com.thingclips.smart.hometab.activity.FamilyHomeActivity`

但目前**還沒找回完整 module source，也沒找回足夠證據確認最後 6 條規則到底有沒有達到完整去廣告效果**。

所以這頁目前只能列成：

**狀態：歷史實驗／待回收，不能當成已完成方案。**

不是因為已證明無解，而是資料不夠，不拿記憶補成可用 module。

## 待補

- `SmartLife-AdBlock.zip` 或原始 module source
- 6 條規則的精確內容
- 套用前後廣告畫面
- 裝置控制是否正常的回歸測試
- App 更新後是否還有效

如果最後只找得到當時配置、找不到完整 source，就會留 historical；若重新做新版，會另外標 `reimplementation`。

> **附註：** 內容由 AI 按指定格式上傳整理，有錯、缺漏或其他問題請直接私訊。

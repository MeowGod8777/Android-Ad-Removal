# JMComic3 去廣告 patch

## 已經測到的結果

- App 可以直接進首頁，不用先按原本的關閉 X。
- 測過的頁面廣告都沒了。
- 漫畫正常閱讀。
- 小回歸：從「個人中心」回首頁時，可能要重新選一次內容線路。

## 現在還缺的

真正的 patch recipe / source 變更還沒完整找回來。

之前產出的 patched APK 可以證明「當時確實改成功」，但不適合拿它本身當公開 source。

之後 recipe 找回來時，至少補：

- 目標 APK 版本和 SHA-256
- 實際改過的 resource / smali
- rebuild 指令、工具版本
- signing 方法
- 改完後的驗證 checklist
- APK / data package 更新後還能不能用

這裡不直接上傳受版權保護的修改後 APK，重點是留下可重現的修改方法。

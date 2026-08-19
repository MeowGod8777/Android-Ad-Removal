# JMComic3 去廣告 patch

## 過去已驗證的行為

- App 可以直接進入首頁，不再需要原本的關閉 X 步驟。
- 已測試頁面的廣告消失。
- 漫畫閱讀功能仍可正常使用。
- 已知小回歸：從「個人中心」回首頁時，可能需要重新選一次內容線路。

## 目前還缺什麼

真正的 patch recipe / source 變更目前還沒有完整回收到這個 repository。之前產出的 patched APK 本身不適合拿來當公開 archive 的 source of truth。

之後找回 recipe 時，至少要記錄：

- 目標 APK 版本與 SHA-256。
- 精確的 resource / smali 修改。
- rebuild 指令與工具版本。
- signing 方法。
- patch 後功能驗證 checklist。
- 上游 data package 或 APK 更新後的相容性結果。

不要直接把受版權保護的修改後 APK binary 上傳到這裡，取代真正可重現的 patch source。

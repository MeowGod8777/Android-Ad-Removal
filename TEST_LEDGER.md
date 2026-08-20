# Test Ledger — Android Ad Removal

| ID | Baseline | 方案 / 唯一變數 | 結果 | 結論 | 狀態 |
|---|---|---|---|---|---|
| JMCOMIC3-PATCH | JMComic3 當時目標 APK | 靜態去廣告 patch | 可直接進首頁、不需按 X；已測頁面廣告消失；漫畫正常 | 去廣告主功能成立 | FROZEN behavioral checkpoint |
| JMCOMIC3-SIDE | 同 patched build | 個人中心 → 首頁 | 可能需要重新選一次線路 | 已知副作用，不得標記「零 regression」 | FROZEN known issue |
| JMCOMIC3-RECIPE | 同上 | patch recipe 保存 | 完整 resource/smali recipe 尚未全部回收 | artifact 行為已知，但重現性未封箱 | OPEN migration |
| SMARTLIFE-ADGUARD | Smart Life 7.9.3 | AdGuard filtering | 廣告消失；裝置控制可用 | network filtering 可日用 | FROZEN for that version/config |
| ADGUARD-GPT | AdGuard 全域過濾 | ChatGPT 未排除 | ChatGPT 外掛/連接功能受影響 | AdGuard 不是零副作用；ChatGPT 需 exclusion | FROZEN compatibility fact |
| SMARTLIFE-KSU | 歷史 `smartlife_adblock` module | KSU 規則式 module | 非目前日用主方案 | 僅 historical，不拿來覆蓋 AdGuard 現況 | RETIRED/HISTORICAL |

新 App 或版本新增時，以 package/version/hash 為新的 ledger key；不能只寫「同一個 App 又測一次」。

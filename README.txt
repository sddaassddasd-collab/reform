《自新 Reform》導演空間控制台 v28 — 道具新增／刪除版

新增功能
- 「＋新增道具」：可新增全新的道具／物件。
- 新增時可設定：
  - 所屬章
  - 名稱
  - 類型
  - 關聯 Action（可複選）
  - 說明
  - 警告／待確認
  - 第一張參考圖片（選填；支援一般 URL 或 Google Drive 分享連結）
- 既有道具編輯器現在也可以修改「關聯 Action」。
- 「刪除此道具」：從目前道具清單移除。
- 「已刪除」：集中查看並恢復被刪除的道具。

刪除的設計
- 不會把原始資料永久抹掉。
- project.json 使用 hiddenProps 保存「隱藏／刪除」狀態。
- 新增的自訂道具放在 customProps。
- 因此原本道具與後來新增的道具都能刪除，也都能從「已刪除」恢復。

圖片與 Google Drive
- 延續 v27：圖片只保存網址，不搬移圖片檔。
- Google Drive 圖片請設為「知道連結的任何人都可查看」。

保存方式
- 新增／刪除／恢復／編輯先保存在瀏覽器本機草稿。
- 按頂端「儲存」後，會和劇本、筆記、360、圖片一起寫入 GitHub 的 project.json。
- 仍保留「匯出 project.json」作為備份。

project.json 新欄位
- customProps：新增的自訂道具。
- hiddenProps：被刪除／隱藏的道具 key。
- propOverrides：原本道具文字／關聯 Action 的修改。
- imageOverrides：原本道具參考圖片的修改。

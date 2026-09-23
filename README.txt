《自新 Reform》導演空間控制台 v26 — GitHub 一鍵儲存版

核心功能
- 劇本、Action 導演筆記、空間筆記、360 位置：先自動暫存在本機。
- 「儲存到 GitHub」：直接呼叫 GitHub Contents API，更新 repo 裡的 project.json 並建立 commit。
- 「匯出 project.json」仍保留作為離線備份／緊急備援。

第一次設定
1. 建立 Fine-grained personal access token。
2. Repository access 只選這個專案 repo。
3. Repository permissions → Contents → Read and write。
4. 在頁面「GitHub 儲存設定」填：
   - Repository owner
   - Repository
   - Branch（通常 main）
   - project.json 路徑（通常 project.json；如果 Pages 放在 docs 資料夾則填 docs/project.json）
   - Token
5. 按「測試連線」。
6. 成功後即可使用頁面頂端「儲存到 GitHub」。

安全設計
- Token 不會寫入 index.html 或 project.json。
- Repository 設定存在 localStorage。
- Token 預設存在 sessionStorage；關閉目前瀏覽器工作階段後需要重新貼上。
- 若勾選「記住 Token 在這台瀏覽器」，才會把 Token 存在 localStorage。
- 不建議在公用電腦勾選記住 Token。

防止覆蓋
- 頁面載入時會記住正式 project.json 的內容。
- 儲存前先從 GitHub API 讀取 repo 最新 project.json。
- 如果 GitHub 上已被其他人更新，會停止儲存，不直接覆蓋。
- GitHub Contents API PUT 仍使用目前 blob SHA；若 GET 後又發生變動，GitHub 會回報衝突，工具也不會強制覆蓋。

GitHub Pages
- 如果網址是 OWNER.github.io/REPO/，工具會嘗試自動推測 owner 與 repo。
- branch 與 project.json 的 repository 路徑仍請第一次確認。
- Commit 完成後，GitHub Pages 的部署／快取可能不是瞬間完成；repo 中 project.json 已經先更新。

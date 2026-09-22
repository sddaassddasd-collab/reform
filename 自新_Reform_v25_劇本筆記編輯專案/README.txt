《自新 Reform》導演空間控制台 v25

檔案
- index.html：介面、Cue 流程、360、劇本與筆記編輯功能
- project.json：正式的劇本／Action／360／筆記專案資料

這一版可直接編輯
1. 每個 Action 的劇本文字
2. 每個 Action 的導演筆記
3. 每個實體空間的空間筆記
4. 每個 Action 的 360 自訂位置（延續 v24）

資料保存方式
- 在頁面中輸入時：自動存在目前瀏覽器的本機草稿。
- 本機草稿不會直接修改 GitHub 上的 project.json。
- 右上角「•••」→「匯出 project.json」：將所有本機草稿（劇本、Action 筆記、空間筆記、360 位置）合併成新的 project.json。
- 再用這個新檔覆蓋 GitHub repo 裡的 project.json，即成為其他人會讀到的正式版本。

劇本資料
- raw：保留原始劇本／Action 資料。
- actionSettings[action].scriptOverride：正式的劇本文字修改。
- 因此可以隨時恢復原稿，不會破壞 raw 裡的原始文字。

筆記資料
- actionSettings[action].directorNote：Action 導演筆記。
- spaceNotes[spaceId]：空間筆記，例如插座、光線、聲場、動線、容量、現場限制。
- 原本畫面上的「空間判讀」與「原稿備注／製作說明」仍然保留為唯讀資料，不會和導演自己的筆記混在一起。

GitHub Pages
- index.html 與 project.json 放在同一資料夾即可。
- GitHub Pages 會自動讀取 project.json。

直接雙擊本機 index.html
- 因為瀏覽器對 file:// 讀取旁邊 JSON 有安全限制，頁面會要求手動選 project.json。

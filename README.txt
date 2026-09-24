《自新 Reform》導演工作台 v31 — 互動房間平面圖版

新增功能
- 中央「平面圖」模式改成可互動房間圖。
- 1F / 2F 可切換。
- 每個房間／可確認區域都是獨立 SVG 區塊。
- Action 切換時，預設對應房間會自動 highlight。
- 「編輯房間」後可直接點另一個房間改 Action 定位。
- 一般點擊：改成單一房間。
- Shift / Command / Ctrl 點擊：可多選房間。
- 「清除定位」可留下樓層但不指定房間。
- 「恢復預設」回到 v31 內建的劇本／空間對位。
- 房間修改存進 actionSettings.roomAssignment，會跟現有「儲存」一起寫回 project.json。
- 查看／修改房間不會改目前模擬節、completed 或 Cue 狀態。

預設 Action 對位
- 2-01、2-02：洗衣工場（洗衣區）
- 3-01、3-02：錄音室
- 3-03、3-04：面會室
- 3-05、3-06：福利社
- 4-01、4-02：醫務室
- 4-03～4-05：圖書室
- 5-02：外役餐廳
- 6-01～6-05、7-00：2F 押房區（區域級，不假定四個房號）
- 7-01～7-03：2F 候選，但預設不指定房間，等導演自行選。

史料／精度處理
- 1F 的空間名稱依國家人權博物館公開資料與既有官方平面圖名稱建立。
- 2F 公開資料可確認北側為行政空間，其餘主要為押房空間；目前沒有足夠依據把劇本四個牢房對到四個精確房號，所以只拆到區域。
- 互動 SVG 是導演工作用空間示意，不宣稱是建築測繪圖。

官方底圖
- 「官方底圖」可切換查看國家人權博物館現有 1F 圖。
- 目前執行環境無法可靠抓取該官方 JPG 二進位檔，因此沒有假裝把它做成本地 JPG。
- assets/official_floorplan_source.txt 保留官方來源。
- assets/renai_1f_interactive.svg / renai_2f_interactive.svg 是本地互動示意參考圖。

資料結構
roomAssignment 儲存在既有 actionSettings 中，例如：
{
  "roomAssignment": {
    "floor": "1f",
    "roomIds": ["1f_recording"],
    "precision": "room"
  }
}
因此不用另外新增資料檔或新的 schema。

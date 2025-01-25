20241229 Disccusion log:
1. 初步程式功能需求:
- 固定間隔20分鐘擷取熱影像+一般照片(手機相機)影像，存於local端
- 檔案命名: 手動輸入之病歷號_timestamp_(flir)or(cam)
- 從熱影像擷取溫度資料(需要兩個測溫點)，及手機影像擷取兩點之RGB data
- 整合前次研究之Random Forrest之python code，生成model analysis之結果
- 目標: 三月底
2. 硬軟體整合:
- "Flirwireless " Sample code 含有之功能: 熱影像串流 / 參數與顯示調整
- Github平台上整合
- 如需要可約時間: 周末/平日晚上/過年前

20250105 Discussion log:
1. 已有自動拍攝功能，但擷取的影像沒辦法做後續分析
- Flir分析軟體: https://ignite.flir.com/
- 一般用Flir App 擷取的影像可用ignite分出熱影像/一般照片, 及選取測溫點
2. 待嘗試設定兩個像素點(或範圍) 並輸出溫度與RGB數值
- 之前的RGB data code 在"算平均RGB.ipynb"裡
3. 數值輸出在excel或csv檔案, 並想辦法載入架在外部伺服器的AI model
4. 或可參考的Code:
- https://github.com/calderonf/thermalDiabetestools?tab=readme-ov-file#thermaldiabetestools
- https://github.com/susanmeerdink/FLIR_thermal_tools
- https://github.com/andy6804tw/FlirOne/tree/master

20250125 Discussion log: 
Plan B:
1.	用原Flir app, 先手動標記flap & control 溫度點
2.	到一個伺服器or html的網頁，上傳熱影像照片檔，手動輸入溫度值+自動判別的影像RGB data -> 給出prediction  (問問看x-ray analyze)
3.	Feed back 給予病歷號 和 default(nil); Normal; 缺血; 瘀血 的label.
4.	標記存入雲端硬碟裡


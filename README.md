# 基於 Detectron2 的肺部氣胸檢測系統 (Pneumothorax Detection)

## 專案簡介
本專案利用深度學習與電腦視覺技術，自動化掃描 X-ray 影像以快速且準確地標記氣胸位置。專案採用 PyTorch 基礎的 Detectron2 框架，透過 Mask R-CNN 進行高精度的實例分割 (Instance Segmentation)。

## 技術
* **深度學習框架**: PyTorch, Detectron2 
* **開發語言**: Python
* **核心模型**: R-50, R-101, X-101 

## 資料集與工程挑戰
*  **資料來源**: 羅東博愛醫院提供的 784 張標記 X-ray 影像。
*  **解決過擬合 (Overfitting)**: 初期訓練因資料量不足產生嚴重過擬合。本專案實作了資料擴增 (Data Augmentation)，透過將影像進行不同角度的旋轉，成功提升模型的泛化能力。

## 實驗結果
 經過 8000 次與 12000 次訓練週期的比較，**R-50 模型**展現出最佳的抗過擬合能力與定位精度：
*  **最佳模型**: R-50 
*  **AP50 指標**: 81.85%
*  **總損失 (Total Loss)**: 0.2092 (8000次訓練)

## 截圖
*  **訓練次數**: 8000 
<img width="1515" height="577" alt="image" src="https://github.com/user-attachments/assets/ecdf9cc3-4282-4f1f-b44d-4e03e0e83ac1" />

*  **訓練次數**: 12000 
<img width="1520" height="577" alt="image" src="https://github.com/user-attachments/assets/7847506b-ff94-4568-9eb7-ccdc9d35d4f4" />

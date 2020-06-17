### 說明
針對某女鞋品牌自2018年6月之2020年4月之實際零售數據，包含會員資料、交易資料與網站瀏覽行為資料等，本組目標為根據會員的交易行為對會員進行分群，探究各客群的會員輪廓及行為差異，並據此對各客群給予行銷建議。
首先以RFM(Recency,Frequency,Monetary)為分群特徵，採用k-means將一年內有交易之會員進行分群，最終分為「高價活躍VIP」、「活躍舊客」、「潛力舊客」、「潛力新客」、「潛在流失會員」五個客群。
為了進一步了解各群的特性，我們針對分群結果來探討各群會員輪廓，並進行卡方檢定以驗證變數與分群是否有顯著的關聯。
此外，針對各群建構行為關聯矩陣(馬可夫鏈)，若兩行為之時間差距少於一小時，則判定兩行為屬於同一使用者旅程，以分析分析每一客群的行為差異。並結合意藍標籤分析顧客喜好，對於不同潛力客群提供行銷建議。
也計算各客群之平均顧客終身價值，來作為行銷預算分配的依據。


### 執行環境
Python3.7 + Jupyter Notebook

### 目錄結構說明
* dataset: 
	- Freq&Monetary.csv: 每位會員之購買頻率(Frequency)與總購買金額(Monetary)，以及加權購買頻率與加權總購買金額。(權重: 每筆資料乘以距2020/1/20日的日期差倒數，給予較近之消費資料較高權重。之所以定為2020/1/20日市未排除疫情可能影響消費行為)
	- LastPurchase_onlyFinish.csv: 每位會員之最近購買日距2020/1/20日的日期差(Recency)。
	- members_behavior_clusterID.zip: 每筆會員行為資料以及該會員所屬客群ID。
* 分群+卡方檢定.ipynb: 採用k-means將一年內有交易之會員進行分群，並將選定之變數(與群集進行卡方檢定。
* memberID_clusterID.csv: 分群結果，每筆會員以及其所屬客群ID。
* P矩陣（馬可夫鏈）.xlsx: 各客群之行為關聯矩陣
* heatmap.py: 將P矩陣（馬可夫鏈）.xlsx 視覺化為熱力圖
* CLV顧客價值.csv: 各客群之顧客價值計算
* Report.pdf




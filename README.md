# 實作「rule-based」的推薦系統
### 一、專案目的：
根據使用者過去的購買行為與商品資訊，打造一個美妝商品推薦系統。
### 二、使用工具：
1. 資料：來自 2014 年 Amazon 發布的資料集
    * 購買記錄_美妝類：2000-01-10 - 2018-10-02 (共 371345 筆)
      * 訓練資料：2000-01-10 - 2018-09-01 (共 370752 筆)
      * 測試資料：2018-09-01 - 2018-09-30 (共 590 筆)
    * 商品資訊_美妝類：共 32892 個商品
2. 程式語言：Python
### 三、推薦方法：
* 規則一：依據使用者過去的購買紀錄，推薦「買過這個商品的人也購買...」之個人化商品清單，並依照 推薦次數 ->銷量->商品評價 排序清單。
* 規則二：依照商品指標分數推薦分數高的商品，指標排序：支持度->銷量->評價。
* 整合方式：依照規則一推薦至多5項商品，然後以規則二推薦滿10項商品。
### 四、推薦結果：
* 評估分數：Recall = 0.0830508
* 註1：對於本測試資料，規則一沒有產生預期效果，可能因為只有3位目標客戶使用到這份個人化清單，其他目標客戶都沒有購買過個人化推薦清單上的「過去購買商品」。
* 註2：測試資料中，只有 0.01% 的使用者也存在訓練資料中，很可能因此讓運用歷史資料產生的個人化推薦清單沒有明顯效果。
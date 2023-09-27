---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: 瞭解如何使用流量估算器，讓您知道您的是否有足夠的流量 [!DNL Adobe Target] [!UICONTROL 多變數測試] 活動才能成功。
title: 所需的流量大小 [!UICONTROL 多變數測試] (MVT)活動？
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 75%

---

# 預估成功所需的流量 [!UICONTROL 多變數測試] 活動

因為多變數測試會比較多個體驗，請務必瞭解若要提供有意義的結果需要多少流量。流量估算程式會使用關於您的頁面和待測試體驗數量的統計資料，以預估讓測試成功所需的流量和測試持續時間。

流量估算程式會預測需要的樣本大小，以確保下列:

* 95% 可信度。此統計數字表示沒有實際提升度時回報誤判的機會為5% （100% — 信賴水準）。
* 80% 統計檢定力. 此統計值表示測試偵測到真正提升度25%或以上的機率為80%。
* 最低 25% 的可靠可偵測的提升度. [!DNL Target] 會計算有 80% 的機會可偵測到 25% 或更高真實提升度所需的流量。

此測試使用 Bonferroni 校正來對多個比較進行更正。此方法已知較為保守，它是利用強制執行相對大的最小可靠可偵測提升度來平衡。

流量估算程式也會提供回饋意見，讓您得知是否有足夠的流量讓您設計的測試成功。

1. 從 [!UICONTROL 視覺化體驗撰寫器]，按一下 **[!UICONTROL 流量]** 圖示。

   流量估算程式隨即開啟。您可以再按一下&#x200B;**[!UICONTROL 「流量」]**&#x200B;圖示來隱藏流量估算程式。

   ![預估正面影像](assets/estimatorempty.png)

1. 提供一般轉換率、預估每日訪客人數和測試持續時間。

   * **[!UICONTROL 內容組合數量]**: 在執行任何排除之後，根據要隨活動建立的體驗數量自動計算。
   * **[!UICONTROL 一般轉換率]**: 轉換率會根據您的估計或來自您分析系統的過去資料而以百分比表示。
   * **[!UICONTROL 預估每日訪客人數]**: 這是根據鎖定目標條件所得到的可能檢視此頁面的訪客數量。這可能根據您的分析資料。
   * **[!UICONTROL 測試持續時間]**: 活動要執行的天數。

   流量估算程式會使用這些統計資料來判斷執行成功測試所需的調整。

   在接近流量估算程式頂端，您輸入的值會經過計算並顯示結果。

   ![估計影像不足](assets/estimatorinsufficient.png)

   當您變更數量時，預估即會變更。例如，如果您正在測試許多體驗，而您的轉換率和曝光率太低，流量估算器會顯示測試必須執行多久才能成功。 或者，如果您的流量很低，流量估算程式可能會建議較低數量的體驗，讓您可以執行測試達需要的天數。

   如果您沒有足夠的流量，您可以執行以下一或兩個動作:

   * 減少選件組合的數量和位置的數量。
   * 增加測試的持續時間。

   調整數量直到流量估算程式指出您有足夠的流量為止，然後據以設計您的測試。

   ![estimatorok影像](assets/estimatorok.png)

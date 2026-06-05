---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: 瞭解如何使用流量估算程式，讓您知道您是否擁有足夠的流量以讓 [!DNL Adobe Target] [!UICONTROL 多變數測試]活動成功。
title: '[!UICONTROL 多變數測試] (MVT)活動需要多少流量？'
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
TQID: https://experienceleague.adobe.com/XHBXV7Jtvp87ve4NTd-016E2dFkHTbPu-8-nY8GE-VM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 19%

---

# 預估成功的[!UICONTROL 多變數測試]活動所需的流量

因為多變數測試會比較多個體驗，請務必瞭解若要提供有意義的結果需要多少流量。 [!UICONTROL 流量估算程式]會使用您頁面的相關統計資料，以及正在測試的體驗數目，來估算流量和測試成功所需的測試持續時間。

[!UICONTROL 流量估算程式]預測確保下列專案所需的樣本大小：

* 95%信賴度。 此統計數字表示沒有實際提升度時回報誤判的機會為5% （100% — 信賴水準）。
* 80%統計檢定力。 此統計值表示測試偵測到真正提升度25%或以上的機率為80%。
* 最低可偵測提升度為25%。 [!DNL Target]會計算80%機率偵測到25%或以上的真正提升所需的流量量。

此測試使用 Bonferroni 校正來對多個比較進行更正。 此方法已知較為保守，它是利用強制執行相對大的最小可靠可偵測提升度來平衡。

[!UICONTROL 流量估算程式]也提供回饋意見，讓您知道您是否擁有足夠的流量，可以順利完成您設計的測試。

1. 在[!UICONTROL 多變數]活動中，從[!UICONTROL 視覺化體驗撰寫器]的[!UICONTROL 體驗]頁面，按一下[!UICONTROL 體驗]頁面左上角的&#x200B;**[!UICONTROL 流量]**&#x200B;圖示（ ![流量估算器圖示](/help/main/assets/icons/Gauge2.svg)）。

   [!UICONTROL 流量估算程式]開啟。

   ![流量估算器使用者介面](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   您可以再按一下圖示來隱藏[!UICONTROL 流量估算程式]。

   在[!UICONTROL 流量估算程式]頂端附近，會計算您輸入的值並顯示結果。

1. （依條件）提供一般轉換率、預估每日訪客人數和測試持續時間。

   * **[!UICONTROL 內容組合數量]**：在任何排除之後，根據要隨活動建立的體驗數量自動計算。
   * **[!UICONTROL 一般轉換率]**：轉換率會根據您的估計或來自您分析系統的過去資料而以百分比表示。
   * **[!UICONTROL 預估每日訪客人數]**：這是根據鎖定目標條件所得到的可能檢視此頁面的訪客數量。 這可能根據您的分析資料。
   * **[!UICONTROL 測試持續時間]**：活動要執行的天數。

   [!UICONTROL 流量估算程式]會使用這些統計資料來決定執行成功測試所需的調整。

   當您變更數量時，預估即會變更。 例如，如果您正在測試許多體驗，而您的轉換率和曝光率太低，[!UICONTROL 流量估算器]會顯示測試必須執行多久才能成功。 或者，如果您的流量很低，[!UICONTROL 流量估算程式]可能會建議較少的體驗數量，讓您能夠執行所需天數的測試。

   如果您沒有足夠的流量，您可以執行以下一或兩個動作:

   * 減少產品建議組合的數量和位置的數量。
   * 增加測試的持續時間。

   調整數字，直到[!UICONTROL 流量估算程式]指出您有足夠的流量，然後相應地設計測試。

---
keywords: traffic estimator;automated personalization;ap
description: 「流量估計器」提供意見回饋，讓您知道您是否有足夠的流量讓Adobe Target活動成功。
title: 預估成功所需的流量
feature: ap
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 25%

---


# ![PREMIUM](/help/assets/premium.png) 預估成功所需的流量{#estimate-the-traffic-required-for-success}

The [!UICONTROL Traffic Estimator] provides feedback that lets you know whether you have sufficient traffic for your [!DNL Adobe Target] activity to succeed.

Because an [!UICONTROL Automated Personalization] activity uses multiple offer combinations, it is important to know how much traffic is required to provide meaningful results. The [!UICONTROL Traffic Estimator] uses statistics about your page and the number of experiences being tested to estimate the amount of traffic and the test duration needed to make the activity successful.

The [!UICONTROL Traffic Estimator] determines if there is enough traffic to generate personalized models, by comparing the estimated page impressions and typical conversion rate for the pages. 理想上，對於成功的活動，正確的樣本大小可確保個人化內容會在活動持續期間的 50% 或 14 天內就緒 (以較少者為準)。這可讓您有充分的時間來取得個人化內容並學習要傳送的內容。

Remember that [!DNL Target] randomly serves experiences until the personalization algorithms are built. The checkmark icon beside each offer shows when the model for that offer is ready and [!DNL Target] is able to begin delivering personalized content. 因為僅能在模型就緒之後預期提升度，視覺說明可讓您設定正確的預期。Use the [!UICONTROL Traffic Estimator] in the [!UICONTROL Visual Experience Composer] (VEC) to get a guideline of when the models will be ready.

## 使用流量估計器

1. From the [!UICONTROL Visual Experience Composer], click **[!UICONTROL Traffic]**.

   ![流量圖示](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   The [!UICONTROL Traffic Estimator] opens. You can click **[!UICONTROL Traffic]** again to hide the [!UICONTROL Traffic Estimator].

   ![](assets/ap_est.png)

1. 提供一般轉換率 (或您從此活動預期的轉換率)、預估每日活動曝光次數和測試持續期間。

   * **選件數**:根據在排除任何項目後作為活動一部分建立的體驗數自動計算。
   * **一般轉換率**: 轉換率會根據您的估計或來自您分析系統的過去資料而以百分比表示.
   * **預計每日瀏覽次數**:這是根據定位條件，能夠檢視活動的訪客每天的瀏覽次數。 這可能根據您的分析資料。請注意，此數量應為造訪次數，而非不重複訪客次數。
   * **測試持續時間**: 活動要執行的天數。

   The [!UICONTROL Traffic Estimato]r uses these statistics to determine what adjustments are needed to run a successful test.

   Near the top of the [!UICONTROL Traffic Estimator], the values you entered are calculated and the results are shown.

   ![](assets/ap_est_no.png)

   當您變更數量時，預估即會變更。For example, if you are testing a large number of combinations and your conversion rate and impressions are too low, the [!UICONTROL Traffic Estimator] shows how long the test will need to run to be successful. Or, if your traffic is low, the [!UICONTROL Traffic Estimator] might suggest a lower number of offer combinations so you can run the test the desired number of days.

   如果您沒有足夠的流量，您可以執行以下一個或所有動作:

   * Consider using an [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md) activity instead of [!UICONTROL Automated Personalization] to create experiences with several offer changes in one experience variation.
   * Reduce the number of offer combinations within your [!UICONTROL Automated Personalization] activity.
   * 增加活動的持續時間。

   Adjust the numbers until the [!UICONTROL Traffic Estimator] says you have sufficient traffic, then design your test accordingly.

   ![](assets/ap_est_yes.png)

   If the traffic is sufficient, the [!UICONTROL Traffic] icon shows a green check. 如果流量不足，圖示會顯示紅色的警告標籤。

## 關於流量估計器的常見問題

使用流量估計器時，請考慮下列常 [!UICONTROL 見問答]:

### 為什麼我 [!DNL Target] 的AP活動流量足夠時，不建立個人化模型？

在特定情況下，您的流量可能足夠大，以建立個人化模型，但該流量可能會通知 [!DNL Target] ，個人化模型與隨機模型之間沒有有意義的差異。 雖然模型已內建並測 [!DNL Target] 試過，但由於模型並未明顯優於隨機模型，因此無法部署。

模型未比隨機選件好的一個可能原因是選件彼此差異不大。 如果是這樣，您可以嘗試讓選件在視覺上更不同（如果訊息類似），或嘗試變更訊息本身。

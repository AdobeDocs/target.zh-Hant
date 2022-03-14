---
keywords: 流量估計器；自動個性化；ap；估計流量；自動目標
description: 使用Adobe [!DNL Target] 流量估計器，用於確定您是否有足夠的流量使您的Automated Personalization活動成功。
title: 成功活動需要多少流量？
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 13%

---

# ![PREMIUM](/help/main/assets/premium.png) 預估成功所需的流量

的 [!DNL Adobe Target] [!UICONTROL 流量估計器] 提供反饋，讓您知道是否有足夠的流量 [!UICONTROL Automated Personalization] 要成功的活動。

因為 [!UICONTROL Automated Personalization] 活動使用多個服務組合，瞭解需要多少流量才能提供有意義的結果非常重要。 的 [!UICONTROL 流量估計器] 使用有關頁面的統計資訊和正在測試的體驗數，以估計使活動成功所需的通信量和test持續時間。

的 [!UICONTROL 流量估計器] 通過比較估計的頁面印象和頁面的典型轉換率，確定是否有足夠的流量來生成個性化模型。 理想上，對於成功的活動，正確的樣本大小可確保個人化內容會在活動持續期間的 50% 或 14 天內就緒 (以較少者為準)。此過程允許有足夠的時間來獲取個性化內容並學習要傳遞的內容。

記住 [!DNL Target] 隨機地提供體驗，直到個性化算法建立。 每個優惠旁邊的複選標籤表徵圖顯示該優惠的模型何時就緒 [!DNL Target] 能夠開始提供個性化內容。 因為僅能在模型就緒之後預期提升度，視覺說明可讓您設定正確的預期。使用 [!UICONTROL 流量估計器] 的 [!UICONTROL 視覺體驗作曲家] (VEC)，獲取模型準備時間的指南。

## 使用流量估計器

1. 從 [!UICONTROL 視覺體驗作曲家]按一下 **[!UICONTROL 流量]**。

   ![流量圖示](/help/main/c-activities/t-automated-personalization/assets/icon-traffic.png)

   的 [!UICONTROL 流量估計器] 的上界。 您可以按一下 **[!UICONTROL 流量]** 來隱藏 [!UICONTROL 流量估計器]。

   ![流量估計器用戶介面](assets/ap_est.png)

1. 指定典型的轉換率（或您預期從此活動中轉換的比率）、每天估計的活動印象和test持續時間。

   | 量度 | 說明 |
   | --- | --- |
   | **[!UICONTROL 優惠數量]** | 此度量根據在排除任何項後作為活動的一部分建立的經驗數自動計算。 |
   | **[!UICONTROL 一般轉換率]** | 此度量根據您的估計或分析系統的過去資料以百分比表示。 |
   | **[!UICONTROL 預估的每日造訪次數]** | 此指標是能夠根據目標標準查看活動的訪問者每天的訪問次數。 此度量可以基於您的分析資料。 這個號碼必須是訪問，而不是唯一訪問者。 |
   | **[!UICONTROL 測試持續時間]** | 您要活動執行的天數。 |

   的 [!UICONTROL 流量估計器] 使用這些度量來確定運行成功test所需的調整。

   靠近 [!UICONTROL 流量估計器]，將計算您輸入的值並顯示結果。

   ![顯示值和結果的流量估計](assets/ap_est_no.png)

   當您變更數量時，預估即會變更。例如，如果您正在測試許多組合，並且轉換率和印象太低，則 [!UICONTROL 流量估計器] 顯示test必須運行多長時間才能成功。 或者，如果你的車流量很低， [!UICONTROL 流量估計器] 可以建議較少的優惠組合數，以便您可以按所需天數運行test。

   如果通信量不足，請考慮以下事項：

   * 考慮使用 [自動目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 活動 [!UICONTROL Automated Personalization] 創造體驗，讓體驗在一次體驗變化中發生幾次變化。
   * 減少您的服務組合數量 [!UICONTROL Automated Personalization] 的子菜單。
   * 增加活動的持續時間。

   調整數字，直到 [!UICONTROL 流量估計器] 指示您有足夠的流量，然後相應地設計test。

   ![顯示足夠通信消息的通信估計器](assets/ap_est_yes.png)

   如果流量足夠， [!UICONTROL 流量] 表徵圖顯示綠色複選框。 如果流量不足，圖示會顯示紅色的警告標籤。

## 有關流量估計器的常見問題

使用時請考慮以下常見問題 [!UICONTROL 流量估計器]:

### 為什麼即使我的AP活動擁有足夠的流量，也無法構建個性化模型？

在某些情況下，您的流量足夠大，可以構建個性化模型，但流量可以通知 [!DNL Target] 個性化模型和隨機模型之間沒有有意義的區別。 雖然模型是內置的 [!DNL Target] 並且測試了，由於模型並不比隨機模型好，所以沒有部署。

模型不如隨機模型的一個可能原因可能是報價之間的差別不夠大。 如果是，您可以嘗試在消息相似的情況下使服務更直觀地不同，也可以嘗試更改消息本身。

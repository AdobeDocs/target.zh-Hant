---
keywords: 流量估算器；automated personalization；ap；估算流量
description: 使用[!UICONTROL 流量估算程式]評估您是否有足夠的流量讓[!UICONTROL Automated Personalization]活動成功。
title: 成功的[!UICONTROL Automated Personalization]活動需要多少流量？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
TQID: https://experienceleague.adobe.com/rLjNgDlAWK-r9Zv7083vo-PdWTPy3aHGS4fXEGeTdnY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 794
ht-degree: 8%

---

# 預估成功所需的流量

[!DNL Adobe Target] [!UICONTROL 流量估算程式]提供的意見回饋可讓您知道您的[!UICONTROL Automated Personalization] (AP)活動是否有足夠的流量可以成功。

由於[!UICONTROL Automated Personalization]活動使用多個選件組合，因此瞭解需要多少流量才能提供有意義的結果非常重要。 [!UICONTROL 流量估算程式]會使用您頁面的相關統計資料，以及正在測試的體驗數目，來估算讓活動成功所需的流量和測試持續時間。

[!UICONTROL 流量估算程式]會比較預估的頁面曝光次數和頁面的一般轉換率，以判斷是否有足夠的流量產生個人化模型。 理想上，對於成功的活動，正確的樣本大小可確保個人化內容會在活動持續期間的 50% 或 14 天內就緒 (以較少者為準)。 此程式可讓您有充足的時間取得個人化內容，並瞭解要傳送哪些內容。

請記住，[!DNL Target]會隨機提供體驗，直到建立個人化演演算法為止。 每個優惠方案旁的勾號圖示會顯示該優惠方案的模型何時準備就緒，[!DNL Target]何時可以開始提供個人化內容。 由於提升度僅在模型準備就緒後才可預期，因此視覺指示可讓您設定正確的預期。 使用[!UICONTROL 視覺化體驗撰寫器] (VEC)中的[!UICONTROL 流量估算器]，取得模型準備就緒時的指引。

## 使用流量估算程式

1. 在[!UICONTROL Automated Personalization]活動中，從[!UICONTROL 視覺化體驗撰寫器]的[!UICONTROL 體驗]頁面，按一下[!UICONTROL 體驗]頁面左上角的&#x200B;**[!UICONTROL 流量]**&#x200B;圖示（ ![流量估算器圖示](/help/main/assets/icons/Gauge2.svg)）。

   [!UICONTROL 流量估算程式]開啟。

   ![流量估算器使用者介面](assets/ap-est.png)

   您可以再按一下圖示來隱藏[!UICONTROL 流量估算程式]。

1. 指定一般轉換率（或您從此活動預期的轉換率）、預估每日活動曝光次數和測試持續時間。

   | 量度 | 說明 |
   | --- | --- |
   | **[!UICONTROL 選件數目]** | 此量度會在任何排除後，根據要隨活動建立的體驗數量自動計算。 |
   | **[!UICONTROL 一般轉換率]** | 此量度會根據您的估計或來自您分析系統的過去資料而以百分比表示。 |
   | **[!UICONTROL 預估每日造訪次數]** | 此量度是根據鎖定目標條件，從能夠檢視活動的訪客得到的每日造訪次數。 此量度可以根據您的分析資料。 此數字必須是造訪次數，而非不重複訪客。 |
   | **[!UICONTROL 測試持續時間]** | 您要活動執行的天數。 |

   [!UICONTROL 流量估算程式]會使用這些量度來決定執行成功測試所需的調整。

   在[!UICONTROL 流量估算程式]頂端附近，會計算您輸入的值並顯示結果。

   ![顯示值與結果的流量預估](assets/ap-est-no.png)

   當您變更數量時，預估即會變更。 例如，如果您要測試許多組合，而您的轉換率和曝光率太低，[!UICONTROL 流量估算程式]會顯示測試必須執行多久才能成功。 或者，如果您的流量低，[!UICONTROL 流量估算程式]可能會建議較少的選件組合數量，以便您執行所需天數的測試。

   如果您沒有足夠的流量，請考慮下列事項：

   * 請考慮使用[[!UICONTROL 自動鎖定目標]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)活動（而非[!UICONTROL Automated Personalization]）來建立體驗，讓一個體驗變數中有數個選件變更。
   * 減少[!UICONTROL Automated Personalization]活動中的選件組合數量。
   * 增加活動的持續時間。

   調整數字，直到[!UICONTROL 流量估算程式]指出您有足夠的流量，然後相應地設計測試。

   ![流量估算器顯示足夠的流量訊息](assets/ap-est-yes.png)

   如果流量足夠，[!UICONTROL 流量]圖示會顯示綠色檢查。 如果流量不足，圖示會顯示紅色的警告標籤。

## 關於流量估算的常見問題

使用[!UICONTROL 流量估算程式]時，請考量下列常見問題：

### 為什麼即使我的AP活動有足夠的流量，仍沒有建立個人化模型？

在特定情況下，您的流量夠大，可以建立個人化模型，但流量可能會通知[!DNL Target]個人化模型與隨機之間沒有有意義的差異。 雖然模型是在[!DNL Target]中建立並測試，但並未部署，因為此模型並不比隨機模型好。

模型沒有優於隨機選件的可能原因可能是選件彼此之間的差異不足。 如果是這樣的話，您可以嘗試在訊息相似時讓選件在視覺上更不同，或者也可以嘗試變更訊息本身。

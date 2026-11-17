---
keywords: 流量估算器；automated personalization；ap；估算流量
description: 使用[!UICONTROL 流量估算程式]評估您是否有足夠的流量讓[!UICONTROL Automated Personalization]活動成功。
title: 成功的[!UICONTROL Automated Personalization]活動需要多少流量？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
TQID: 'https://experienceleague.adobe.com/rLjNgDlAWK-r9Zv7083vo-PdWTPy3aHGS4fXEGeTdnY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: ddd4fa83540294ee229b87f041bc2245ba9a3464
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 8%
---
# 預估成功所需的流量 {#traffic-estimator}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何使用&#x200B;**[!UICONTROL 流量估算程式]**，以檢查您的&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動是否有足夠的流量可以成功。

>[!ENDSHADEBOX]

[!DNL Adobe Target] **[!UICONTROL 流量估算程式]**&#x200B;提供的意見回饋可讓您知道您的&#x200B;**[!UICONTROL Automated Personalization]** (AP)活動是否有足夠的流量可以成功。 AP活動會使用多個選件組合，因此瞭解需要多少流量才能提供有意義的結果是很重要的。 **[!UICONTROL 流量估算程式]**&#x200B;會使用您頁面的相關統計資料，以及正在測試的體驗數目，來估算讓活動成功所需的流量和測試持續時間。

**[!UICONTROL 流量估算程式]**&#x200B;會比較預估的頁面曝光次數和頁面的一般轉換率，以判斷是否有足夠的流量產生個人化模型。 理想上，對於成功的活動，正確的樣本大小可確保個人化內容會在活動持續期間的 50% 或 14 天內就緒 (以較少者為準)。 此程式可讓您有充足的時間取得個人化內容，並瞭解要傳送哪些內容。

[!DNL Target]會隨機提供體驗，直到建立個人化演演算法為止。 每個優惠方案旁的勾號圖示會顯示該優惠方案的模型何時準備就緒，[!DNL Target]何時可以開始提供個人化內容。 只有在模型準備就緒後，才會預期提升度，因此視覺指示可讓您設定正確的預期。 使用&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)中的&#x200B;**[!UICONTROL 流量估算器]**，取得模型準備就緒時的指引。

>[!NOTE]
>
>即使您的流量足夠，個人化模型也不一定都會部署。 [!DNL Target]會建置及測試模型，但只有在模型執行效果優於隨機選取的體驗時，才會部署模型。 如果模式並不比隨機好，選件彼此之間的差異可能並不足夠。 在這種情況下，如果訊息內容類似，請讓選件在視覺上更不同，或是變更訊息本身。

## 使用流量估算程式 {#use-traffic-estimator}

當您建置&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動時，**[!UICONTROL 流量估算程式]**&#x200B;可讓您檢查進入頁面的流量是否足以讓個人化模型及時準備就緒。 在啟動活動之前執行此檢查可協助您避免測試無法觸及足夠訪客以提供個人化內容，並示範如何在流量不足時調整優惠方案組合數量或活動持續時間。

1. 從您的&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動，存取**[!UICONTROL 視覺化體驗撰寫器]的&#x200B;**[!UICONTROL 體驗]**&#x200B;頁面。

1. 按一下&#x200B;**[!UICONTROL 流量]**&#x200B;圖示（![流量估算器圖示](/help/main/assets/icons/Gauge2.svg)）。

   **[!UICONTROL 流量估算程式]**&#x200B;開啟。 若要結束視窗，請再次按一下圖示。

   ![流量估算器使用者介面](assets/ap-est.png)

1. 指定一般轉換率（或您從此活動預期的轉換率）、預估每日活動曝光次數和測試持續時間。

   **[!UICONTROL 流量估算程式]**&#x200B;會使用這些量度來決定執行成功測試所需的調整。

   | 量度 | 說明 |
   | --- | --- |
   | **[!UICONTROL 選件數目]** | 此量度會在任何排除後，根據要隨活動建立的體驗數量自動計算。 |
   | **[!UICONTROL 一般轉換率]** | 此量度會根據您的估計或來自您分析系統的過去資料而以百分比表示。 |
   | **[!UICONTROL 預估每日造訪次數]** | 此量度是根據鎖定目標條件，從能夠檢視活動的訪客得到的每日造訪次數。 此量度可以根據您的分析資料。 此數字必須是造訪次數，而非不重複訪客。 |
   | **[!UICONTROL 測試持續時間]** | 您要活動執行的天數。 |



1. 檢閱結果。 當您變更數量時，預估即會變更。

   例如，如果您要測試許多組合，而您的轉換率和曝光率太低，**[!UICONTROL 流量估算程式]**&#x200B;會顯示測試必須執行多久才能成功。 或者，如果您的流量低，**[!UICONTROL 流量估算程式]**&#x200B;可能會建議較少的選件組合數量，以便您執行所需天數的測試。

   ![顯示值與結果的流量預估](assets/ap-est-no.png)

1. 如果您沒有足夠的流量，請考慮下列選項：

   * 使用[**[!UICONTROL 自動鎖定目標]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md)活動（而非&#x200B;**[!UICONTROL Automated Personalization]**）來建立體驗，讓一個體驗變數中有數個選件變更。
   * 減少&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中的選件組合數量。
   * 增加活動的持續時間。

1. 調整數字，直到&#x200B;**[!UICONTROL 流量估算程式]**&#x200B;指出您有足夠的流量，然後相應地設計測試。

   如果流量足夠，**[!UICONTROL 流量]**&#x200B;圖示會顯示綠色檢查。 如果流量不足，圖示會顯示紅色的警告標籤。

   ![流量估算器顯示足夠的流量訊息](assets/ap-est-yes.png)

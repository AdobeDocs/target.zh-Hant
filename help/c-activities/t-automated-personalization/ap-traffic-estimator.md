---
keywords: 流量估計器；自動個人化；ap；估計流量；自動目標
description: 使用Adobe Target流量估計器來判斷您是否有足夠的流量讓Automated Personalization活動成功。
title: 成功活動需要多少流量？
feature: 自動個人化
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
translation-type: tm+mt
source-git-commit: 6ba670ef69fa23c0023636a1920eed15dcd9dd06
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 13%

---

# ![PREMIUM](/help/assets/premium.png) 預估成功所需的流量

[!DNL Adobe Target] [!UICONTROL 流量估計器]提供反饋，讓您知道是否有足夠的流量使[!UICONTROL Automated Personalization]活動成功。

由於[!UICONTROL Automated Personalization]活動使用多個選件組合，因此務必瞭解提供有意義結果所需的流量。 [!UICONTROL 流量估計器]會使用您頁面的統計資料和所測試的體驗數，來估計流量量以及成功進行活動所需的測試持續時間。

[!UICONTROL 流量估計器]會比較估計的頁面印象和頁面的典型轉換率，判斷是否有足夠的流量產生個人化模型。 理想上，對於成功的活動，正確的樣本大小可確保個人化內容會在活動持續期間的 50% 或 14 天內就緒 (以較少者為準)。此程式可讓您有充足的時間取得個人化內容，並學習要提供哪些內容。

請記住，[!DNL Target]會隨機提供體驗，直到建立個人化演算法為止。 每個選件旁的核取標籤圖示會顯示該選件的模型已就緒，且[!DNL Target]可開始傳送個人化內容。 因為僅能在模型就緒之後預期提升度，視覺說明可讓您設定正確的預期。使用[!UICONTROL 視覺體驗撰寫器](VEC)中的[!UICONTROL 流量估計器]，取得模型就緒時的指引。

## 使用流量估計器

1. 在[!UICONTROL Visual Experience Composer]中，按一下&#x200B;**[!UICONTROL Traffic]**。

   ![流量圖示](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   [!UICONTROL 流量估計器]隨即開啟。 您可以再次按一下「流量&#x200B;****」，隱藏「流量估計器]」。[!UICONTROL 

   ![流量估計器使用者介面](assets/ap_est.png)

1. 指定典型轉換率（或您預期此活動的轉換率）、每日預估活動曝光數，以及測試期間。

   | 量度 | 說明 |
   | --- | --- |
   | **[!UICONTROL 選件數]** | 此量度會根據在排除任何項目後，作為活動一部分建立的體驗數量自動計算。 |
   | **[!UICONTROL 一般轉換率]** | 此度量會根據您的估計或分析系統的過去資料，以百分比表示。 |
   | **[!UICONTROL 預估的每日造訪次數]** | 此量度是根據定位條件，能夠檢視活動的訪客每天的瀏覽次數。 此量度可能以您的分析資料為基礎。 此數字必須是瀏覽，而非獨特訪客。 |
   | **[!UICONTROL 測試持續時間]** | 您要活動執行的天數。 |

   [!UICONTROL 流量估計器]使用這些度量來判斷執行成功測試所需的調整。

   在[!UICONTROL 流量估計器]的頂部附近，將計算您輸入的值並顯示結果。

   ![顯示值和結果的流量估計](assets/ap_est_no.png)

   當您變更數量時，預估即會變更。例如，如果您正在測試許多組合，且轉換率和印象太低，[!UICONTROL 流量估計器]會顯示測試必須執行多久才能成功。 或者，如果您的流量較低，[!UICONTROL 流量估計器]可建議較少的選件組合，以便您執行所需天數的測試。

   如果流量不足，請考慮以下事項：

   * 請考慮使用[Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md)活動，而非[!UICONTROL Automated Personalization]來建立體驗，其中在一個體驗變化中有數個選件變更。
   * 減少[!UICONTROL Automated Personalization]活動中的選件組合數。
   * 增加活動的持續時間。

   調整數字，直到[!UICONTROL 流量估計器]指出您有足夠的流量，然後據以設計您的測試。

   ![顯示足夠流量訊息的流量估計器](assets/ap_est_yes.png)

   如果流量足夠，[!UICONTROL 流量]圖示會顯示綠色勾選。 如果流量不足，圖示會顯示紅色的警告標籤。

## 關於流量估計器的常見問題

使用[!UICONTROL 流量估計器]時，請考慮下列常見問答：

### 為什麼即使我的AP活動具有足夠的流量，個人化模型仍無法建立？

在某些情況下，您的流量足夠大，足以建立個人化模型，但該流量可能會通知[!DNL Target]個人化模型與隨機模型之間沒有有意義的差異。 雖然模型是在[!DNL Target]中內建並經過測試，但並未部署，因為模型並不比隨機模型好。

模型沒有比隨機選擇好的一個可能原因是選件彼此差異不夠大。 如果是，您可以嘗試讓選件在視覺上更不同（如果訊息類似），或嘗試變更訊息本身。

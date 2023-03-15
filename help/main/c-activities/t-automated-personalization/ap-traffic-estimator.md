---
keywords: 流量估算程式；自動個人化；ap；預估流量；自動鎖定目標
description: 使用Adobe [!DNL Target] 流量估算，以判斷您是否有足夠的流量讓Automated Personalization活動成功。
title: 成功的活動需要多少流量？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 13%

---

# 預估成功所需的流量

此 [!DNL Adobe Target] [!UICONTROL 流量估算器] 提供意見回饋，讓您知道您是否有足夠的流量 [!UICONTROL Automated Personalization] 成功的活動。

因為 [!UICONTROL Automated Personalization] 活動使用多個選件組合，請務必了解提供有意義的結果需要多少流量。 此 [!UICONTROL 流量估算器] 使用頁面和所測試體驗數量的相關統計資料，以預估成功進行活動所需的流量和測試持續時間。

此 [!UICONTROL 流量估算器] 比較估計的頁面曝光次數和頁面的一般轉換率，以判斷是否有足夠的流量可產生個人化模型。 理想上，對於成功的活動，正確的樣本大小可確保個人化內容會在活動持續期間的 50% 或 14 天內就緒 (以較少者為準)。此程式可讓您有充足的時間取得個人化內容，並學習要提供哪些內容。

記住 [!DNL Target] 隨機提供體驗，直到建立個人化演算法為止。 每個選件旁的核取標籤圖示會顯示該選件的模型何時就緒，而 [!DNL Target] 能夠開始提供個人化內容。 因為僅能在模型就緒之後預期提升度，視覺說明可讓您設定正確的預期。使用 [!UICONTROL 流量估算器] 在 [!UICONTROL 可視化體驗撰寫器] (VEC)，取得模型準備時間的指引。

## 使用流量估算程式

1. 從 [!UICONTROL 可視化體驗撰寫器]，按一下 **[!UICONTROL 流量]**.

   ![流量圖示](/help/main/c-activities/t-automated-personalization/assets/icon-traffic.png)

   此 [!UICONTROL 流量估算器] 開啟。 您可以按一下 **[!UICONTROL 流量]** 再次隱藏 [!UICONTROL 流量估算器].

   ![流量估算程式使用者介面](assets/ap_est.png)

1. 指定一般轉換率（或您從此活動預期的轉換率）、預估每日活動曝光次數和測試持續時間。

   | 量度 | 說明 |
   | --- | --- |
   | **[!UICONTROL 選件數]** | 在執行任何排除後，系統會根據隨活動建立的體驗數量自動計算此量度。 |
   | **[!UICONTROL 一般轉換率]** | 此量度會根據您的估計或來自您分析系統的過去資料而以百分比表示。 |
   | **[!UICONTROL 預估的每日造訪次數]** | 此量度是根據鎖定目標條件，從可檢視活動的訪客取得的每日造訪次數。 此量度可以根據您的分析資料。 此數字必須為造訪，而非不重複訪客。 |
   | **[!UICONTROL 測試持續時間]** | 您要活動執行的天數。 |

   此 [!UICONTROL 流量估算器] 使用這些量度來判斷執行成功測試所需的調整。

   在 [!UICONTROL 流量估算器]，則會計算您輸入的值並顯示結果。

   ![顯示值和結果的流量估計](assets/ap_est_no.png)

   當您變更數量時，預估即會變更。例如，如果您要測試許多組合，而您的轉換率和曝光次數太低，則 [!UICONTROL 流量估算器] 顯示測試必須執行多久才會成功。 或者，如果您的流量低， [!UICONTROL 流量估算器] 可建議較少的選件組合，以便您能以所需的天數執行測試。

   如果您沒有足夠的流量，請考慮下列事項：

   * 請考慮使用 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 活動而非 [!UICONTROL Automated Personalization] 若要建立體驗，在一個體驗變異中有數個選件變更。
   * 減少您 [!UICONTROL Automated Personalization] 活動。
   * 增加活動的持續時間。

   調整數字，直到 [!UICONTROL 流量估算器] 指出您有足夠的流量，然後據此設計測試。

   ![顯示足夠流量訊息的流量估算器](assets/ap_est_yes.png)

   如果流量足夠，則 [!UICONTROL 流量] 圖示會顯示綠色勾號。 如果流量不足，圖示會顯示紅色的警告標籤。

## 流量估算程式的常見問題

使用時，請考量下列常見問題集 [!UICONTROL 流量估算器]:

### 為什麼即使我的AP活動有足夠的流量，仍未建立個人化模型？

在特定情況下，您的流量會足夠大，足以建立個人化模型，但該流量可能會通知 [!DNL Target] 個人化模型與隨機之間沒有有意義的差異。 雖然模型已內建 [!DNL Target] 並經過測試，因為模型並未比隨機更好，所以沒有部署。

模型未比隨機更好的可能原因，可能是選件彼此的差異不夠。 如果是，如果傳訊類似，您可以嘗試讓選件在視覺上更加不同，或者您可以嘗試變更傳訊本身。

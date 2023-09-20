---
keywords: 流量估算器；automated personalization；ap；估算流量
description: 使用 [!DNL Adobe Target] [!UICONTROL 流量估算器] 以判斷您是否擁有足夠的流量可供 [!UICONTROL Automated Personalization] 活動才能成功。
title: 成功所需的流量 [!UICONTROL Automated Personalization] 活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 10%

---

# 預估成功所需的流量

此 [!DNL Adobe Target] [!UICONTROL 流量估算器] 提供意見反應，讓您知道自己的流量是否足夠 [!UICONTROL Automated Personalization] (AP)活動成功。

因為 [!UICONTROL Automated Personalization] 活動會使用多個選件組合，瞭解需要多少流量才能提供有意義的結果是很重要的。 此 [!UICONTROL 流量估算器] 會使用頁面的相關統計資料，以及正在測試的體驗數量，來預估流量和活動成功所需的測試持續時間。

此 [!UICONTROL 流量估算器] 比較預估的頁面曝光次數和頁面的一般轉換率，判斷是否有足夠的流量產生個人化模型。 理想上，對於成功的活動，正確的樣本大小可確保個人化內容會在活動持續期間的 50% 或 14 天內就緒 (以較少者為準)。此程式可讓您有充足的時間取得個人化內容，並瞭解要傳送哪些內容。

請記住 [!DNL Target] 會隨機提供體驗，直到建立個人化演演算法為止。 每個選件旁的核取標籤圖示會顯示該選件的模型何時準備就緒且 [!DNL Target] 能夠開始提供個人化內容。 由於提升度僅在模型準備就緒後才可預期，因此視覺指示可讓您設定正確的預期。 使用 [!UICONTROL 流量估算器] 在 [!UICONTROL 視覺化體驗撰寫器] (VEC)，以取得模型準備就緒時的指引。

## 使用流量估算程式

1. 從 [!UICONTROL 體驗] 第頁，共 [!UICONTROL 視覺化體驗撰寫器] 在 [!UICONTROL Automated Personalization] 活動，按一下  **[!UICONTROL 流量]** 圖示。

   ![流量圖示](/help/main/c-activities/t-automated-personalization/assets/icon-traffic.png)

   此 [!UICONTROL 流量估算器] 隨即開啟。 您可以按一下 **[!UICONTROL 流量]** 再次以隱藏 [!UICONTROL 流量估算器].

   ![流量估算器使用者介面](assets/ap_est.png)

1. 指定一般轉換率（或您從此活動預期的轉換率）、預估每日活動曝光次數和測試持續時間。

   | 量度 | 說明 |
   | --- | --- |
   | **[!UICONTROL 選件數量]** | 此量度會在任何排除後，根據要隨活動建立的體驗數量自動計算。 |
   | **[!UICONTROL 一般轉換率]** | 此量度會根據您的估計或來自您分析系統的過去資料而以百分比表示。 |
   | **[!UICONTROL 預估的每日造訪次數]** | 此量度是根據鎖定目標條件，從能夠檢視活動的訪客得到的每日造訪次數。 此量度可以根據您的分析資料。 此數字必須是造訪次數，而非不重複訪客。 |
   | **[!UICONTROL 測試持續時間]** | 您要活動執行的天數。 |

   此 [!UICONTROL 流量估算器] 會使用這些量度來決定執行成功測試所需的調整。

   靠近頂端 [!UICONTROL 流量估算器]，則會計算您輸入的值並顯示結果。

   ![顯示值和結果的流量預估](assets/ap_est_no.png)

   當您變更數量時，預估即會變更。例如，如果您要測試許多組合，而您的轉換率和曝光率太低，則 [!UICONTROL 流量估算器] 顯示測試必須執行多久才能成功。 或者，如果您的流量低， [!UICONTROL 流量估算器] 可建議較少數目的選件組合，讓您根據所需的天數執行測試。

   如果您沒有足夠的流量，請考慮下列事項：

   * 考慮使用 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 活動而非 [!UICONTROL Automated Personalization] 以在一個體驗變數中建立具有數個選件變更的體驗。
   * 減少您的產品組合數量 [!UICONTROL Automated Personalization] 活動。
   * 增加活動的持續時間。

   調整數字，直到 [!UICONTROL 流量估算器] 表示您有足夠的流量，然後據此設計測試。

   ![流量估算器顯示足夠的流量訊息](assets/ap_est_yes.png)

   如果流量足夠， [!UICONTROL 流量] 圖示會顯示綠色勾號。 如果流量不足，圖示會顯示紅色的警告標籤。

## 關於流量估算的常見問題

使用時，請考慮下列常見問題 [!UICONTROL 流量估算器]：

### 為什麼即使我的AP活動有足夠的流量，仍沒有建立個人化模型？

在特定情況下，您的流量夠大，可以建立個人化模型，但該流量可能會回報 [!DNL Target] 個人化模型與隨機之間沒有有意義的差異。 雖然模型是內建的 [!DNL Target] 經過測試，並未部署，因為此模型並不比隨機模型更佳。

模型沒有優於隨機選件的可能原因可能是選件彼此之間的差異不足。 如果是這樣的話，您可以嘗試在訊息相似時讓選件在視覺上更不同，或者也可以嘗試變更訊息本身。

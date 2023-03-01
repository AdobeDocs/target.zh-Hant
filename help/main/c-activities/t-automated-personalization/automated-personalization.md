---
keywords: 自動個人化；ap；對象；整體；隨機森林；多臂吃角子老虎機；thompson取樣；ml；機器學習
description: 了解如何在Adobe中使用Automated Personalization(AP)活動 [!DNL Target] 使用進階機器學習來比對每個訪客的不同選件變數。
title: 什麼是Automated Personalization(AP)活動？
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: 3ac61272ee1ccd72a8670966f181e7798cbe9f76
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 89%

---

# ![PREMIUM](/help/main/assets/premium.png) Automated Personalization（美聯社）

[!UICONTROL Automated Personalization] (AP) [!DNL Adobe Target] 結合選件或訊息，並使用進階機器學習來根據訪客的個別客戶設定檔比對每位訪客的不同選件變數，以便個人化內容並促進提升度。

>[!NOTE]
>
>[!DNL Target Premium] 解決方案提供[!UICONTROL 自動個人化]功能。[!DNL Target Standard] 若沒有 [!DNL Target Premium] 授權則不包含此功能。如果您有 [!DNL Target Premium] 授權，[!DNL Target Premium] 卡會取代[!DNL Adobe Experience Cloud] 中的 [!DNL Target Standard] 卡。

與[!UICONTROL 自動鎖定目標]類似，[!UICONTROL 自動個人化]使用隨機森林演算法 (一種主流的資料科學整體方法) 作為主要的個人化演算法，用來決定要向訪客顯示的最佳體驗。[!UICONTROL 自動個人化在測試的探索階段很重要。]鎖定多種訪客時，允許機器學習以決定最有效的內容也相當實用。演算法會隨著時間學習預測最有效的內容，並顯示最可能達成您的目標的內容。

若要尋找有關如何 [!UICONTROL Automated Personalization] 不同於 [!UICONTROL 自動鎖定目標]，請參閱 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

行銷人員在他們的網站上實作一個檔案，這可讓他們指向和點擊任何內容，然後使用 VEC ([!UICONTROL 可視化體驗撰寫器]) 為該區域以可視方式建立並選取其他內容選項。接著，演算法會根據系統所擁有有關訪客的行為資料，自動判斷要為每一個人提供何種內容，藉此提供個人化的體驗。因為[!UICONTROL 自動個人化]可以適應訪客行為中的變更，它可以在不設定結束日期的情況下執行，以持續提供提升度和個人化。這有時稱為「一律開啟」模式。在瞭解從最佳化發現的提升度之前，行銷人員不需要執行測試、分析結果，然後傳送獲勝者 (這是實施標準 A/B 活動成果的標準作業順序)。

討論[!UICONTROL 自動個人化]時，下列字詞相當實用:

| 術語 | 定義 |
|---|---|
| 多臂吃角子老虎機 | 最佳化的多臂吃角子老虎機方法可平衡探索學習和該學習的利用。 |
| 隨機森林 | 隨機森林是先進的機器學習方法。就資料科學而言，這是利用根據訪客和造訪屬性來建構大量決策樹而實現的整體分類或迴歸方法。在 Target 內，隨機森林可用來針對每個特定訪客，決定何種體驗預期轉換的可能性最高 (或每次造訪帶來的收入最高)。如需關於 Target 中隨機森林的資訊，請參閱[隨機森林演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。 |
| Thompson 取樣 | Thompson 取樣的目標是要判斷哪個體驗是整體最佳 (非個人化)，同時將找到該體驗的「成本」降至最低。即便兩個體驗之間沒有統計上的差異，Thompson 取樣仍一律會挑選獲勝者。如需詳細資訊，請參閱 [Thompson 取樣](https://en.wikipedia.org/wiki/Thompson_sampling)。 |

使用[!UICONTROL 自動個人化]時，請考慮下列詳細資料:

**自動個人化使用隨機森林演算法來進行個人化。**

隨機森林是先進的機器學習方法。就資料科學而言，這是利用根據訪客和造訪屬性來建構大量決策樹而實現的整體分類或迴歸方法。在 Target 內，隨機森林可用來針對每個特定訪客，決定何種體驗預期轉換的可能性最高 (或每次造訪帶來的收入最高)。例如，使用 Chrome 的訪客為金級忠誠成員，並且在星期二存取您的網站更可能會使用體驗 A 進行轉換，而來自紐約的訪客更可能使用體驗 B 進行轉換。如需 Target 中隨機森林的相關資訊，請參閱[隨機森林演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。

**個人化模型會為每次造訪最佳化。**

* 演算法會預測訪客轉換的可能性 (或預估來自轉換的收入) 以便提供最佳體驗。
* 在現有工作階段結束時，訪客會符合新體驗的資格 (除非他或她位在控制群組中，在此情況下，訪客第一次造訪時看到的體驗，與他或她將在後續造訪中看到的體驗相同)。
* 在工作階段內，呈現的體驗不會變更以保有視覺一致性。

**個人化模型會適應訪客行為中的變更。**

* 多臂吃角子老虎機可確保模型一律會「耗費」少量的流量，以在活動期間繼續學習，並防止過度利用先前學習的趨勢。
* 每 24 個小時基礎模型會使用最新的訪客行為資料重新建置，以確保 Target 一律會利用變動的訪客偏好設定。
* 如果演算法無法判斷個別訪客的成功體驗，它會自動切換，以顯示整體的最佳執行體驗，同時仍繼續尋找個人化獲勝者。使用 [Thompson 取樣](https://en.wikipedia.org/wiki/Thompson_sampling)找到執行最佳的體驗。

**模型會持續將單一目標量度最佳化。**

* 此量度可根據轉換或收入 (具體而言，[!UICONTROL 每位訪客帶來的收入]) 計算得出。

**Target 會自動收集關於訪客的資訊以建置個人化模型。**

* 如需[!UICONTROL 自動鎖定目標]和[!UICONTROL 自動個人化]中所使用的屬性相關資訊，請參閱[自動個人化資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

**[!DNL Adobe Experience Cloud]Target 會自動使用所有 共用對象，以建立個人化模型。**

* 您不需執行任何特定動作，即可將對象新增至模型。如需將 [!DNL Experience Cloud Audiences] 用於 [!DNL Target] 的相關資訊，請參閱 [Experience Cloud 對象](/help/main/c-integrating-target-with-mac/mmp.md)。

**行銷人員可以上傳離線資料、傾向分數或其他自訂資料來建置個人化模型。**

建置個人化模型時，離線資料 (例如 CRM 資訊或客戶流失傾向分數) 可能具有重大價值。有數種方式可以在[!UICONTROL 自動個人化] (AP) 和[!UICONTROL 自動鎖定目標]個人化演算法中輸入資料。

* [mbox 參數](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}
* [設定檔參數](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}
* [設定檔更新的伺服器端 API](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/)

如需[!UICONTROL 自動個人化]和[!UICONTROL 自動鎖定目標]個人化演算法自動收集和使用之資料的相關資訊，請參閱[自動個人化資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## ![概述徽章](/help/main/assets/overview.png) 訓練影片：活動類型

此影片說明 [!DNL Target Standard/Premium] 中的可用活動類型。[!UICONTROL 自動個人化的討論在 5:55 開始。]

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)

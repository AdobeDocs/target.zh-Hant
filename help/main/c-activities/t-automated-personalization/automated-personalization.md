---
keywords: 自動個人化；ap；對象；整體；隨機森林；多臂吃角子老虎機；Thompson取樣；ml；機器學習
description: 瞭解如何使用 [!UICONTROL Automated Personalization] (AP)中的活動 [!DNL Adobe Target] 會使用進階機器學習來比對每位訪客的不同選件變數。
title: 什麼是 [!UICONTROL Automated Personalization] (AP)活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 40%

---

# [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization] (AP)中的活動 [!DNL Adobe Target] 結合優惠方案或訊息，並使用進階機器學習，根據訪客的個別客戶設定檔來比對每位訪客的不同優惠方案變數，以便個人化內容並促進提升度。

>[!NOTE]
>
>[!DNL Target Premium] 解決方案提供[!UICONTROL 自動個人化]功能。若無 [!DNL Target Standard] 授權，[!DNL Target Premium] 不提供此功能。如需此授權提供之進階功能的詳細資訊，請參閱 [Target Premium](/help/main/c-intro/intro.md#premium)。

類似於 [!UICONTROL 自動鎖定目標]， [!UICONTROL Automated Personalization] 使用 [隨機森林演演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)，此為一領先的資料科學整體方法，可作為其主要個人化演演算法，用來決定要向訪客顯示的最佳體驗。 [!UICONTROL 自動個人化在測試的探索階段很重要。]鎖定多種訪客時，允許機器學習以決定最有效的內容也相當實用。演算法會隨著時間學習預測最有效的內容，並顯示最可能達成您的目標的內容。

若要尋找關於如何操作的詳細資訊 [!UICONTROL Automated Personalization] 不同於 [!UICONTROL 自動鎖定目標]，請參閱 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB).

行銷人員在他們的網站上實作一個檔案，這可讓他們指向和點選任何內容，然後使用為該區域以視覺化方式建立和選取其他內容選項 [!UICONTROL 視覺化體驗撰寫器] (VEC)。 接著，演算法會根據系統所擁有有關訪客的行為資料，自動判斷要為每一個人提供何種內容，藉此提供個人化的體驗。因為[!UICONTROL 自動個人化]可以適應訪客行為中的變更，它可以在不設定結束日期的情況下執行，以持續提供提升度和個人化。此模式有時稱為「隨時待命」。 在瞭解從最佳化發現的提升度之前，行銷人員不需要執行測試、分析結果，然後傳送獲勝者 (這是實施標準 A/B 活動成果的標準作業順序)。

討論[!UICONTROL 自動個人化]時，下列字詞相當實用:

| 術語 | 定義 |
|---|---|
| 多臂吃角子老虎機 | 最佳化的多臂吃角子老虎機方法可平衡探索學習和該學習的利用。 |
| 隨機森林 | 領先的機器學習方法。 在資料科學術語中，這是一種整體分類或回歸方法，會根據訪客和造訪屬性建構許多決策樹。 |
| Thompson 取樣 | Thompson取樣的目標是決定哪些體驗是最佳的整體（非個人化），同時儘量減少尋找該體驗的「成本」。 即便兩個體驗之間沒有統計上的差異，Thompson 取樣仍一律會挑選獲勝者。如需詳細資訊，請參閱 [Thompson 取樣](https://en.wikipedia.org/wiki/Thompson_sampling)。 |

使用[!UICONTROL 自動個人化]時，請考慮下列詳細資料:

## [!UICONTROL Automated Personalization] 使用隨機森林演演算法來進行個人化

隨機森林是領先的機器學習方法。 在資料科學術語中，這是一種整體分類或回歸方法，會根據訪客和造訪屬性建構許多決策樹。 範圍 [!DNL Target]，隨機森林用於決定哪個體驗對於每個特定訪客具有轉換的最高可能性（或每次造訪的最高收入）。 例如，使用Chrome的訪客是金會員忠誠度會員，且週二存取您的網站可能會更容易透過體驗A轉換。來自紐約的訪客可能會更容易透過體驗B轉換。如需有關隨機森林的詳細資訊，請參閱 [!DNL Target]，請參閱 [隨機森林演演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## 個人化模型會針對每次造訪進行最佳化

* 演演算法會預測訪客的轉換可能性（或轉換的估計收入），以提供最佳體驗。
* 訪客有資格在現有工作階段結束後取得新體驗，除非該訪客在控制組中。 如果訪客在控制組中，則訪客在首次造訪時看到的體驗，與後續造訪中看到的體驗相同。
* 呈現的體驗不會在工作階段中變更以維持視覺一致性。

## 個人化模型會因應訪客行為的變化

* 多臂吃角子老虎機可確保模型一律會「花費」一小部分的流量，在整個活動期間繼續學習，並防止過度利用先前學習過的趨勢。
* 基礎模型每24小時會使用最新的訪客行為資料重建一次，以確保 [!DNL Target] 一律使用變更訪客偏好設定。
* 如果演算法無法判斷個別訪客的成功體驗，它會自動切換，以顯示整體的最佳執行體驗，同時仍繼續尋找個人化獲勝者。使用 [Thompson 取樣](https://en.wikipedia.org/wiki/Thompson_sampling)找到執行最佳的體驗。

## 模型會持續將單一目標量度最佳化

* 此量度可根據轉換或收入 (具體而言，[!UICONTROL 每位訪客帶來的收入]) 計算得出。

## [!DNL Target] 自動收集關於訪客的資訊以建置個人化模型

* 如需[!UICONTROL 自動鎖定目標]和[!UICONTROL 自動個人化]中所使用的屬性相關資訊，請參閱[自動個人化資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## [!DNL Target] 自動使用全部 [!DNL Adobe Experience Cloud] 共用受眾以建置個人化模型

* 您不需要執行任何特定動作，將對象新增至模型。 如需將 [!DNL Experience Cloud Audiences] 用於 [!DNL Target] 的相關資訊，請參閱 [Experience Cloud 對象](/help/main/c-integrating-target-with-mac/mmp.md)。

## 行銷人員可以上傳離線資料、傾向分數或其他自訂資料，以建立個人化模型

離線資料（例如CRM資訊或客戶流失傾向分數）在建置個人化模型時可能極具價值。 有數種方式可以在[!UICONTROL 自動個人化] (AP) 和[!UICONTROL 自動鎖定目標]個人化演算法中輸入資料。

* [mbox 參數](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [設定檔參數](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [設定檔更新的伺服器端 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}

如需[!UICONTROL 自動個人化]和[!UICONTROL 自動鎖定目標]個人化演算法自動收集和使用之資料的相關資訊，請參閱[自動個人化資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## 訓練影片: 活動類型

此影片說明 [!DNL Target] 中的可用活動類型。[!UICONTROL 自動個人化的討論在 5:55 開始。]

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)

---
keywords: 自動個人化；ap；對象；整體；隨機森林；多臂吃角子老虎機；Thompson取樣；ml；機器學習
description: 瞭解如何在[!DNL Adobe Target]中使用[!UICONTROL Automated Personalization] (AP)活動，這些活動使用進階機器學習將不同的選件變數對應到每位訪客。
title: 什麼是[!UICONTROL Automated Personalization] (AP)活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
TQID: 'https://experienceleague.adobe.com/BBtKgNRTlqNFFoAjr1LQkhHyZeAlXG2h8D7bsndh4kQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: de439134b0ee5aa795ae255bba852b9b6f10da12
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 15%
---
# 開始使用[!UICONTROL Automated Personalization] {#automated-personalization-overview}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動如何比對每個訪客的優惠方案變數，以及您使用它時應該考量哪些事項。

>[!ENDSHADEBOX]

>[!NOTE]
>
>**[!UICONTROL Automated Personalization]**&#x200B;屬於[!DNL Target Premium]解決方案的一部分。 若無 [!DNL Target Standard] 授權，[!DNL Target Premium] 不提供此功能。 如需此授權提供之進階功能的詳細資訊，請參閱 [Target Premium](/help/main/c-intro/intro.md#premium)。

[!DNL Adobe Target]中的&#x200B;**[!UICONTROL Automated Personalization]** (AP)活動會結合選件或訊息，並使用進階機器學習來根據訪客的個別客戶設定檔比對每位訪客的不同選件變數，以個人化內容並促進提升度。

行銷人員在他們的網站上實作一個檔案，這可讓他們指向和點選任何內容，然後使用&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)為該區域以視覺化方式建立其他內容選項。 接著，演演算法會根據系統所擁有有關訪客的行為資料，自動判斷要為每位訪客提供的內容片段。

**[!UICONTROL Automated Personalization]**&#x200B;會因應訪客行為的變更，以便在未設定結束日期的情況下執行，以持續提供提升度和個人化。 此模式有時稱為「隨時待命」。 在達成提升度之前，行銷人員不需要執行測試、分析結果，然後傳送獲勝者。 **[!UICONTROL Automated Personalization]**&#x200B;在測試的探索階段以及目標鎖定不同的訪客時，也很有價值。 如需關於它與&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;差異之處的詳細資訊，請參閱[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB)。

討論&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;時，下列字詞相當實用：

| 術語 | 定義 |
|---|---|
| 多臂吃角子老虎機 | 最佳化的多臂吃角子老虎機方法可平衡探索學習和該學習的利用。 |
| 隨機森林 | 領先的機器學習方法。 在資料科學術語中，這是一種整體分類或回歸方法，會根據訪客和造訪屬性建構許多決策樹。 |
| Thompson 取樣 | Thompson取樣的目標是決定哪些體驗是最佳的整體（非個人化），同時儘量減少尋找該體驗的「成本」。 Thompson取樣一律會挑選獲勝者，即使兩個體驗之間沒有統計差異。 如需詳細資訊，請參閱 [Thompson 取樣](https://en.wikipedia.org/wiki/Thompson_sampling)。 |

## 個人化模型的運作方式 {#how-ap-works}

**[!UICONTROL Automated Personalization]**&#x200B;使用隨機森林演演算法來進行個人化。 隨機森林是領先的機器學習方法。 在資料科學術語中，這是一種整體分類或回歸方法，會根據訪客和造訪屬性建構許多決策樹。 在[!DNL Target]內，隨機森林用於決定每個特定訪客的預期轉換可能性最高（或每次造訪收入最高）的體驗。

例如，使用Chrome的訪客為金會員忠誠會員，且於週二存取您的網站時，可能較容易透過體驗A轉換。來自紐約的訪客則較容易透過體驗B轉換。

如需[!DNL Target]中隨機森林的詳細資訊，請參閱[隨機森林演演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。

| 外觀 | 運作方式 |
|---|---|
| 每次造訪的&#x200B;**最佳化** | 演演算法會預測訪客轉換的可能性（或轉換的估計收入）以提供最佳體驗。 訪客符合在現有工作階段結束時取得新體驗的資格，除非該訪客在控制組中。 控制組中的訪客看到與第一次造訪相同的體驗。 體驗不會在工作階段中變更，以維持視覺一致性。 |
| **適應訪客行為的變化** | 多臂吃角子老虎機一律會花費一小部分流量，在活動期間繼續學習，並防止過度利用之前學習過的趨勢。 基礎模型會使用最新的訪客行為資料每24小時重建一次。 如果演演算法無法判斷個別訪客的成功體驗，則會顯示使用[Thompson取樣](https://en.wikipedia.org/wiki/Thompson_sampling)找到的整體最佳表現體驗，同時繼續尋找個人化的獲勝者。 |
| **目標量度** | 模型會持續將單一目標量度最佳化，該量度可以是轉換型或收入型（具體而言，每次造訪帶來&#x200B;**[!UICONTROL 收入]**）。 |
| **資料和對象** | [!DNL Target]會自動收集關於訪客的資訊以建置個人化模型。 如需&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;與&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;中所使用屬性的詳細資訊，請參閱[Automated Personalization資料彙集](/help/main/c-activities/t-automated-personalization/ap-data.md)。 [!DNL Target]也會自動使用所有[!DNL Adobe Experience Cloud]個共用對象，因此您不需要執行任何特定動作來將對象新增至模型。 如需詳細資訊，請參閱[Experience Cloud對象](/help/main/c-integrating-target-with-mac/mmp.md)。 |
| **自訂資料** | 行銷人員可以上傳離線資料（例如CRM資訊或客戶流失傾向分數），或其他自訂資料來建立個人化模型。 可以使用[mbox引數](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}、[設定檔引數](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}或設定檔更新[&#128279;](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}的伺服器端API來輸入資料。 |

## 訓練影片: 活動類型 {#training-video}

此影片說明 [!DNL Target] 中的可用活動類型。 從5:55開始討論&#x200B;**[!UICONTROL Automated Personalization]**。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)

---
keywords: 建議；建議活動；條件；演演算法；建議金鑰；自訂金鑰；垂直產業；零售；eccommerce；銷售機會產生；b2b；金融服務；媒體；發佈
description: 瞭解如何在Adobe [!DNL Target] [!DNL Recommendations]中使用條件。
title: 如何在 [!DNL Target] Recommendations中使用條件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 15%

---

# 條件

[!DNL Adobe Target] [!DNL Recommendations]中的條件為規則，可根據預先決定的一組訪客行為決定要建議的產品或內容。 條件能以熱門趨勢、訪客目前和過去的行為，或類似產品和內容為基礎。 您可以新增多個條件，將多個建議類型彼此測試。

以下各節將詳細說明條件索引鍵以及可用於每個索引鍵的建議邏輯。 按一下連結以取得更多詳細資訊。

## 垂直產業 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

建立條件時，您可以根據建議活動的目標選取垂直產業。

| 垂直產業 | 目標 |
|--- |--- |
| 零售/電子商務 | 轉換帶動購買 |
| 潛在客戶開發/B2B/金融服務 | 轉換但未購買 |
| 媒體/出版 | 參與度 |

其他條件選項會根據您選取的垂直產業而變更。 您可以在&#x200B;**[!UICONTROL Recommendations > Settings]**&#x200B;頁面上設定預設垂直產業，或為每個條件指定垂直產業。

## 演演算法型別 {#section_885B3BB1B43048A88A8926F6B76FC482}

您選取的演演算法型別會決定可用的演演算法。 有數種演演算法型別，當您設定[!DNL Recommendations]活動時會以條件卡呈現。

![條件頁面](assets/criteria-page.png)

下表說明各種演演算法型別及其隨附的演演算法。

| 演演算法型別 | 使用時機 | 可用的演演算法 |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | 根據使用者的購物車內容提供建議。 | <ul><li>瀏覽過這些專案、也瀏覽了其他專案的使用者</li><li>瀏覽過這些專案、但購買了其他專案的使用者</li><li>購買了此專案、也購買了其他專案的使用者</li></ul>如需詳細資訊，請參閱&#x200B;*以推薦索引鍵*&#x200B;為基礎的建議[購物車型](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based)。 |
| [!UICONTROL Popularity-Based] | 根據您網站上的專案整體人氣或使用者最喜愛或檢視次數最多的類別、品牌、型別等內的專案人氣提供建議。 | <ul><li>全網站檢視次數最多</li><li>依類別檢視次數最多</li><li>依專案屬性檢視次數最多</li><li>全網站最暢銷商品</li><li>依類別排名的最暢銷商品</li><li>依專案屬性排名的最暢銷商品</li><li>依Analytics量度排名最前</li></ul> |
| [!UICONTROL Item-Based] | 根據找到使用者目前正在檢視或最近檢視之專案的類似專案提供建議。 | <ul><li>檢視過此項目、也檢視了其他項目的使用者</li><li>瀏覽過此項目、但購買了其他項目的使用者</li><li>購買了此項目、也購買了其他項目的使用者</li><li>具有類似屬性的專案</li></ul> |
| [!UICONTROL User-Based] | 根據使用者的行為提供建議。 | <ul><li>最近查看的項目</li><li>為您推薦</li></ul> |
| [!UICONTROL Custom Criteria] | 根據您上傳的自訂檔案提出建議。 | <ul><li>自訂演演算法</li></ul> |

如需每個演演算法的詳細資訊，請參閱[讓建議以建議索引鍵為依據](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

## 使用自訂建議索引鍵 {#custom-key}

您也可以讓建議以自訂設定檔屬性的值為依據。

>[!NOTE]
>
>可透過JavaScript、API或整合將自訂設定檔引數傳遞至[!DNL Target]。 如需自訂設定檔屬性的詳細資訊，請參閱[訪客設定檔](/help/main/c-target/c-visitor-profile/visitor-profile.md)。

例如，假設您要根據使用者最近新增至佇列的影片顯示建議影片。

1. 按一下&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**。

1. 按一下&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**。

1. 在[基本資訊區段](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)中填入資訊。

1. 在[建議的演演算法](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo)區段中，從&#x200B;**[!UICONTROL Algorithm Type]**&#x200B;清單中選取&#x200B;**[!UICONTROL Item Based]**。

1. 從&#x200B;**[!UICONTROL Algorithm]**&#x200B;清單中選取&#x200B;**[!UICONTROL People Who Viewed This, Viewed That]**。

1. 從&#x200B;**[!UICONTROL Recommendation Key]**&#x200B;清單中選取自訂設定檔屬性（例如，[!UICONTROL Last Show Added to Watchlist]）。

   ![建立新條件對話方塊](assets/custom-key1.png)

## 檢視條件資訊 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

您可以將游標移至卡片上並按一下卡片上的「資訊」圖示，這樣無需開啟條件，即可在快顯卡上查看條件詳情。

![條件卡暫留](/help/main/c-recommendations/c-algorithms/assets/criteria_hover.png)

按一下「**[!UICONTROL Algorithm Info]**」標籤，即可檢視選取條件的一般資訊，包括名稱、說明、垂直產業、頁面型別、建議金鑰、建議邏輯和演演算法ID。

![演算法資訊索引標籤](/help/main/c-recommendations/c-algorithms/assets/criteria_info.png)

按一下「**[!UICONTROL Algorithm Usage]**」標籤，以檢視參考所選條件的活動清單。 卡片會列出作用中、非作用中和草稿活動。 按一下「已上線活動/非作用中活動/草稿活動」下拉式清單，以檢視參照該條件的完整活動清單。 您可以按一下活動連結以開啟活動並編輯。

![演演算法使用情形索引標籤](/help/main/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>[!UICONTROL Algorithm Usage]功能目前僅支援Recommendations活動。 A/B測試、自動分配、自動鎖定目標，以及體驗鎖定目標(XT)活動目前不支援此功能，這些活動包含[個建議作為選件](/help/main/c-recommendations/recommendations-as-an-offer.md)。

---
keywords: 建議；建議活動；條件；演演算法；建議金鑰；自訂金鑰；垂直產業；零售；eccommerce；銷售機會產生；b2b；金融服務；媒體；發佈
description: 瞭解如何在Adobe [!DNL Target] [!DNL Recommendations]中使用條件。
title: 如何在 [!DNL Target] Recommendations中使用條件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 5%

---

# [!UICONTROL Criteria]

[!DNL Adobe Target] [!DNL Recommendations]中的[!UICONTROL Criteria]是根據預先決定的一組訪客行為決定要建議哪些產品或內容的規則。 條件能以熱門趨勢、訪客目前和過去的行為，或類似產品和內容為基礎。 您可以新增多個條件，將多個建議類型彼此測試。

以下各節將詳細說明您可用於每個索引鍵的條件索引鍵和建議邏輯。 按一下連結以取得更多詳細資訊。

## 垂直產業 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

建立條件時，您可以根據建議活動的目標選取垂直產業。

| 垂直產業 | 目標 |
|--- |--- |
| [!UICONTROL Retail/Ecommerce] | 轉換帶動購買 |
| [!UICONTROL Lead Generation/B2B/Financial Services] | 轉換但未購買 |
| [!UICONTROL Media/Publishing] | 參與度 |

其他條件選項會根據您選取的垂直產業而變更。 您可以在&#x200B;**[!UICONTROL Administration]>[!UICONTROL Recommendations]**&#x200B;頁面上設定預設的垂直產業，或為每個條件指定垂直產業。

## 演演算法型別 {#section_885B3BB1B43048A88A8926F6B76FC482}

您選取的演演算法型別會決定可用的演演算法。

下表說明各種演演算法型別及其隨附的演演算法。

| 演演算法型別 | 使用時機 | 可用的演演算法 |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | 根據使用者的購物車內容提供建議。 | <ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul>如需詳細資訊，請參閱&#x200B;*以推薦索引鍵*&#x200B;為基礎的建議[購物車型](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based)。 |
| [!UICONTROL Popularity-Based] | 根據您網站上的專案整體人氣或使用者最喜愛或檢視次數最多的類別、品牌、型別等內的專案人氣提供建議。 | <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | 根據找到使用者目前正在檢視或最近檢視之專案的類似專案提供建議。 | <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | 根據使用者的行為提供建議。 | <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
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

## 檢視條件資訊 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

您可以按一下[!UICONTROL Name]欄中的所需條件來檢視條件詳細資料。

「**[!UICONTROL Attributes]**」和「詳細資料」區段可讓您檢視所選條件的一般資訊，包括其[!UICONTROL Name]、[!UICONTROL Description]、[!UICONTROL Industry Vertical]、[!UICONTROL Page Types]、[!UICONTROL Recommendation Key]、[!UICONTROL Recommendation Logic]、[!UICONTROL Algorithm ID]以及「上次修改時間」資訊（日期及修改演演算法的人員）。

**[!UICONTROL Usage]**&#x200B;區段可讓您檢視參考所選條件的活動清單。

>[!NOTE]
>
>目前僅支援[!DNL Recommendations]活動的[!UICONTROL Algorithm Usage]功能。 包含[個建議作為選件](/help/main/c-recommendations/recommendations-as-an-offer.md)的[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]和[!UICONTROL Experience Targeting] (XT)活動目前不支援此功能。

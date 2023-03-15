---
keywords: 建議；建議活動；條件；演算法；建議索引鍵；自訂索引鍵；行業垂直；零售；電子商務；銷售機會產生；b2b；金融服務；媒體；發佈
description: 了解如何在Adobe中使用條件 [!DNL Target] [!DNL Recommendations].
title: 如何在 [!DNL Target] Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 23%

---

# 條件

中的標準 [!DNL Adobe Target] [!DNL Recommendations] 是根據預先決定的一組訪客行為決定要建議的產品或內容的規則。 條件可以基於人氣趨勢、訪客的目前和過去行為，或類似的產品和內容。您可以新增多個條件，將多個建議類型彼此測試。

以下小節將詳細說明條件索引鍵，以及可用於每個索引鍵的建議邏輯。 按一下連結以取得詳細資訊。

## 垂直產業 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

建立條件時，您會根據建議活動的目標選取垂直產業。

| 垂直產業 | 目標 |
|--- |--- |
| 零售/電子商務 | 轉換帶動購買 |
| 潛在客戶開發/B2B/金融服務 | 轉換但未購買 |
| 媒體/出版 | 參與 |

其他條件選項會根據您選取的垂直產業而變更。 您可以在 **[!UICONTROL Recommendations >設定]** 頁面，或者您可以為每個條件指定垂直的產業。

## 演算法類型 {#section_885B3BB1B43048A88A8926F6B76FC482}

您選取的演算法類型決定可用的演算法。 有數種演算法類型，在您設定 [!DNL Recommendations] 活動。

![條件頁面](assets/criteria-page.png)

下表說明各種演算法類型及其隨附的演算法。

| 演算法類型 | 使用時機 | 可用演算法 |
| --- | --- | --- |
| [!UICONTROL 購物車型] | 根據使用者的購物車內容提供建議。 | <ul><li>瀏覽過這些項目、也瀏覽過這些項目的使用者</li><li>瀏覽過這些、也購買了的人</li><li>購買、購買的人</li></ul>如需詳細資訊，請參閱 [購物車型](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) in *讓建議以建議索引鍵為依據*. |
| [!UICONTROL 人氣] | 根據網站上某個項目的整體人氣，或根據使用者最喜愛或最常檢視的類別、品牌、類型等項目的人氣，提出建議。 | <ul><li>網站上檢視次數最多</li><li>按類別檢視次數最多</li><li>依項目屬性檢視次數最多</li><li>網站最暢銷商品</li><li>最暢銷商品類別</li><li>依項目屬性的最暢銷商品</li><li>依Analytics量度排名前</li></ul> |
| [!UICONTROL 項目型] | 根據找到與使用者目前檢視或最近檢視的項目類似的項目來提供建議。 | <ul><li>檢視過此項目、也檢視了其他項目的使用者</li><li>瀏覽過此項目、但購買了其他項目的使用者</li><li>購買了此項目、也購買了其他項目的使用者</li><li>具有類似屬性的項目</li></ul> |
| [!UICONTROL 使用者型] | 根據使用者的行為提出建議。 | <ul><li>最近查看的項目</li><li>建議您</li></ul> |
| [!UICONTROL 自訂條件] | 根據您上傳的自訂檔案提出建議。 | <ul><li>自訂演算法</li></ul> |

如需每個演算法的詳細資訊，請參閱 [讓建議以建議索引鍵為依據](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## 使用自訂建議索引鍵 {#custom-key}

您也可以根據自訂設定檔屬性的值來提供建議。

>[!NOTE]
>
>自訂設定檔參數可傳遞至 [!DNL Target] 透過JavaScript、API或整合。 如需自訂設定檔屬性的詳細資訊，請參閱 [訪客設定檔](/help/main/c-target/c-visitor-profile/visitor-profile.md).

例如，假設您要根據使用者最近新增至佇列的影片來顯示建議電影。

1. 按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 條件]**.

1. 按一下 **[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件]**.

1. 填寫 [基本資訊部分](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. 在 [建議的演算法](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo) 部分，選擇 **[!UICONTROL 項目型]** 從 **[!UICONTROL 演算法類型]** 清單。

1. 選擇 **[!UICONTROL 瀏覽過此項目、也瀏覽了其他項目的使用者]** 從 **[!UICONTROL 演算法]** 清單。

1. 從 **[!UICONTROL 建議金鑰]** 清單(例如， [!UICONTROL 上次新增至觀看清單的節目])。

   ![建立新條件對話方塊](assets/custom-key1.png)

## 檢視條件資訊 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

您可以將游標移至卡片上並按一下卡片上的「資訊」圖示，這樣無需開啟條件，即可在快顯卡上查看條件詳情。

![條件卡暫留](/help/main/c-recommendations/c-algorithms/assets/criteria_hover.png)

按一下&#x200B;**[!UICONTROL 「演算法資訊」]**&#x200B;索引標籤，即可查看選取條件的一般資訊，包括名稱、說明、垂直產業、頁面類型、建議金鑰、建議邏輯和演算法 ID。

![演算法資訊索引標籤](/help/main/c-recommendations/c-algorithms/assets/criteria_info.png)

按一下&#x200B;**[!UICONTROL 「演算法使用情形」]**&#x200B;索引標籤，即可查看參照選取條件的活動清單。此卡片會列出使用中、非使用中和草稿活動。 按一下「即時活動/非使用中活動/草稿活動」下拉式清單，以檢視參考該條件之活動的完整清單。 您可以按一下活動連結以開啟活動並編輯。

![演算法使用情形索引標籤](/help/main/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>此 [!UICONTROL 演算法使用] 目前僅支援Recommendations活動。 A/B測試、自動分配、自動鎖定目標和體驗鎖定目標(XT)活動目前不支援此功能，這些活動包含 [選件形式的建議](/help/main/c-recommendations/recommendations-as-an-offer.md).

---
keywords: 建議；建議活動；條件；演演算法；建議金鑰；自訂金鑰；垂直產業；零售；eccommerce；銷售機會產生；b2b；金融服務；媒體；發佈
description: 瞭解如何在Adobe [!DNL Target] [!DNL Recommendations]中使用條件。
title: 如何在[!DNL Target]建議中使用條件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
TQID: 'https://experienceleague.adobe.com/Wo7I3piBQ7zwYF7kqRphDeWjcBCpyvIvTkwKK0t0f9U'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
    internal-label: Integrations
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 5%
---
# 開始使用[!UICONTROL 條件] {#get-started-criteria}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解條件如何在[!DNL Adobe Target Recommendations]中運作，以及有哪些垂直產業、演演算法型別和建議金鑰選項可供使用。

>[!ENDSHADEBOX]

[!DNL Adobe Target] [!DNL Recommendations]中的&#x200B;**[!UICONTROL 條件]**&#x200B;是根據預先決定的一組訪客行為決定要建議哪些產品或內容的規則。 條件可以基於人氣趨勢、訪客的目前和過去行為，或類似的產品和內容。 您可以將多個條件新增至活動，以相互測試多個建議型別。

選取的垂直產業和演演算法型別決定了建立條件時可用的選項。

## 垂直產業 {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

建立條件時，會根據Recommendations活動的目標選取垂直產業。

| 垂直產業 | 目標 |
|--- |--- |
| **[!UICONTROL 零售/電子商務]** | 轉換帶動購買 |
| **[!UICONTROL 潛在客戶開發/B2B/金融服務]** | 轉換但未購買 |
| **[!UICONTROL 媒體/出版]** | 參與度 |

其他條件選項會根據選取的垂直產業而變更。 可在&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 建議]**&#x200B;頁面上設定預設垂直產業，或為每個條件指定垂直產業。

## 演演算法型別 {#section_885B3BB1B43048A88A8926F6B76FC482}

選取的演演算法型別會決定可用的演演算法。 下表說明演演算法型別及其隨附的演演算法。

| 演演算法型別 | 使用時機 | 可用的演演算法 |
| --- | --- | --- |
| **[!UICONTROL 購物車型]** | 根據使用者的購物車內容提供建議。 | <ul><li>**[!UICONTROL 瀏覽過這些專案的使用者，也瀏覽了]**</li><li>**[!UICONTROL 瀏覽過這些商品的人們也購買了]**</li><li>**[!UICONTROL 已購買這些商品的人，也已購買]**</li></ul>如需詳細資訊，請參閱&#x200B;*以推薦索引鍵*&#x200B;為基礎的建議[購物車型](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based)。 |
| **[!UICONTROL 以熱門程度為基礎]** | 根據網站中專案的整體人氣或使用者最喜愛或檢視次數最多類別、品牌、型別等內的專案人氣提供建議。 | <ul><li>整個網站檢視次數最多&#x200B;****</li><li>依類別檢視次數最多&#x200B;****</li><li>**[!UICONTROL 檢視次數最多的專案屬性]**</li><li>**[!UICONTROL 依輪廓屬性的檢視次數最多項目]**</li><li>整個網站&#x200B;**[!UICONTROL 最暢銷商品]**</li><li>**[!UICONTROL 依類別排名的最暢銷商品]**</li><li>**[!UICONTROL 依專案屬性的最暢銷商品]**</li><li>**[!UICONTROL 依個人檔案屬性的最暢銷商品]**</li><li>**[!UICONTROL Analytics量度排名最前]**</li></ul> |
| **[!UICONTROL 專案型]** | 根據與使用者目前正在檢視或最近檢視之專案相似的專案提供建議。 | <ul><li>**[!UICONTROL 瀏覽過此專案、也瀏覽了其他專案的使用者]**</li><li>**[!UICONTROL 瀏覽過此專案、但購買了其他專案的使用者]**</li><li>**[!UICONTROL 購買了此專案、也購買了其他專案的使用者]**</li><li>**[!UICONTROL 具有類似屬性的專案]**</li></ul> |
| **[!UICONTROL 以使用者為基礎]** | 根據使用者的行為提供建議。 | <ul><li>**[!UICONTROL 最近查看的項目]**</li><li>**[!UICONTROL 為您推薦]**</li></ul> |
| **[!UICONTROL 自訂條件]** | 根據上傳的自訂檔案提出建議。 | <ul><li>自訂演演算法</li></ul> |

如需每個演演算法的詳細資訊，請參閱[讓建議以建議索引鍵為依據](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

## 使用自訂建議金鑰 {#custom-key}

Recommendations也可以根據自訂設定檔屬性的值。 例如，可根據使用者最近新增至佇列的影片顯示建議影片。

1. 按一下&#x200B;**[!UICONTROL 建議]** > **[!UICONTROL 條件]**。

1. 按一下&#x200B;**[!UICONTROL 建立條件]** > **[!UICONTROL 建立條件]**。

   ![已開啟[建立條件]功能表的[條件]頁面，顯示[建立條件]和[建立條件順序]](../assets/criteria_1.png)

1. 在[基本資訊區段](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)中填入資訊。

1. 在[建議的演演算法](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo)區段中，從&#x200B;**[!UICONTROL 演演算法型別]**&#x200B;清單中選取&#x200B;**[!UICONTROL 以專案為基礎]**。

1. 從&#x200B;**[!UICONTROL 演演算法]**&#x200B;清單中選取&#x200B;**[!UICONTROL 檢視過此專案、也檢視了該]**&#x200B;專案的使用者。

1. 從&#x200B;**[!UICONTROL 建議索引鍵]**&#x200B;清單Select自訂設定檔屬性（例如&#x200B;**[!UICONTROL 最近新增到觀看清單的節目]**）。

   >[!NOTE]
   >
   >可透過JavaScript、API或整合將自訂設定檔引數傳遞至[!DNL Target]。 如需自訂設定檔屬性的詳細資訊，請參閱[訪客設定檔](/help/main/c-target/c-visitor-profile/visitor-profile.md)。

   ![建立條件對話方塊，其中顯示[建議演演算法]區段及[演演算法型別]、[演演算法]和[建議索引鍵]清單](../assets/criteria_2.png)

## 檢視條件資訊 {#section_7162DE58E4594FD688A4D7FDB829FD8B}

條件詳細資訊會顯示條件的設定方式以及可使用條件的活動。

1. 按一下&#x200B;**[!UICONTROL 建議]** > **[!UICONTROL 條件]**&#x200B;以顯示條件清單。

1. 在&#x200B;**[!UICONTROL 名稱]**&#x200B;欄中按一下所需的條件。

1. 檢視&#x200B;**[!UICONTROL 屬性]**&#x200B;和詳細資訊區段中選取條件的一般資訊，包括其&#x200B;**[!UICONTROL 名稱]**、**[!UICONTROL 描述]**、**[!UICONTROL 垂直產業]**、**[!UICONTROL 頁面型別]**、**[!UICONTROL 建議金鑰]**、**[!UICONTROL 建議邏輯]**、**[!UICONTROL 演演算法ID]**&#x200B;和上次修改時間資訊（日期及修改演演算法的使用者）。

1. 檢視參考&#x200B;**[!UICONTROL 使用狀況]**&#x200B;區段中選取條件的活動清單。

   >[!NOTE]
   >
   >目前僅支援[!DNL Recommendations]活動的&#x200B;**[!UICONTROL 演演算法使用量]**&#x200B;功能。 **[!UICONTROL A/B測試]**、**[!UICONTROL 自動分配]**、**[!UICONTROL 自動鎖定目標]**&#x200B;以及&#x200B;**[!UICONTROL 體驗鎖定目標]** (XT)活動目前不支援此功能，這些活動包含[個建議作為選件](/help/main/c-recommendations/recommendations-as-an-offer.md)。

   ![屬性與詳細資訊區段及使用狀況區段標示的條件詳細資料](../assets/criteria_3.png)

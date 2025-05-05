---
keywords: 包含規則;包含條件;建議;建立新條件;促銷活動;動態篩選;動態;空白值;忽略篩選規則;靜態篩選;按值篩選;實體屬性比對;輪廓屬性比對;參數比對;靜態篩選
description: 瞭解如何在 [!DNL Target] Recommendations中建立條件與促銷的包含規則。
title: 如何在Recommendations中使用動態和靜態包含規則？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '1825'
ht-degree: 16%

---

# 使用動態和靜態包含規則

在[!DNL Adobe Target]中建立條件和促銷活動的包含規則，並新增動態或靜態篩選規則，以便為您的建議取得更好的結果。

對於條件和促銷活動，建立和使用包含規則的過程很相似，就如同使用案例和範例很相似一樣。本節將說明條件和促銷活動以及如何使用包含規則。

## 將篩選規則新增至條件和促銷活動 {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

以下章節包含更多資訊: 

### 將篩選規則新增至條件

1. 當[建立條件](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE) (**[!UICONTROL Recommendations]> [!UICONTROL Criteria] > [!UICONTROL Create Criteria] >[!UICONTROL Create Criteria]**)時，請按一下&#x200B;**[!UICONTROL Inclusion Rules]**&#x200B;下方的&#x200B;**[!UICONTROL Add Filtering Rule]**。

   ![新增篩選規則](/help/main/c-recommendations/c-algorithms/assets/add-fitering-rule.png)

1. 按一下「建議應遵守哪些其他規則」方塊中的&#x200B;**靜態篩選器**&#x200B;下拉式清單，然後從[!UICONTROL Static Filter]下拉式清單中選擇所需的選項。

   ![靜態篩選器下拉式清單](/help/main/c-recommendations/c-algorithms/assets/dynamic-and-static.png)

   可用的選項依選取的行業別和建議金鑰而不同。

### 將篩選規則新增至促銷活動

1. 在[建立促銷活動](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)時，請選取&#x200B;**[!UICONTROL Promote by Attribute]**，然後按一下&#x200B;**[!UICONTROL Add Filtering Rule]**。

## 篩選類型 {#section_0125F1ED10A84C0EB45325122460EBCD}

以下小節列出條件和促銷活動的[!UICONTROL Dynamic Filtering]與[!UICONTROL Filter by Value]的篩選選項型別：

### 動態篩選

動態包含規則比靜態包含規則更強大，而且會產生更好的結果和參與。 考慮以下事項：

* 動態包含規則會透過比對使用者設定檔引數或mbox呼叫中的屬性來傳送建議。

  例如，您可以建立「最受歡迎的條件」建議。 從傳回的建議集中，您可以針對使用者存取顯示建議的頁面時傳遞的屬性，即時篩選掉任何建議。

* 使用靜態規則來限制建議中包含的專案（而不使用集合）。

* 您可以視需要建立儘可能多的動態包含規則。 包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。

下列選項適用於動態篩選：

| 動態篩選選項 | 詳細資料 |
| --- | --- |
| [[!UICONTROL Entity Attribute Matching]](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | 比較一批潛在的建議專案與使用者已有互動的特定專案，以動態篩選。<P>當您想要顯示最可能吸引訪客的建議（例如訪客最喜愛的品牌）時，請使用[!UICONTROL Entity Attribute Matching]。 |
| [[!UICONTROL Profile Attribute Matching]](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | 比較專案（實體）與使用者設定檔中的值，以動態篩選。<P>當您想要顯示符合儲存在訪客設定檔中的值（例如大小或最喜愛的品牌）的建議，請使用[!UICONTROL Profile Attribute Matching]。 |
| [[!UICONTROL Parameter Matching]](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | 比較專案（實體）與請求（API或mbox）中的值，以動態篩選。<P>使用[!UICONTROL Parameter Matching]來建議符合頁面引數或訪客引數（例如裝置維度或地理位置）的內容。 |

### 按值篩選

下列選項可依值篩選：

| 依值選項篩選 | 詳細資料 |
| --- | --- |
| [[!UICONTROL Static Filter]](/help/main/c-recommendations/c-algorithms/static-value.md) | 手動輸入一或多個要篩選的靜態值。 |

## 可用的運運算元 {#operators}

動態條件和促銷活動比靜態條件和促銷活動強大得多，並產生更好的結果和參與。

下列範例提供如何在行銷工作中使用動態促銷和排除的一般概念：

| 運算子 | 範例 |
| --- | --- |
| [!UICONTROL equals any of]<P>（[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]、[!UICONTROL Parameter Matching]和[!UICONTROL Static Filter]皆可使用。） | 如果在動態促銷活動中使用「等於」運運算元，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以促銷下列來源的其他專案：<ul><li>相同品牌</li><li>相同類別</li><li>來自自家品牌的相同類別和</li><li>相同商店</li></ul> |
| [!UICONTROL does not equal any of]<P>（[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]、[!UICONTROL Parameter Matching]和[!UICONTROL Static Filter]皆可使用。） | 如果在動態促銷活動中使用「[!UICONTROL does not equal any of]」運運算元，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以促銷下列來源的其他專案：<ul><li>另一部電視劇</li><li>不同的型別</li><li>不同的產品系列</li><li>不同的樣式ID</li></ul> |
| [!UICONTROL is greater than or equal to any of]<P>（[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]、[!UICONTROL Parameter Matching]和[!UICONTROL Static Filter]皆可使用。） | 使用&quot;[!UICONTROL is greater than or equal to any of]&quot;運運算元，當訪客檢視您網站上的專案時（例如產品），您可以促銷如下的其他專案：<ul><li>成本相同或更昂貴</li></ul> |
| [!UICONTROL is less than or equal to any of]<P>（[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]、[!UICONTROL Parameter Matching]和[!UICONTROL Static Filter]皆可使用。） | 使用&quot;[!UICONTROL is less than or equal to an of]&quot;運運算元，當訪客檢視您網站上的專案時（例如產品），您可以促銷如下的其他專案：<ul><li>成本相同或較便宜</li><li>排除較便宜的專案</li></ul> |
| [!UICONTROL contains any of] （可與[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]、[!UICONTROL Parameter Matching]和[!UICONTROL Static Filter]搭配使用。） | 使用&quot;[!UICONTROL contains any of]&quot;運運算元，當訪客檢視您網站上的專案時（例如產品），您可以促銷如下的其他專案：<ul><li>標題包含相同品牌</li></ul> |
| [!UICONTROL does not contain any of]<P>（[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]、[!UICONTROL Parameter Matching]和[!UICONTROL Static Filter]皆可使用。） | 使用「不包含任何」運運算元，當訪客檢視您網站上的專案時（例如產品），您可以促銷如下的其他專案：<ul><li>標題不含粗字</li></ul> |
| [!UICONTROL starts with any of]<P>（[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]、[!UICONTROL Parameter Matching]和[!UICONTROL Static Filter]皆可使用。） | 使用&quot;[!UICONTROL starts with an of]&quot;運運算元，當訪客檢視您網站上的專案時（例如產品），您可以促銷如下的其他專案：<ul><li>產品名稱以iPhone開頭</li></ul> |
| [!UICONTROL ends with any of]<P>（[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]、[!UICONTROL Parameter Matching]和[!UICONTROL Static Filter]皆可使用。） | 使用&quot;[!UICONTROL ends with an of]&quot;運運算元，當訪客檢視您網站上的專案時（例如產品），您可以促銷如下的其他專案：<ul><li>內容結尾是EN，表示英文</li></ul> |
| [!UICONTROL is between]<P>（可與[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching]搭配使用。） | 如果在動態促銷活動中使用「i[!UICONTROL s between]」運運算元，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以促銷如下的其他專案：<ul><li>更貴</li><li>更便宜</li><li>成本加減30%</li><li>同季的後續集數</li><li>系列中先前的書籍</li></ul> |
| [!UICONTROL list contains an item in]<P>（[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching]均可用。） | 在設定檔屬性比對中使用「[!UICONTROL list contains an item in]」運運算元，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以促銷如下的其他專案：<ul><li>可在訪客的地理位置中使用</li></ul>**範例**：您想要建議只在訪客地理區域中可用的專案。<P>您的篩選規則可能如下所示：<P>`availableGeographies list contains an item in user.currentGeography`<P>**注意**：使用此運運算元時，規則的[右側](#caveats)應該會有清單。 |
| [!UICONTROL list does not contain an item in]<P>（[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching]均可用。） | 在設定檔屬性比對中使用&quot;[!UICONTROL list does not contain an item in]&quot;運運算元，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以排除下列其他專案：<ul><li>在訪客已檢視的最後10個專案清單中</li></ul></ul>**範例**：您不想要促銷訪客最近檢視過且沒有興趣的專案。<P>您的篩選規則可能如下所示：<P>`id is not contained in list user.lastViewedItems`<P>**注意**：使用此運運算元時，規則的[右側](#caveats)應該會有清單。 |
| [!UICONTROL list contains an item in]<P>（可與[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching]搭配使用。） | 在設定檔屬性比對中使用&quot;[!UICONTROL list contains an item in]&quot;運運算元，當訪客檢視您網站上的專案時（例如體育賽事或音樂會），您可以促銷如下的其他專案：<ul><li>與訪客最喜愛的團隊之一相關聯</li></ul>**範例**：您想要建議與訪客最喜愛的團隊之一相關聯的遊戲。<P>您的篩選規則可能如下所示：<P>` teamsPlaying list contains an item in user.favoriteTeams`<P>**注意**：使用此運運算元時，規則的[兩面](#caveats)中應該要有清單。 |
| [!UICONTROL list does not contain an item in]<P>（可與[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching]搭配使用。） | 在引數屬性比對中使用&quot;[!UICONTROL list does not contain an item in]&quot;運運算元，當訪客檢視您網站上的專案時（例如產品、文章或電影），您可以排除下列其他專案：<ul><li>包含在禁止型別清單中</li></ul>**範例**：您想要排除成人訪客可用的專案，例如菸草和酒精。<P>您的篩選規則可能如下所示：<P>`itemType is not contained in list mbox.prohibitedTypes`<P>**注意**：使用此運運算元時，規則的[兩面](#caveats)中應該要有清單。 |
| [!UICONTROL list contains all items in]<P>（可與[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching]搭配使用。） | 在設定檔屬性比對中使用&quot;[!UICONTROL list does not contain an item in]&quot;運運算元，當訪客檢視您網站上的專案時（例如工作張貼或配方），您可以促銷如下的其他專案：<ul><li>包含一組技能</li><li>包含一組必要的要素</li></ul>**範例1**：假設訪客有一組技能(Java、C++和HTML)。 目錄中的專案是具有所需技能(Java和HTML)的工作。 建議工作給訪客之前，請確定訪客的設定檔包含所有必要的技能。<P>您的篩選規則可能如下所示：<P>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<P>**範例2**：假設使用者有食品櫃配料清單。 配方包含所需成分的清單。 建議訪客的配方之前，請確定訪客的設定檔包含所有必要的要素。<P>您的篩選規則可能如下所示：<P>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<P>**注意**：使用此運運算元時，規則的[兩面](#caveats)中應該要有清單。 |
| [!UICONTROL list does not contain all items in]<P>（可與[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching]搭配使用。） | 在實體屬性比對中使用&quot;[!UICONTROL list does not contain all items in]&quot;運運算元，當訪客檢視您網站上的專案時（例如體育賽事或音樂會），您可以促銷如下的其他專案：<ul><li>不要包含一組團隊</li></ul>**範例**：假設一項體育賽事包含兩支球隊。 訪客的設定檔指出該訪客不想檢視這些團隊的遊戲。 如果您希望確保這些團隊在玩遊戲，您不會推薦遊戲。<P>您的篩選規則可能如下所示：<P>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<P>**注意**：使用此運運算元時，規則的[兩面](#caveats)中應該要有清單。 |

## 依[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching]篩選時處理空白值 {#section_7D30E04116DB47BEA6FF840A3424A4C8}

您可選擇數個選項，在依[!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]及[!UICONTROL Parameter Matching]篩選退出條件及促銷活動時處理空白值。

以前，如果值空白，則不會傳回結果。如果條件有空白值，則「如果 *x* 為空白」下拉式清單可讓您選擇適當的動作來執行，如下圖所示:

![empty_value影像](assets/empty_value.png)

若要選取所需的動作，請將游標停留在齒輪圖示(![icon_gear image](assets/icon_gear.png))上，然後選擇所需的動作：

| Action | 可用於 | 詳細資料 |
|--- |--- |--- |
| [!UICONTROL Ignore this filtering rule] | [!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching] | 此動作是[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching]的預設值。<P>此選項會指定忽略規則。例如，假設有三個篩選規則，而第三個規則未傳遞任何值，為了避免不傳回任何結果，您可以直接用空白值忽略第三個規則。 |
| [!UICONTROL Do not show any results for this criteria]<P>（僅限條件） | [!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching] | 此動作是[!UICONTROL Entity Attribute Matching]的預設值。<P>在新增此選項之前，此動作是[!DNL Target]處理空白值的方式：不顯示此條件的結果。 |
| [!UICONTROL 不促銷任何專案<P>（僅限促銷活動）] | [!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching] | 此動作是[!UICONTROL Entity Attribute Matching]的預設值。<P>在新增此選項之前，此動作是[!DNL Target]處理空白值的方式：不顯示此條件的結果。 |
| [!UICONTROL Use a static value] | [!UICONTROL Entity Attribute Matching]、[!UICONTROL Profile Attribute Matching]和[!UICONTROL Parameter Matching] | 如果值為空白，您可以選擇使用靜態值。 |

## 注意事項 {#caveats}

>[!IMPORTANT]
>
>使用「等於」和「不等於」運算子時，在執行階段，動態條件或促銷活動中的不同資料類型可能不相容。如果左側有預先定義的屬性或自訂屬性，請在右側明智地使用[!UICONTROL Value]、[!UICONTROL Margin]、[!UICONTROL Inventory]和[!UICONTROL Environment]值。

![左_右影像](assets/left_right.png)

下表顯示有效規則，以及在執行階段可能不相容的規則:

| 相容規則 | 可能不相容的規則 |
|--- |--- |
| value - 介於 - 目前項目的 90% 和 110% - salesValue | salesValue - 介於 - 目前項目的 90% 和 110% - value |
| value - 介於 - 目前項目的 90% 和 110% - value | clearancePrice - 介於 - 目前項目的 90% 和 110% - margin |
| margin - 介於 - 目前項目的 90% 和 110% - margin | storeInventory - 等於 - 目前項目的 - inventory |
| inventory - 等於 - 目前項目的 - inventory |  |

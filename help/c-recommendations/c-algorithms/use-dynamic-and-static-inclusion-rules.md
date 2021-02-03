---
keywords: 包含規則;包含條件;建議;建立新條件;促銷活動;動態篩選;動態;空白值;忽略篩選規則;靜態篩選;按值篩選;實體屬性比對;設定檔屬性比對;參數比對;靜態篩選
description: 有關在Adobe Target Recommendations中建立標準和促銷包含規則，以及新增其他動態或靜態篩選規則以取得更佳結果的資訊。
title: 在Target Recommendations中使用動態和靜態包含規則
feature: Recommendations
mini-toc-levels: 3
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 41%

---


# ![PREMIUM](/help/assets/premium.png) 使用動態和靜態包含規則{#use-dynamic-and-static-inclusion-rules}

有關在[!DNL Adobe Target]中建立標準和促銷的包含規則，以及新增其他動態或靜態篩選規則，以便為建議取得更佳結果的資訊。

>[!NOTE]
>
>對於條件和促銷活動，建立和使用包含規則的過程很相似，就如同使用案例和範例很相似一樣。本節將涵蓋標準和促銷活動以及包含規則的使用。

## 將篩選規則新增至條件 {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

[建立條件時](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)，請按一下&#x200B;**[!UICONTROL 「包含規則」]**&#x200B;下的&#x200B;**[!UICONTROL 「新增篩選規則」]**。

![](assets/inclusion_options_new.png)

可用的選項依選取的行業別和建議金鑰而不同。

## 將篩選規則新增至促銷活動  {#section_D59AFB62E2EE423086281CF5D18B1076}

[建立促銷活動](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)時，請選取&#x200B;**[!UICONTROL 「依屬性促銷」]**，然後按一下&#x200B;**[!UICONTROL 「新增篩選規則」]**。

![](assets/inclusion_options.png)

## 篩選類型 {#section_0125F1ED10A84C0EB45325122460EBCD}

以下各節列出[!UICONTROL 動態篩選]和[!UICONTROL 依值篩選]的篩選選項類型，供標準和促銷使用：

### 動態篩選

動態包含規則比靜態包含規則更強大，而且可產生更佳的結果和參與度。 考慮以下事項:

* 動態包含規則會比對使用者描述檔參數或mbox呼叫中的屬性，以提供建議。

   例如，您可以建立「最受歡迎的准則」建議，然後針對傳回的建議集建立建議，然後針對使用者存取顯示建議的頁面時傳遞的屬性，即時篩選任何建議。

* 使用靜態規則來限制建議中包含的項目（而非使用系列）。

* 您可以視需要建立任意數量的動態包含規則。 包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。

動態篩選可使用下列選項：

| 動態篩選選項 | 詳細資料 |
| --- | --- |
| [實體屬性比對](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | 透過比較潛在建議項目群組與使用者已互動的特定項目，動態篩選。<br>當您 [!UICONTROL 想要顯] 示最有可能吸引訪客的建議（例如訪客的最愛品牌）時，請使用實體屬性符合。 |
| [設定檔屬性比對](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | 透過比較項目（實體）與使用者描述檔中的值，動態篩選。<br>當您 [!UICONTROL 想要顯示] 符合訪客描述檔中儲存之值（例如大小或我的最愛品牌）的建議時，請使用描述檔屬性符合。 |
| [參數比對](/help/c-recommendations/c-algorithms/parameter-matching.md) | 透過比較項目（實體）與請求中的值（API或mbox），動態篩選。<br>使用 [!UICONTROL 參數] 匹配可建議符合頁面參數或訪客參數的內容，例如裝置尺寸或地理位置。 |

### 按值篩選

以下選項可用於按值篩選：

| 依值篩選選項 | 詳細資料 |
| --- | --- |
| [靜態濾鏡](/help/c-recommendations/c-algorithms/static-value.md) | 手動輸入一或多個靜態值以進行篩選。 |

## 動態准則和促銷範例

動態標準和促銷比靜態標準和促銷強大得多，可產生更佳的結果和參與度。

以下範例提供如何在行銷活動中使用動態促銷的一般概念：

| 運算元 | 範例 |
| --- | --- |
| 等於 | 在動態促銷中使用「等於」運算子，當訪客在您的網站上檢視項目（例如產品、文章或影片）時，您可從以下網站促銷其他項目：<ul><li>相同品牌</li><li>相同種類</li><li>相同類別 AND 來自於自主品牌</li><li>相同商店</li></ul> |
| 不等於 | 在動態促銷中使用「不等於」運算子，當訪客在您的網站上檢視項目（例如產品、文章或影片）時，您可以從以下位置促銷其他項目：<ul><li>不同影集</li><li>不同內容類型</li><li>不同產品系列</li><li>不同樣式 ID</li></ul> |
| 介於 | 在動態促銷中使用「介於」運算子，當訪客在您的網站上檢視項目（例如產品、文章或影片）時，您可以促銷其他項目：<ul><li>較貴</li><li>較便宜</li><li>成本加或減 30%</li><li>同一季的最後幾集</li><li>同一套書的前幾本</li></ul> |

## 按實體屬性匹配、描述檔屬性匹配和參數匹配{#section_7D30E04116DB47BEA6FF840A3424A4C8}篩選時處理空值

在依[!UICONTROL 「實體屬性符合]」、[!UICONTROL 「描述檔屬性符合]」和[!UICONTROL 退出標準和促銷活動的「參數符合]」篩選時，您可以選擇數個選項來處理空值。

以前，如果值空白，則不會傳回結果。如果條件有空白值，則「如果 *x* 為空白」下拉式清單可讓您選擇適當的動作來執行，如下圖所示:

![](assets/empty_value.png)

若要選取所需的動作，請將游標停留在齒輪圖示上 (![](assets/icon_gear.png))，然後選擇所需的動作:

| Action | 可用於 | 詳細資料 |
|--- |--- |--- |
| [!UICONTROL 忽略此篩選規則] | [!UICONTROL 描述檔屬性] [!UICONTROL 比對與參數比對] | 這是[!UICONTROL 描述檔屬性符合]和[!UICONTROL 參數符合]的預設動作。<br>此選項會指定忽略規則。例如，假設有三個篩選規則，而第三個規則未傳遞任何值，為了避免不傳回任何結果，您可以直接用空白值忽略第三個規則。 |
| [!UICONTROL 不要顯示此准則的任何結果]<br>（僅限准則） | [!UICONTROL 實體屬性匹配]、描述 [!UICONTROL 檔屬性匹配]、參數 [!UICONTROL 匹配] | 這是[!UICONTROL 實體屬性符合]的預設動作。<br>[!DNL Target]在新增此選項的值之前，此動作代表 處理空白值的方式，也就是不顯示此條件的任何結果。 |
| [!UICONTROL 不促銷任何項目<br>（僅限促銷）] | [!UICONTROL 實體屬性匹配]、描述 [!UICONTROL 檔屬性匹配]、參數 [!UICONTROL 匹配] | 這是[!UICONTROL 實體屬性符合]的預設動作。<br>[!DNL Target]在新增此選項的值之前，此動作代表 處理空白值的方式，也就是不顯示此條件的任何結果。 |
| [!UICONTROL 使用靜態值] | [!UICONTROL 實體屬性匹配]、描述 [!UICONTROL 檔屬性匹配]、參數 [!UICONTROL 匹配] | 如果值為空白，您可以選擇使用靜態值。 |

## 注意事項 {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>使用「等於」和「不等於」運算子時，在執行階段，動態條件或促銷活動中的不同資料類型可能不相容。如果左側具有預先定義的屬性或自訂屬性，則您應在右側明智地使用[!UICONTROL Value]、[!UICONTROL Margin]、[!UICONTROL Inventory]和[!UICONTROL Environment]值。

![](assets/left_right.png)

下表顯示有效規則，以及在執行階段可能不相容的規則:

| 相容規則 | 可能不相容的規則 |
|--- |--- |
| value - 介於 - 目前項目的 90% 和 110% - salesValue | salesValue - 介於 - 目前項目的 90% 和 110% - value |
| value - 介於 - 目前項目的 90% 和 110% - value | clearancePrice - 介於 - 目前項目的 90% 和 110% - margin |
| margin - 介於 - 目前項目的 90% 和 110% - margin | storeInventory - 等於 - 目前項目的 - inventory |
| inventory - 等於 - 目前項目的 - inventory |  |

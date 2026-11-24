---
keywords: 目錄搜尋；目錄；搜尋；排除；集合；篩選器；推薦
description: 瞭解如何使用[!DNL Recommendations] [!UICONTROL 目錄搜尋]來尋找產品或內容、從目錄中移除專案等等。
title: 如何使用[!DNL Recommendations] [!UICONTROL 目錄搜尋]？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
TQID: 'https://experienceleague.adobe.com/en3hkFsDjEE86Tc-3vPSiZFy0K47SftZMN6RW0INNic'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 7%
---
# [!UICONTROL 目錄搜尋] {#catalog-search}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在[!DNL Adobe Recommendations]中搜尋目錄以尋找產品或內容，以及如何篩選、檢視和移除專案。

>[!ENDSHADEBOX]

[!DNL Adobe Recommendations]中的&#x200B;**[!UICONTROL 目錄搜尋]**&#x200B;頁面是用來尋找目錄中的產品或內容。 此頁面最基本的工作是搜尋專案。 此頁面也可讓您變更環境、篩選多面向、修改表格中的欄等等。

目錄是整個產品集（實體）。 它可以包含許多集合，這些集合會將產品組織在邏輯群組中。

目錄索引會在第一個摘要上傳時自動建立，並根據[指定的排程](/help/main/c-recommendations/c-products/feeds.md#steps)重新整理。

透過摘要檔案、API或mbox更新收到更新時，目錄會自動重新整理。 更新通常會在一小時內完成。 如果正在進行更新，會顯示最新更新的開始時間。 如果沒有任何正在進行的更新，會顯示最新更新的開始和結束時間。

## 搜尋目錄

使用搜尋結果來檢閱目錄中的專案，並視需要從中移除專案。

1. 按一下&#x200B;**[!UICONTROL 建議]** > **[!UICONTROL 目錄搜尋]**。

1. （選擇性）若要篩選結果，請按一下&#x200B;**[!UICONTROL 顯示篩選器]**&#x200B;圖示（![顯示篩選器圖示](/help/main/assets/icons/Filter.svg)），然後選取要套用的篩選器。 可用的篩選器為&#x200B;**[!UICONTROL 環境]**、**[!UICONTROL 集合]**、**[!UICONTROL 類別]**、**[!UICONTROL 品牌]**、**[!UICONTROL 詳細目錄]**&#x200B;和&#x200B;**[!UICONTROL 值]**。

   [環境](/help/main/administrating-target/environments.md)組織網站和生產前環境，以進行管理和分隔的報表。 若要變更環境，請從&#x200B;**[!UICONTROL 環境]**&#x200B;下拉式清單中選取所需的環境。

   ![反白顯示篩選面板的目錄搜尋頁面：集合、類別、品牌、詳細目錄、值和進階搜尋](../assets/catalog_search.png)

1. 在&#x200B;**[!UICONTROL 搜尋範圍]**&#x200B;欄位中輸入搜尋字詞。

1. （選擇性）從選項功能表中選取搜尋選項（從&#x200B;**[!UICONTROL 搜尋範圍]**&#x200B;欄位的向下箭頭開啟），以調整搜尋。

   搜尋選項包含下列項目:

   * ID
   * 名稱
   * 訊息

1. 按一下&#x200B;**[!UICONTROL 自訂表格]**&#x200B;圖示（![自訂表格圖示](/help/main/assets/icons/ColumnSetting.svg)）以修改&#x200B;**[!UICONTROL 目錄搜尋]**&#x200B;頁面上的作用中欄。

   ![目錄搜尋頁面，其中的「自訂表格」圖示反白顯示](../assets/catalog_search_4.png)

1. 捲動搜尋結果中的專案以檢視縮圖和其他產品資訊。

   >[!NOTE]
   >
   >在針對具有某數值的自訂屬性進行目錄搜尋時，結果會將自訂屬性視為字串型別，而非數值。
   >
   >目前無法變更屬性的型別。 若要要求變更，請[開啟客戶問題](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，此問題參考其型別必須從字串變更為數值的屬性。

1. 按一下搜尋結果中的專案可檢視其詳細資訊，包括其ID、名稱、訊息、類別等。

   ![目錄專案的詳細資料，顯示其ID、類別、利潤和其他屬性](../assets/catalog_search_2.png)

1. 若要從目錄中移除專案，請按一下[從目錄中移除]。**&#x200B;**

   然後，會從目錄索引中移除該專案的所有相關資訊。 只有在資料摘要中再次新增專案時，專案才會再次包含在目錄中。 已刪除的專案也必須從摘要中個別刪除。

   ![目錄專案的詳細資料，其中的[從目錄移除]按鈕反白顯示](../assets/catalog_search_3.png)

<!--
### Perform an advanced search {#advanced-search}

You can use [!UICONTROL Advanced Search] to further refine your search results or to save your search results as a [collection](/help/main/c-recommendations/c-products/collections.md) or [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Click the **[!UICONTROL Advanced Search]** link.

   ![Advanced Search page](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use the drop-down lists to specify the parameter, operator, and values for your search.

1. (Optional) Click **[!UICONTROL Add Rule]** to add an additional search rule.

   Each additional search rule is joined with the AND operator.

1. Click **[!UICONTROL Search]**.

1. (Optional) Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   For more information, see [Create a collection or exclusion based on Advanced Search](#save-as) below.
-->

<!--
## Modify the Catalog Search page (filters and columns)

You can temporarily modify the available filters and columns on the [!UICONTROL Catalog Search] page for the current session.

### Modify filters

You can add additional filter facets to the [!UICONTROL Catalog Search] page.

1. In the **[!UICONTROL Filters]** panel, click **[!UICONTROL Modify]**.

   ![Modify filters link](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Select the desired search facets (ID, name, message, etc.), then click **[!UICONTROL Save]**.

   ![Add filters](/help/main/c-recommendations/c-products/assets/add-filters.png)

Keep in mind that the additional filter facets are available in the current session only.
-->



<!--
## Create a collection or exclusion based on Advanced Search {#save-as}

You can create [collections](/help/main/c-recommendations/c-products/collections.md) or [exclusions](/help/main/c-recommendations/c-products/exclusions.md) using [!UICONTROL Advanced Search] on the [!UICONTROL Catalog Search] page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Perform an [advanced search](#advanced-search).

1. Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections or exclusions based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. Exclusions are handled in a similar fashion.
-->

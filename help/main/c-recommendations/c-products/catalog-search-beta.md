---
keywords: 目錄搜尋；目錄；搜尋；排除；集合；篩選器；推薦
description: 瞭解如何使用 [!DNL Recommendations] [!UICONTROL Catalog Search] 若要尋找產品或內容，請從目錄中移除專案等等。
title: 如何使用 [!DNL Recommendations] [!UICONTROL Catalog Search]？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
hide: true
hidefromtoc: true
exl-id: 6b0175b1-0eee-498d-8a08-513cf6695114
source-git-commit: 16a7c11e8b9b1a08b1e467519f997d0b05e47529
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 21%

---

# [!UICONTROL Catalog Search]

此 [!UICONTROL Catalog Search] 頁面位置 [!DNL Adobe Recommendations] 可協助您在目錄中尋找產品或內容。 您可以在此頁面上執行的最基本工作是搜尋專案。 此外，您可以變更環境、篩選多面、修改表格中的欄、新增搜尋多面等等。

目錄是指您的整個產品集 (實體)。您的目錄可以包含許多系列，好讓您以邏輯區間組織產品。

## 存取 [!UICONTROL Catalog Search]

若要存取 [!UICONTROL Catalog Search] 頁面，按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

![目錄搜尋頁面](/help/main/c-recommendations/c-products/assets/catalog-search-new.png)

## 執行簡單搜尋

1. 在「 」中輸入搜尋字詞 **[!UICONTROL Search In]** 欄位。

1. （選擇性）您可以從選項功能表中選取搜尋選項(按一下 [!UICONTROL Search In] 欄位。

   搜尋選項包含下列項目:

   * ID
   * 名稱
   * 訊息

1. 捲動搜尋結果中的專案以檢視縮圖和其他產品資訊。

   >[!NOTE]
   >
   > 當您針對包含某數值的自訂屬性執行目錄搜尋時，結果會將自訂屬性視為字串類型，而非數值。
   >
   >目前沒有可讓您變更屬性型別的功能。 若要變更，[開啟客戶問題](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，指出需要將類型從字串變更為數值的屬性。

   您也可以使用篩選器來尋找所需的產品。 例如，按一下 **[!UICONTROL Show Filters]** 圖示( ![顯示篩選器圖示](/help/main/c-recommendations/c-products/assets/icon-show-filters.png) )，展開 [!UICONTROL Collections] Facet，然後選取一或多個集合，目錄會顯示屬於所選集合的所有產品。

<!-- ### Perform an advanced search {#advanced-search}

You can use [!UICONTROL Advanced Search] to further refine your search results or to save your search results as a [collection](/help/main/c-recommendations/c-products/collections.md) or [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Click the **[!UICONTROL Advanced Search]** link.

   ![Advanced Search page](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use the drop-down lists to specify the parameter, operator, and values for your search.

1. (Optional) Click **[!UICONTROL Add Rule]** to add an additional search rule.

   Each additional search rule is joined with the AND operator.

1. Click **[!UICONTROL Search]**.

1. (Optional) Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   For more information, see [Create a collection or exclusion based on Advanced Search](#save-as) below.-->

## 檢視專案的詳細資訊

您可以檢視個別專案的詳細資料，包括ID、名稱、訊息、類別等，只要檢視其詳細資料。

1. 按一下搜尋結果中的專案以檢視其詳細資訊。

## 從目錄中移除專案

1. 按一下搜尋結果中的專案以檢視其詳細資訊。

1. 按一下 **[!UICONTROL Remove from Catalog]**。

1. 確認您要移除專案。

該專案的所有相關資訊都會從目錄索引中移除。 只有當專案再次新增到資料摘要中時，它才會包含在您的目錄中。 已刪除的專案必須從摘要個別刪除。

## 重新整理目錄

上傳第一個摘要時，系統會自動建立目錄的索引，並根據 [指定的排程](/help/main/c-recommendations/c-products/feeds.md#steps).

透過摘要檔案、API 或 mbox 更新收到更新時，目錄會自動重新整理。更新通常會在一小時內完成。 如果正在進行更新，會顯示最新更新的開始時間。如果沒有任何正在進行的更新，會顯示最新更新的開始和結束時間。

<!-- ## Create a collection or exclusion based on Advanced Search {#save-as}

You can create [collections](/help/main/c-recommendations/c-products/collections.md) or [exclusions](/help/main/c-recommendations/c-products/exclusions.md) using [!UICONTROL Advanced Search] on the [!UICONTROL Catalog Search] page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Perform an [advanced search](#advanced-search).

1. Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections or exclusions based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. Exclusions are handled in a similar fashion.-->

## 變更環境

[環境](/help/main/administrating-target/environments.md) 可讓您組織網站和生產前環境，以便輕鬆管理和分隔報表。

1. 按一下顯示篩選器圖示( ![顯示篩選器圖示](/help/main/c-recommendations/c-products/assets/icon-show-filters.png) )。

1. 從中選擇所需的環境 **[!UICONTROL Environment]** 下拉式清單。

<!-- ## Modify the Catalog Search page (filters and columns)

You can temporarily modify the available filters and columns on the [!UICONTROL Catalog Search] page for the current session.

### Modify filters

You can add additional filter facets to the [!UICONTROL Catalog Search] page.

1. In the **[!UICONTROL Filters]** panel, click **[!UICONTROL Modify]**.

   ![Modify filters link](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Select the desired search facets (ID, name, message, etc.), then click **[!UICONTROL Save]**.

   ![Add filters](/help/main/c-recommendations/c-products/assets/add-filters.png)

Keep in mind that the additional filter facets are available in the current session only.-->

## 修改欄

您可以暫時修改上作用中的欄 [!UICONTROL Catalog Search] 頁面。

1. 按一下 **[!UICONTROL Customize Table]** 圖示(  ![自訂表格圖示](/help/main/c-recommendations/c-products/assets/icon-customize-table.png) )。

1. 選取或取消選取想要顯示或隱藏的欄。

請記住，您所做的任何變更只會套用至目前的作業階段。

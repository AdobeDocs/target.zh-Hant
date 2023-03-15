---
keywords: 目錄搜尋；目錄；搜尋；排除；集合；篩選
description: 了解如何使用Recommendations目錄搜尋來尋找產品或內容、建立集合或排除項目、從目錄中移除項目等。
title: 如何使用Recommendations目錄搜尋？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 23%

---

# 目錄搜尋

此 [!UICONTROL 目錄搜尋] 頁面 [!DNL Adobe Recommendations] 可協助您找出目錄中的產品或內容。 在此頁面上，您可執行的最基本任務是搜尋項目。 此外，您可以變更環境、將搜尋結果儲存至集合或排除項目、新增篩選Facet、修改表格中的欄、新增搜尋Facet等。

目錄是指您的整個產品集 (實體)。您的目錄可包含許多集合，這是在邏輯貯體中組織產品的方法。

## 存取目錄搜尋

若要存取 [!UICONTROL 目錄搜尋] 頁面，按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 目錄搜尋]**.

![目錄搜尋頁面](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## 搜尋項目

您可以使用簡單搜尋或進階搜尋來尋找目錄中的項目。

### 執行簡單的搜索

1. 在 **[!UICONTROL 搜尋產品]** 欄位。

1. （可選）您可以從選項功能表中選取搜尋選項，以縮小搜尋欄位中按向下箭頭時顯示的範圍。

   ![searchproducts功能表影像](assets/searchproductsmenu.png)

   搜尋選項包含下列項目:

   * ALL  — 使用OR邏輯搜尋所有其他搜尋條件。
   * 名稱
   * 品牌
   * 類別
   * ID
   * 訊息

1. 您現在可以捲動搜尋結果中的項目，以檢視縮圖和其他產品資訊。

   下圖顯示使用「全部」選項的「腳踏車」結果。

   ![腳踏車目錄搜尋](/help/main/c-recommendations/c-products/assets/bike-results.png)

   「產品」旁顯示的數字代表在所指定環境中可用的總數之中，符合搜尋詞語的產品數量。

   請注意，您可以使用搜尋自動完成功能。 在下圖中，輸入「bik」會傳回包含「bike」一字的所有產品。

   ![搜索自動完成](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >當您針對包含某數值的自訂屬性執行目錄搜尋時，結果會將自訂屬性視為字串類型，而非數值。
   >
   >目前沒有可讓您變更屬性類型的功能。 若要變更，[開啟客戶問題](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，指出需要將類型從字串變更為數值的屬性。

1. 您也可以使用篩選器來尋找所需的產品。 在下列範例中，展開 [!UICONTROL 集合] 刻面，並選取「腳踏車工具」，目錄顯示中的所有腳踏車工具。

   ![腳踏車工具](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. 您可以輸入搜尋詞，例如&quot;chain&quot;，在結果清單中進一步搜尋。

   ![搜索鏈](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### 執行進階搜尋 {#advanced-search}

您可以使用 [!UICONTROL 進階搜尋] 以進一步細化搜尋結果或將搜尋結果儲存為 [集合](/help/main/c-recommendations/c-products/collections.md) 或 [排除](/help/main/c-recommendations/c-products/exclusions.md).

1. 按一下 **[!UICONTROL 進階搜尋]** 連結。

   ![進階搜尋頁面](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. 使用下拉式清單來指定搜尋的參數、運算子和值。

1. （選用）按一下 **[!UICONTROL 新增規則]** 以新增其他搜尋規則。

   每個額外的搜尋規則都以AND運算子連結。

1. 按一下&#x200B;**[!UICONTROL 搜尋]**。

1. （選用）按一下 **[!UICONTROL 另存新檔]**，然後按一下 **[!UICONTROL 集合]** 或 **[!UICONTROL 排除]**.

   ![另存新檔選項](/help/main/c-recommendations/c-products/assets/save-as.png)

   如需詳細資訊，請參閱 [根據進階搜尋建立集合或排除項目](#save-as) 下方。

## 查看項的詳細資訊

您可以檢視個別項目的詳細資訊，包括ID、名稱、訊息、類別等。

1. 按一下搜尋結果中的項目以檢視其詳細資料。

   ![產品詳細資訊](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## 從目錄中移除項目

1. 按一下搜尋結果中的項目以檢視其詳細資料。

1. 按一下 **[!UICONTROL 從目錄中刪除]**.

1. 確認您要移除項目。

該項目的所有資訊都將從目錄索引中刪除。 只有在資料摘要中再次新增項目時，該項目才會包含在目錄中。 已刪除的項目必須從摘要中個別刪除。

## 重新整理目錄

目錄的索引會在您上傳第一個摘要時自動建立，並根據 [指定排程](/help/main/c-recommendations/c-products/feeds.md#steps).

透過摘要檔案、API 或 mbox 更新收到更新時，目錄會自動重新整理。更新通常會在一小時內完成。如果正在進行更新，會顯示最新更新的開始時間。如果沒有任何正在進行的更新，會顯示最新更新的開始和結束時間。

## 根據進階搜尋建立集合或排除項目 {#save-as}

您可以使用目錄搜尋頁面上的進階搜尋 ([](/help/main/c-recommendations/c-products/collections.md)[](/help/main/c-recommendations/c-products/exclusions.md)Recommendations[!UICONTROL  > ]目錄搜尋[!UICONTROL  > ]進階搜尋[!UICONTROL )，以建立]集合[!UICONTROL 或]排除項目。

1. 執行 [進階搜尋](#advanced-search).

1. 按一下 **[!UICONTROL 另存新檔]**，然後按一下 **[!UICONTROL 集合]** 或 **[!UICONTROL 排除]**.

   ![另存新檔選項](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >此 [!UICONTROL 進階搜尋] 功能不區分大小寫；不過，傳送時傳回的產品會以區分大小寫的搜尋為基礎。 此不相符的情況可能導致混淆。根據使用的結果建立集合或排除時，請務必考慮區分大小寫 [!UICONTROL 進階搜尋] 功能。 例如，如果您執行 &quot;Holiday&quot; 的搜尋，初始的搜尋清單結果會包含 &quot;Holiday&quot; 和 &quot;holiday&quot;。如果您之後建立一個目錄，目的要傳回包含 &quot;holiday&quot; 的產品，則只會傳回包含 &quot;holiday&quot; 的產品。不會傳回包含 &quot;Holiday&quot; 的產品。排除項目也是以類似的方式處理。

## 變更環境

[環境](/help/main/administrating-target/environments.md) 可讓您組織網站和生產前環境，以方便管理和分開報告。

1. 按一下「環境」連結。

   ![環境連結](/help/main/c-recommendations/c-products/assets/environment.png)

1. 選取所需的環境。

## 修改「目錄搜尋」頁面（篩選器和欄）

您可以暫時修改 [!UICONTROL 目錄搜尋] 頁面。

### 修改篩選器

您可以新增其他篩選Facet至 [!UICONTROL 目錄搜尋] 頁面。

1. 在 **[!UICONTROL 篩選器]** 面板，按一下 **[!UICONTROL 修改]**.

   ![修改篩選器連結](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. 選取所需的搜尋刻面（ID、名稱、訊息等），然後按一下 **[!UICONTROL 儲存]**.

   ![新增篩選條件](/help/main/c-recommendations/c-products/assets/add-filters.png)

請記住，其他篩選刻面僅適用於目前的工作階段。

### 修改欄

您可以暫時修改 [!UICONTROL 目錄搜尋] 頁面。

1. 按一下 **[!UICONTROL 欄]** 連結。

   ![欄選項](/help/main/c-recommendations/c-products/assets/columns.png)

1. （條件性）若要重新排序作用中欄的順序，請拖放 **[!UICONTROL 作用中欄]** 區段。

1. （條件性）從 **[!UICONTROL 作用中欄]** 到 **[!UICONTROL 非作用中欄]** （反之亦然）。

   您也可以按一下您要從「使用中」區段移至「非使用中」區段之欄旁的刪除圖示(x)。

請記得，您所做的任何變更都只會套用至目前的工作階段。

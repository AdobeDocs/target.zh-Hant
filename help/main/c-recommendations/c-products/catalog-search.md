---
keywords: 目錄搜索；目錄；搜索；排除；收集；篩選；catalog search;catalog;search;exclusion;collection;filter
description: 瞭解如何使用Recommendations目錄搜索查找產品或內容、建立收藏或排除、從目錄中刪除項目等。
title: 如何使用Recommendations目錄搜索？
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 22%

---

# ![高級](/help/main/assets/premium.png) 目錄搜索

的 [!UICONTROL 目錄搜索] 頁面 [!DNL Adobe Recommendations] 幫助您查找目錄中的產品或內容。 在此頁上可以執行的最基本任務是搜索項目。 此外，您還可以更改環境、將搜索結果保存到集合或排除項、添加篩選器小平面、修改表格中的列、添加新的搜索小平面等。

目錄是指您的整個產品集 (實體)。您的目錄可以包含許多集合，這是一種在邏輯儲存桶中組織產品的方法。

## 訪問目錄搜索

訪問 [!UICONTROL 目錄搜索] 的 **[!UICONTROL Recommendations]** > **[!UICONTROL 目錄搜索]**。

![「目錄搜索」頁](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## 搜索項

您可以使用簡單搜索或高級搜索來查找目錄中的項目。

### 執行簡單搜索

1. 在 **[!UICONTROL 搜索產品]** 的子菜單。

1. （可選）通過從選項菜單中選擇搜索選項來細化搜索，當按一下搜索欄位中的向下箭頭時，將顯示該選項。

   ![](assets/searchproductsmenu.png)

   搜尋選項包含下列項目:

   * ALL  — 使用OR邏輯在所有其他搜索條件中搜索。
   * 名稱
   * 品牌
   * 類別
   * ID
   * 訊息

1. 現在，您可以滾動搜索結果中的項目，以查看縮略圖和其他產品資訊。

   下圖顯示了使用「全部」(All)選項的「腳踏車」結果。

   ![搜索腳踏車目錄](/help/main/c-recommendations/c-products/assets/bike-results.png)

   「產品」旁顯示的數字代表在所指定環境中可用的總數之中，符合搜尋詞語的產品數量。

   請注意，您可以使用搜索自動完成功能。 在下圖中，鍵入&quot;bik&quot;將返回包含&quot;bike&quot;一詞的所有產品。

   ![搜索自動完成](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >當您針對包含某數值的自訂屬性執行目錄搜尋時，結果會將自訂屬性視為字串類型，而非數值。
   >
   >當前，沒有可用功能可更改屬性類型。 若要變更，[開啟客戶問題](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，指出需要將類型從字串變更為數值的屬性。

1. 您還可以使用過濾器來查找所需的產品。 在以下示例中，通過展開 [!UICONTROL 集合] facet並選擇「Bike Tools」（腳踏車工具），目錄顯示中的所有腳踏車工具。

   ![腳踏車工具](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. 您可以通過輸入搜索項（例如&quot;chain&quot;）在結果清單中進一步搜索。

   ![搜索鏈](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### 執行高級搜索 {#advanced-search}

您可以使用 [!UICONTROL 高級搜索] 以進一步細化搜索結果或將搜索結果另存為 [集合](/help/main/c-recommendations/c-products/collections.md) 或 [排除](/help/main/c-recommendations/c-products/exclusions.md)。

1. 按一下 **[!UICONTROL 高級搜索]** 的子菜單。

   ![「高級搜索」頁](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. 使用下拉清單指定搜索的參數、運算子和值。

1. （可選）按一下 **[!UICONTROL 添加規則]** 添加其他搜索規則。

   每個附加搜索規則都與AND運算子相聯。

1. 按一下&#x200B;**[!UICONTROL 搜尋]**。

1. （可選）按一下 **[!UICONTROL 另存為]**，然後按一下 **[!UICONTROL 集合]** 或 **[!UICONTROL 排除]**。

   ![另存為選項](/help/main/c-recommendations/c-products/assets/save-as.png)

   有關詳細資訊，請參見 [基於高級搜索建立集合或排除](#save-as) 下。

## 查看項的詳細資訊

您可以通過查看單個項目的詳細資訊來查看其詳細資訊，包括ID、名稱、消息、類別等。

1. 按一下搜索結果中的項以查看其詳細資訊。

   ![產品詳細資訊](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## 從目錄中刪除項目

1. 按一下搜索結果中的項以查看其詳細資訊。

1. 按一下 **[!UICONTROL 從目錄中刪除]**。

1. 確認要刪除該項目。

有關該項的所有資訊都將從目錄索引中刪除。 僅當在資料源中再次添加該項目時，該項目才會包含在目錄中。 必須從源中單獨刪除已刪除的項。

## 刷新目錄

在上載第一個源時，將自動建立目錄索引，並根據 [指定計畫](/help/main/c-recommendations/c-products/feeds.md#steps)。

透過摘要檔案、API 或 mbox 更新收到更新時，目錄會自動重新整理。更新通常會在一小時內完成。如果正在進行更新，會顯示最新更新的開始時間。如果沒有任何正在進行的更新，會顯示最新更新的開始和結束時間。

## 根據進階搜尋建立集合或排除項目 {#save-as}

您可以使用目錄搜尋頁面上的進階搜尋 ([](/help/main/c-recommendations/c-products/collections.md)[](/help/main/c-recommendations/c-products/exclusions.md)Recommendations[!UICONTROL  > ]目錄搜尋[!UICONTROL  > ]進階搜尋[!UICONTROL )，以建立]集合[!UICONTROL 或]排除項目。

1. 執行 [高級搜索](#advanced-search)。

1. 按一下 **[!UICONTROL 另存為]**，然後按一下 **[!UICONTROL 集合]** 或 **[!UICONTROL 排除]**。

   ![另存為選項](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >的 [!UICONTROL 高級搜索] 功能不區分大小寫；但是，在交付時返回的產品基於區分大小寫的搜索。 此不相符的情況可能導致混淆。確保在使用 [!UICONTROL 高級搜索] 功能。 例如，如果您執行 &quot;Holiday&quot; 的搜尋，初始的搜尋清單結果會包含 &quot;Holiday&quot; 和 &quot;holiday&quot;。如果您之後建立一個目錄，目的要傳回包含 &quot;holiday&quot; 的產品，則只會傳回包含 &quot;holiday&quot; 的產品。不會傳回包含 &quot;Holiday&quot; 的產品。排除項目也是以類似的方式處理。

## 更改環境

[環境](/help/main/administrating-target/environments.md) 讓您組織站點和生產前環境，以便於管理和分開報告。

1. 按一下「Environment（環境）」連結。

   ![環境連結](/help/main/c-recommendations/c-products/assets/environment.png)

1. 選擇所需的環境。

## 修改「目錄搜索」頁（篩選器和列）

可以臨時修改上的可用篩選器和列 [!UICONTROL 目錄搜索] 的子菜單。

### 修改篩選器

可向 [!UICONTROL 目錄搜索] 的子菜單。

1. 在 **[!UICONTROL 篩選器]** 面板，按一下 **[!UICONTROL 修改]**。

   ![修改篩選器連結](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. 選擇所需的搜索小平面（ID、名稱、消息等），然後按一下 **[!UICONTROL 保存]**。

   ![新增篩選條件](/help/main/c-recommendations/c-products/assets/add-filters.png)

請記住，附加的過濾器小平面僅在當前會話中可用。

### 修改列

可以臨時修改 [!UICONTROL 目錄搜索] 的子菜單。

1. 按一下 **[!UICONTROL 列]** 的子菜單。

   ![列選項](/help/main/c-recommendations/c-products/assets/columns.png)

1. （條件）要重新排序活動列的順序，請拖放 **[!UICONTROL 活動列]** 按鈕。

1. （條件）從 **[!UICONTROL 活動列]** 到 **[!UICONTROL 非活動列]** （反之亦然）。

   也可以按一下要從活動部分移動到非活動部分的列旁邊的刪除表徵圖(x)。

請記住，所做的任何更改都只應用於當前會話。

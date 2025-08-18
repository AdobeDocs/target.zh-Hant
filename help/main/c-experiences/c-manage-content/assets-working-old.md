---
keywords: 內容資料庫; 資產; 注釋; 複製; 刪除資產; 下載資產; 編輯內容; 共用卡片; 檢視內容屬性
description: 瞭解如何在Adobe [!DNL Target] 選件資料庫中管理程式碼和影像選件。 瞭解如何檢視優惠方案的詳細資訊，以及如何編輯、複製、移動或刪除優惠方案。
title: 如何使用優惠資料庫中的內容？
feature: Experiences and Offers
exl-id: 2668ba68-29c8-4c3f-bebc-ba62760a8a61
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 32%

---

# 使用資產庫中的內容

關於您可以在[!DNL Adobe Target]的內容資料庫中執行之工作的資訊，包括註釋、複製、刪除、下載、編輯、共用和檢視屬性。

1. 按一下「**[!UICONTROL Offers]** > **[!UICONTROL Code Offers]**」或「**[!UICONTROL Image Offers]**」。

   ![代碼選件和影像選件索引標籤](/help/main/c-experiences/c-manage-content/assets/offers-both.png)

   如需搜尋產品建議資料庫和建立智慧型集合的相關資訊，請參閱[篩選與搜尋內容](/help/main/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276)。

1. （選用）在[!UICONTROL Card View]與[!UICONTROL List View]之間切換，按一下內容程式庫右上角的[!UICONTROL Card View]圖示或[!UICONTROL List View]圖示。 您也可以在檢視[!UICONTROL View Settings]時使用[!UICONTROL List View]進一步設定資料行。

   下圖顯示檢視[!UICONTROL List View]時可用的選項：

   ![清單檢視選項](/help/main/c-experiences/c-manage-content/assets/view-settings-options.png)

1. 按照下列各節的說明，執行所需的動作：

## 代碼產品建議選項

檢視[!UICONTROL Code Offers]頁面時，您可以暫留在選件或資料夾上，然後選取適當的圖示，對專案執行下列動作。

![代碼選件索引標籤上的暫留圖示](/help/main/c-experiences/c-manage-content/assets/code-offers-hover-icons.png)

* **資訊**：檢視選件的資訊。
* **編輯**：編輯資料夾或選件。
* **複製**：複製選件。 複製並編輯選件可讓您輕鬆建立類似的新選件。
* **移動**：按一下「移動」圖示，導覽至您要移動選件或資料夾的位置，然後按一下「**[!UICONTROL Drop]**」圖示。 例如，您可以將一或多個資料夾移至另一個資料夾，以建立子資料夾。 按一下[!UICONTROL Clear Selection]以取消選取您選取的選件或資料夾。
* **刪除**：刪除選件或資料夾。 請參閱[刪除專案](#delete)時的考量事項。

## 影像產品建議選項

檢視[!UICONTROL Image Offers]頁面時，您可以暫留在選件或資料夾上，然後選取適當的圖示，對專案執行下列動作。

下圖顯示檢視[!UICONTROL Card View]時的暫留圖示。

在卡片檢視中，![在「影像選件」索引標籤上暫留圖示](/help/main/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

下圖顯示檢視[!UICONTROL List View]時的暫留圖示。 若要顯示圖示，請按一下清單中的專案。

在清單檢視中，![在[影像選件]索引標籤上暫留圖示](/help/main/c-experiences/c-manage-content/assets/list-view-hover.png)

* **選取**：選取要執行下列動作的一或多個資料夾：

   * 下載
   * 複製
   * 移動
   * 刪除（請參閱[刪除專案](#delete)時的考量事項。）

  選取要執行下列動作的一或多個影像選件：

   * 共用
   * 下載
   * 檢視屬性
   * 編輯
   * 注釋
   * 移動

* **下載**：下載影像選件或資料夾及其內容。
* **檢視屬性**：檢視專案的屬性。 請務必按一下「[!UICONTROL Basic]」標籤和「[!UICONTROL Advanced]」標籤，以檢視所有可用的資訊。 按一下屬性頁面上的「鉛筆」圖示，可編輯屬性和新增更多資訊。您可以新增中繼資料資訊、發佈狀態和授權資料。
* **其他動作**：在[!UICONTROL Card View]中顯示其他選項。
* **編輯**：編輯資料夾或選件。
* **註釋**：新增備註至資產。 按一下資產，然後選取您要注釋的區域並輸入您的備註。
* **複製**：複製選件。 複製並編輯選件可讓您輕鬆建立類似的新選件。

## 刪除專案時的注意事項 {#delete}

* 您可以刪除包含任何資產和子資料夾數量的整個資料夾。 Target UI 與 Adobe Experience Cloud 資產 UI 皆提供此功能。
* 如果您刪除含有大量影像的資料夾，在幕後執行的程式可能需要一段時間（幾分鐘），然後UI才會重新整理為顯示最終狀態。 需要的時間取決於影像數量，而非影像大小。理想的預估情況是，2,000 個影像需要十分鐘。數分鐘之後，您可以繼續進行其他工作並檢查最終狀態以確認刪除。
* 您可以刪除影像產品建議資料庫中的非空白資料夾。如果沒有任何活動參照資料夾中的所有影像，則會刪除整個資料夾及其內容。如果有任何活動參照了資料夾中的某些影像，則會刪除所有未參照的影像，但會保留包含這些影像的參照影像和資料夾。

## 訓練影片：內容存放庫![Overview badge](/help/main/assets/overview.png)

此影片包括關於管理內容的資訊。(4:56)

* [Experience Cloud 資產資料庫](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html?lang=zh-Hant) 與 Target 內容庫之間的連線
* 自訂 HTML 產品建議
* 可視化體驗撰寫器中的自訂 HTML 產品建議

>[!VIDEO](https://video.tv.adobe.com/v/17387)

---
keywords: 內容資料庫; 資產; 注釋; 複製; 刪除資產; 下載資產; 編輯內容; 共用卡片; 檢視內容屬性
description: 瞭解如何在Adobe [!DNL Target] 選件程式庫中管理程式碼和影像選件。 瞭解如何檢視選件的詳細資訊，以及如何編輯、複製、移動或刪除選件。
title: 如何處理選件程式庫中的內容？
feature: 體驗與優惠
exl-id: 2668ba68-29c8-4c3f-bebc-ba62760a8a61
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 36%

---

# 在資產庫中處理內容

有關您可在[!DNL Adobe Target]內容庫中對資產執行的任務的資訊，包括註解、複製、刪除、下載、編輯、共用和檢視屬性。

1. 按一下「**[!UICONTROL 選件]** > **[!UICONTROL 程式碼選件]**&#x200B;或&#x200B;**[!UICONTROL 影像選件]**」。

   ![程式碼選件和影像選件標籤](/help/c-experiences/c-manage-content/assets/offers-both.png)

   如需搜尋選件資料庫和建立智慧型集合的相關資訊，請參閱[篩選與搜尋內容](/help/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276)。

1. （可選）在[!UICONTROL 卡片檢視]和[!UICONTROL 清單檢視]之間切換，按一下內容庫右上角的[!UICONTROL 卡片檢視]圖示或[!UICONTROL 清單檢視]圖示。 您也可以使用[!UICONTROL 檢視設定]，在檢視[!UICONTROL 清單檢視]時進一步設定欄。

   下圖顯示了查看[!UICONTROL 清單視圖]時的可用選項：

   ![清單檢視選項](/help/c-experiences/c-manage-content/assets/view-settings-options.png)

1. 執行所需動作，如下列章節所述：

## 代碼選件選項

在檢視「代碼選件[!UICONTROL 」頁面時，您可以將滑鼠指標暫留在選件或資料夾上，然後選取適當的圖示，對項目執行下列動作。]

![「程式碼選件」標籤上的暫留圖示](/help/c-experiences/c-manage-content/assets/code-offers-hover-icons.png)

* **資訊**:檢視選件的資訊。
* **編輯**:編輯資料夾或選件。
* **複製**:複製選件。複製並編輯選件可讓您輕鬆建立類似的新選件。
* **移動**:按一下「移動」圖示，導覽至您要將選件或資料夾移至的位置，然後按一下 **** Dropicon。例如，您可以將一個或多個資料夾移動到另一個資料夾以建立子資料夾。 按一下「清除選取範圍」，以取消選取您選取的選件或資料夾。
* **刪除**:刪除選件或資料夾。請參閱[刪除項目時的注意事項](#delete)。

## 影像選件選項

在檢視「影像選件」[!UICONTROL 頁面時，您可以將滑鼠指標暫留在選件或資料夾上，然後選取適當的圖示，對項目執行下列動作。]

下圖顯示了在查看[!UICONTROL 卡片視圖]時的懸停錶徵圖。

![在「卡片檢視」中時，將滑鼠暫留在「影像選件」標籤上的圖示](/help/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

下圖顯示了查看[!UICONTROL 清單視圖]時的懸停錶徵圖。 若要顯示圖示，請按一下清單中的項目。

![在「清單檢視」中時，「影像選件」標籤上的暫留圖示](/help/c-experiences/c-manage-content/assets/list-view-hover.png)

* **選擇**:選擇要在其上執行以下操作的一個或多個資料夾：

   * 下載
   * 複製
   * 移動
   * 刪除（刪除項目](#delete)時請參閱[注意事項。）

   選取要執行下列動作的一或多個影像選件：

   * 共用
   * 下載
   * 檢視屬性
   * 編輯
   * 注釋
   * 移動


* **下載**:下載影像選件或資料夾及其內容。
* **檢視屬性**:檢視項目的屬性。請務必按一下「[!UICONTROL 基本]」標籤和「[!UICONTROL 進階]」標籤，以檢視所有可用資訊。 按一下屬性頁面上的「鉛筆」圖示，可編輯屬性和新增更多資訊。您可以新增中繼資料資訊、發佈狀態和授權資料。
* **更多動作**:在卡片檢視中顯示其 [!UICONTROL 他選項]。
* **編輯**:編輯資料夾或選件。
* **註解**:新增附註至資產。按一下資產，然後選取您要注釋的區域並輸入您的備註。
* **複製**:複製選件。複製並編輯選件可讓您輕鬆建立類似的新選件。

## 刪除項目{#delete}時的注意事項

* 您可以刪除包含任何資產和子資料夾數量的整個資料夾。Target UI 與 Adobe Experience Cloud 資產 UI 皆提供此功能。
* 如果您刪除含有大量影像的資料夾，在幕後執行的程序可能需要一段時間 (幾分鐘)，然後 UI 才會重新整理為顯示最終狀態。需要的時間取決於影像數量，而非影像大小。理想的預估情況是，2,000 個影像需要十分鐘。數分鐘之後，您可以繼續進行其他工作並檢查最終狀態以確認刪除。
* 您可以刪除影像選件資料庫中的非空白資料夾。如果沒有任何活動參照資料夾中的所有影像，則會刪除整個資料夾及其內容。如果有任何活動參照了資料夾中的某些影像，則會刪除所有未參照的影像，但會保留包含這些影像的參照影像和資料夾。

## 訓練影片：內容儲存庫![概述徽章](/help/assets/overview.png)

此影片包括關於管理內容的資訊。(4:56)

* [Experience Cloud 資產資料庫](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) 與 Target 內容庫之間的連線
* 自訂 HTML 選件
* 可視化體驗撰寫器中的自訂 HTML 選件

>[!VIDEO](https://video.tv.adobe.com/v/17387)

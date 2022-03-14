---
keywords: 內容資料庫; 資產; 注釋; 複製; 刪除資產; 下載資產; 編輯內容; 共用卡片; 檢視內容屬性
description: 瞭解如何管理Adobe中提供的代碼和映像 [!DNL Target] 提供庫。 瞭解如何查看聘用的詳細資訊以及如何編輯、複製、移動或刪除聘用。
title: 如何處理優惠庫中的內容？
feature: Experiences and Offers
exl-id: 2668ba68-29c8-4c3f-bebc-ba62760a8a61
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 37%

---

# 在資產庫中處理內容

有關您可以對「內容庫」中的資產執行的任務的資訊 [!DNL Adobe Target] 包括注釋、複製、刪除、下載、編輯、共用和查看屬性。

1. 按一下 **[!UICONTROL 優惠]** > **[!UICONTROL 代碼優惠]** 或 **[!UICONTROL 映像提供]**。

   ![代碼優惠和映像優惠頁籤](/help/main/c-experiences/c-manage-content/assets/offers-both.png)

   如需搜尋選件資料庫和建立智慧型集合的相關資訊，請參閱[篩選與搜尋內容](/help/main/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276)。

1. （可選）在 [!UICONTROL 卡視圖] 和 [!UICONTROL 清單視圖]，按一下 [!UICONTROL 卡視圖] 表徵圖 [!UICONTROL 清單視圖] 表徵圖。 您還可以使用 [!UICONTROL 查看設定] 在查看 [!UICONTROL 清單視圖]。

   下圖顯示了查看 [!UICONTROL 清單視圖]:

   ![清單視圖選項](/help/main/c-experiences/c-manage-content/assets/view-settings-options.png)

1. 執行所需操作，如以下各節所述：

## 代碼選件選項

查看 [!UICONTROL 代碼優惠] 頁面中，您可以通過將滑鼠懸停在優惠或資料夾上，然後選擇相應的表徵圖對項目執行以下操作。

![「代碼提供」頁籤上的懸停錶徵圖](/help/main/c-experiences/c-manage-content/assets/code-offers-hover-icons.png)

* **資訊**:查看優惠資訊。
* **編輯**:編輯資料夾或優惠。
* **複製**:收到。 複製並編輯聘用可讓您輕鬆建立類似的新聘用。
* **移動**:按一下「移動」表徵圖，導航到要將優惠或資料夾移到的位置，然後按一下 **[!UICONTROL 刪除]** 表徵圖 例如，可以將一個或多個資料夾移動到另一個資料夾中以建立子資料夾。 按一下 [!UICONTROL 清除選擇] 要取消選擇已選擇的聘用或資料夾，請執行以下操作：
* **刪除**:刪除聘用或資料夾。 請參閱 [刪除項時的注意事項](#delete)。

## 影像選件選項

查看 [!UICONTROL 映像提供] 頁面中，您可以通過將滑鼠懸停在優惠或資料夾上，然後選擇相應的表徵圖對項目執行以下操作。

下圖顯示了查看 [!UICONTROL 卡視圖]。

![在「卡」視圖中時，懸停在「影像提供」頁籤上的表徵圖](/help/main/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

下圖顯示了查看 [!UICONTROL 清單視圖]。 要顯示表徵圖，請按一下清單中的項。

![在「清單視圖」中時，懸停在「影像提供」頁籤上的表徵圖](/help/main/c-experiences/c-manage-content/assets/list-view-hover.png)

* **選擇**:選擇一個或多個資料夾，以在其上執行以下操作：

   * 下載
   * 複製
   * 移動
   * 刪除(請參閱 [刪除項時的注意事項](#delete)。)

   選擇一個或多個映像提供，以執行以下操作：

   * 共用
   * 下載
   * 檢視屬性
   * 編輯
   * 注釋
   * 移動


* **下載**:下載影像提供或資料夾及其內容。
* **查看屬性**:查看項的屬性。 確保按一下 [!UICONTROL 基本] 頁籤 [!UICONTROL 高級] 頁籤。 按一下屬性頁面上的「鉛筆」圖示，可編輯屬性和新增更多資訊。您可以新增中繼資料資訊、發佈狀態和授權資料。
* **更多操作**:在中時顯示其他選項 [!UICONTROL 卡視圖]。
* **編輯**:編輯資料夾或優惠。
* **注釋**:向資產添加附註。 按一下資產，然後選取您要注釋的區域並輸入您的備註。
* **複製**:收到。 複製並編輯聘用可讓您輕鬆建立類似的新聘用。

## 刪除項時的注意事項 {#delete}

* 您可以刪除包含任何資產和子資料夾數量的整個資料夾。Target UI 與 Adobe Experience Cloud 資產 UI 皆提供此功能。
* 如果您刪除含有大量影像的資料夾，在幕後執行的程序可能需要一段時間 (幾分鐘)，然後 UI 才會重新整理為顯示最終狀態。需要的時間取決於影像數量，而非影像大小。理想的預估情況是，2,000 個影像需要十分鐘。數分鐘之後，您可以繼續進行其他工作並檢查最終狀態以確認刪除。
* 您可以刪除影像選件資料庫中的非空白資料夾。如果沒有任何活動參照資料夾中的所有影像，則會刪除整個資料夾及其內容。如果有任何活動參照了資料夾中的某些影像，則會刪除所有未參照的影像，但會保留包含這些影像的參照影像和資料夾。

## 培訓視頻：內容儲存庫 ![概述徽章](/help/main/assets/overview.png)

此影片包括關於管理內容的資訊。(4:56)

* [Experience Cloud 資產資料庫](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) 與 Target 內容庫之間的連線
* 自訂 HTML 選件
* 可視化體驗撰寫器中的自訂 HTML 選件

>[!VIDEO](https://video.tv.adobe.com/v/17387)

---
keywords: 內容; 資產; 管理內容; 選件; 管理資產; 進入選擇模式; 選擇模式
description: 了解如何使用Adobe Target中的優惠方案資料庫來管理程式碼和影像優惠方案。
title: 如何管理程式碼和影像選件？
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 37%

---

# 選件

使用 [!UICONTROL 選件] 程式庫 [!DNL Adobe Target] 來管理程式碼選件和影像選件內容。

1. 按一下&#x200B;**[!UICONTROL 「選件」]**&#x200B;以開啟資料庫。

   此資料庫包含已透過 [!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] (AMS) 和 API 來設定的選件。在 [!DNL Target Classic] 或其他解決方案中建立的選件，都可以在 [!DNL Target Standard/Premium] 中編輯。

   此 [!UICONTROL 選件] 頁面右側有兩個標籤： [!UICONTROL 代碼選件] 和 [!UICONTROL 影像選件] 可讓您依類型檢視選件。

   ![顯示「代碼選件」和「影像選件」索引標籤的「選件」頁面](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. （選用）按一下 **[!UICONTROL 類型]** 下拉式清單，依類型篩選選件(HTML選件、 [體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md), [遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)，和 [資料夾](/help/main/c-experiences/c-manage-content/create-content-folder.md))。

   ![offers_filter影像](assets/offers_filter.png)

1. （選用）按一下 **[!UICONTROL 來源]** 下拉式清單，依來源篩選選件(Adobe Target、Adobe Target Classic和Adobe Experience Manager)。

1. （選用）將滑鼠暫留在 [!UICONTROL 代碼選件] ，然後按一下所需圖示。

   ![代碼選件選項](assets/offer-picker-large.png)

   選項包括:

   * 檢視(如需詳細資訊，請參閱 [檢視選件定義](#section_6B059DD121434E6292CAB393507D010E) 在下面。)
   * 編輯
   * 複製
   * 移動(例如，若要將一或多個項目移入資料夾，請按一下 **[!UICONTROL 移動]** 圖示，按一下所需的資料夾，然後按一下 **[!UICONTROL 拖放]**.)
   * 刪除

   視您的權限而定，您可能不會看到所有選項的圖示。 例如，使用 [!UICONTROL 觀察者] 權限無權使用 [!UICONTROL 複製] 選項。

   如需您可以對選件和資料夾執行之工作的詳細資訊，請參閱 [使用資產資料庫中的內容](/help/main/c-experiences/c-manage-content/assets-working.md).

1. （選用）將滑鼠暫留在 [!UICONTROL 影像選件] ，然後按一下所需圖示。

   ![影像選件選項](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   選項包括:

   * 選擇
   * 下載
   * 檢視屬性
   * 編輯
   * 注釋
   * 複製

   如需您可以對選件和資料夾執行之工作的詳細資訊，請參閱 [使用資產資料庫中的內容](/help/main/c-experiences/c-manage-content/assets-working.md).

## 檢視選件定義 {#section_6B059DD121434E6292CAB393507D010E}

您可以在 [!UICONTROL 選件] 程式庫，而不開啟選件。

例如，將滑鼠暫留在上的選件上，可存取HTML選件的下列選件定義卡片 [!UICONTROL 內容] 清單中，然後按一下資訊圖示：

![offer-card-html影像](assets/offer-card-html.png)

可使用下列資訊:

* 名稱
* 來源
* 類型
* 選件 ID
* 選件路徑
* 上次修改

按一下[!UICONTROL 「選件使用情況」]標籤，即可在每一個選件的定義快顯卡片中，檢視已參考程式碼選件的活動。此功能不適用影像選件。這樣可讓您在編輯選件時，避免影響其他活動。資訊包括 [!UICONTROL 即時活動] 和 [!UICONTROL 非作用中活動].

![offer-card-usage影像](assets/offer-card-usage.png)

以下是「重新導向」選件的選件定義卡片:

![offer-card-redirect image](assets/offer-card-redirect.png)

可使用下列資訊:

* 名稱
* 來源
* 類型
* 選件 ID
* 選件路徑
* 上次修改
* 重新導向 URL
* 包含所有URL參數（開啟或關閉）
* 傳遞mbox工作階段ID（開啟或關閉）

以下是「遠端」選件的選件定義卡片:

![offer-card-remote映像](assets/offer-card-remote.png)

可使用下列資訊:

* 名稱
* 來源
* 類型
* 選件 ID
* 選件路徑
* 上次修改
* 重新導向 URL 類型
* 絕對或相對 URL

## 訓練影片: 內容存放庫 ![總覽徽章](/help/main/assets/overview.png)

此影片包含管理選件的相關資訊。

* [Experience Cloud 資產資料庫](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) 與 Target 內容庫之間的連線
* 自訂 HTML 選件
* 可視化體驗撰寫器中的自訂 HTML 選件

>[!VIDEO](https://video.tv.adobe.com/v/17387)

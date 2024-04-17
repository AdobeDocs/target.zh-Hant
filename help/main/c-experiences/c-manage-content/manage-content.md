---
keywords: 內容; 資產; 管理內容; 選件; 管理資產; 進入選擇模式; 選擇模式
description: 瞭解如何使用Adobe Target中的選件資料庫來管理程式碼和影像選件。
title: 我該如何管理程式碼和影像選件？
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f93e33e91fb7be9c0d1772a2014864b46c1dfe47
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 16%

---

# 選件

使用 [!UICONTROL Offers] 中的資料庫 [!DNL Adobe Target] 以管理您的代碼選件和影像選件內容。

1. 按一下 **[!UICONTROL Offers]** 以開啟程式庫。

   此資料庫包含已透過 [!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] (AMS) 和 API 來設定的選件。在 [!DNL Target Classic] 或其他解決方案中建立的選件，都可以在 [!DNL Target Standard/Premium] 中編輯。

   此 [!UICONTROL Offers] 頁面在右側有兩個索引標籤： [!UICONTROL Code Offers] 和 [!UICONTROL Image Offers] 可讓您依型別檢視優惠方案。

   ![顯示「代碼選件」和「影像選件」索引標籤的選件頁面](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. （可選）按一下 **[!UICONTROL Type]** 下拉式清單，依型別篩選選件(HTML選件、 [體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)， [重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)， [遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)， [JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)、和 [資料夾](/help/main/c-experiences/c-manage-content/create-content-folder.md))。

   ![offers_filter圖片](assets/offers_filter.png)

1. （可選）按一下 **[!UICONTROL Source]** 下拉式清單，依來源(Adobe Target、Adobe Target Classic和Adobe Experience Manager)篩選選件。

1. （選用）將游標移至上所需的選件或資料夾，以執行其他工作 [!UICONTROL Code Offers] 標籤，然後按一下所需的圖示。

   ![代碼選件選項](assets/offer-picker-large.png)

   選項包括:

   * 檢視(如需詳細資訊，請參閱 [檢視選件定義](#section_6B059DD121434E6292CAB393507D010E) 下。)
   * 編輯
   * 複製
   * 移動(例如，若要將一或多個專案移至資料夾，請按一下 **[!UICONTROL Move]** 圖示下，按一下所需的資料夾，然後按一下 **[!UICONTROL Drop]**.)
   * 刪除

   視您的許可權而定，您可能不會看到所有選項的圖示。 例如，使用者具有 [!UICONTROL Observer] 許可權沒有使用 [!UICONTROL Copy] 選項。

   如需您可以在選件和資料夾上執行之工作的詳細資訊，請參閱 [使用資產庫中的內容](/help/main/c-experiences/c-manage-content/assets-working.md).

1. （選用）將游標移至影像選件或資料夾上所需的位置，以執行其他工作。 [!UICONTROL Image Offers] 標籤，然後按一下所需的圖示。

   ![影像選件選項](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   選項包括:

   * 選擇
   * 下載
   * 檢視屬性
   * 編輯
   * 注釋
   * 複製

   如需您可以在選件和資料夾上執行之工作的詳細資訊，請參閱 [使用資產庫中的內容](/help/main/c-experiences/c-manage-content/assets-working.md).

   >[!NOTE]
   >
   >影像選件不屬於 [企業使用者許可權](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 模型。


## 檢視選件定義 {#section_6B059DD121434E6292CAB393507D010E}

您可以在的快顯示卡片上檢視選件定義的詳細資訊 [!UICONTROL Offers] 程式庫，而不開啟選件。

例如，按一下資訊圖示，即可存取HTML選件的下列選件定義卡片：

![offer-card-html影像](assets/offer-card-html-new.png)

可使用下列資訊:

* 名稱
* 選件 ID
* 類型
* 上次修改

按一下 [!UICONTROL View Full Details] 檢視選件內容和參考代碼選件之活動的連結。 這樣可讓您在編輯選件時，避免影響其他活動。資訊包括 [!UICONTROL Live Activities] 和 [!UICONTROL Inactive Activities].

每張卡片上的可用資訊會依選件型別而異：HTML選件， [體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)， [重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)， [遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)，或 [JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md).

優惠方案詳細資料功能不適用於影像優惠方案。

<!--

## Training video: The Content Repository ![Overview badge](/help/main/assets/overview.png)

This video includes information about managing offers.

* Connection between the [Experience Cloud Asset Library](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) and the Target Content Library 
* Custom HTML Offers 
* Custom HTML Offer in the [!UICONTROL Visual Experience Composer]

>[!VIDEO](https://video.tv.adobe.com/v/17387)

-->

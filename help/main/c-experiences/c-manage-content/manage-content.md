---
keywords: 內容; 資產; 管理內容; 選件; 管理資產; 進入選擇模式; 選擇模式
description: 使用Adobe Target的「優惠」庫瞭解如何管理代碼和映像優惠。
title: 如何管理代碼和映像提供？
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 37%

---

# 選件

使用 [!UICONTROL 優惠] 庫 [!DNL Adobe Target] 管理您的代碼提供和映像提供內容。

1. 按一下&#x200B;**[!UICONTROL 「選件」]**&#x200B;以開啟資料庫。

   此資料庫包含已透過 [!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] (AMS) 和 API 來設定的選件。在 [!DNL Target Classic] 或其他解決方案中建立的選件，都可以在 [!DNL Target Standard/Premium] 中編輯。

   的 [!UICONTROL 優惠] 頁面右側有兩個頁籤： [!UICONTROL 代碼優惠] 和 [!UICONTROL 映像提供] 讓您按類型查看優惠。

   ![顯示「代碼優惠」和「映像優惠」頁籤的「優惠」頁](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. （可選）按一下 **[!UICONTROL 類型]** 按類型篩選優惠的下拉清單(HTML優惠， [體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。 [重定向服務](/help/main/c-experiences/c-manage-content/offer-redirect.md)。 [遠程服務](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。 [JSON優惠](/help/main/c-experiences/c-manage-content/create-json-offer.md), [資料夾](/help/main/c-experiences/c-manage-content/create-content-folder.md))。

   ![](assets/offers_filter.png)

1. （可選）按一下 **[!UICONTROL 源]** 按源篩選提供的下拉清單(Adobe Target、Adobe Target經典和Adobe Experience Manager)。

1. （可選）通過懸停在上面所需的優惠或資料夾上執行其他任務 [!UICONTROL 代碼優惠] 按鈕。

   ![代碼選件選項](assets/offer-picker-large.png)

   選項包括:

   * 查看(有關詳細資訊，請參閱 [查看優惠定義](#section_6B059DD121434E6292CAB393507D010E) 下)。
   * 編輯
   * 複製
   * 移動(例如，要將一個或多個項目移入資料夾，請按一下 **[!UICONTROL 移動]** 表徵圖，按一下所需資料夾，然後按一下 **[!UICONTROL 刪除]**。)
   * 刪除

   根據您的權限，您可能看不到所有選項的表徵圖。 例如， [!UICONTROL 觀察者] 權限無權使用 [!UICONTROL 複製] 的雙曲餘切值。

   有關您可以對聘用和資料夾執行的任務的詳細資訊，請參閱 [在資產庫中處理內容](/help/main/c-experiences/c-manage-content/assets-working.md)。

1. （可選）通過懸停在所需影像提供或資料夾上執行其他任務 [!UICONTROL 映像提供] 按鈕。

   ![影像選件選項](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   選項包括:

   * 選擇
   * 下載
   * 檢視屬性
   * 編輯
   * 注釋
   * 複製

   有關您可以對聘用和資料夾執行的任務的詳細資訊，請參閱 [在資產庫中處理內容](/help/main/c-experiences/c-manage-content/assets-working.md)。

## 查看優惠定義 {#section_6B059DD121434E6292CAB393507D010E}

您可以在中查看彈出式卡的優惠定義詳細資訊 [!UICONTROL 優惠] 圖書館，卻沒有開啟。

例如，通過將HTML優惠懸停在上面，可訪問以下優惠定義卡 [!UICONTROL 內容] 清單，然後按一下「資訊」表徵圖：

![](assets/offer-card-html.png)

可使用下列資訊:

* 名稱
* 來源
* 類型
* 選件 ID
* 選件路徑
* 上次修改

按一下[!UICONTROL 「選件使用情況」]標籤，即可在每一個選件的定義快顯卡片中，檢視已參考程式碼選件的活動。此功能不適用影像選件。這樣可讓您在編輯選件時，避免影響其他活動。資訊包括 [!UICONTROL 即時活動] 和 [!UICONTROL 非活動活動]。

![](assets/offer-card-usage.png)

以下是「重新導向」選件的選件定義卡片:

![](assets/offer-card-redirect.png)

可使用下列資訊:

* 名稱
* 來源
* 類型
* 選件 ID
* 選件路徑
* 上次修改
* 重新導向 URL
* 包括所有URL參數（開啟或關閉）
* 傳遞mbox會話ID（開啟或關閉）

以下是「遠端」選件的選件定義卡片:

![](assets/offer-card-remote.png)

可使用下列資訊:

* 名稱
* 來源
* 類型
* 選件 ID
* 選件路徑
* 上次修改
* 重新導向 URL 類型
* 絕對或相對 URL

## 訓練影片: 內容存放庫 ![概述徽章](/help/main/assets/overview.png)

此影片包含管理選件的相關資訊。

* [Experience Cloud 資產資料庫](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) 與 Target 內容庫之間的連線
* 自訂 HTML 選件
* 可視化體驗撰寫器中的自訂 HTML 選件

>[!VIDEO](https://video.tv.adobe.com/v/17387)

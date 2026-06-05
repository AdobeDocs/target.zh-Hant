---
keywords: 內容; 資產; 管理內容; 產品建議; 管理資產; 進入選擇模式; 選擇模式
description: 探索如何使用[!UICONTROL 選件]資料庫有效管理程式碼和影像選件。
title: 我該如何管理程式碼和影像選件？
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
TQID: https://experienceleague.adobe.com/A8ZLHW-FrWHGPJR7P-mhl2pO6SPoDc--LWpFEjtQzBY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 958
ht-degree: 7%

---

# 產品建議

探索如何使用[!DNL Adobe Target]中的[!UICONTROL 選件]資料庫有效管理程式碼和影像選件。

若要顯示[!UICONTROL 選件]資料庫，請按一下[!DNL Target] UI頂端的&#x200B;**[!UICONTROL 選件]**&#x200B;標籤。

![產品建議頁面](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

[!UICONTROL 選件]資料庫包含已透過[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] (AMS)和API設定的選件。 在 [!DNL Target Classic] 或其他解決方案中建立的產品建議，都可以在 [!DNL Target Standard/Premium] 中編輯。

[!UICONTROL 選件]資料庫提供所有程式碼和影像選件的概觀，並讓您執行各種動作：

| 元素 | 說明 |
|--- |--- |
| 左側導覽邊欄 | 切換顯示[!UICONTROL 代碼選件]或[!UICONTROL 影像選件]。 |
| [!UICONTROL 顯示資料夾] / [!UICONTROL 隱藏資料夾]<P>![顯示篩選器/隱藏篩選器圖示](/help/main/assets/icons/RailLeft.svg) | 按一下&#x200B;**[!UICONTROL 顯示資料夾]**&#x200B;或&#x200B;**[!UICONTROL 隱藏資料夾]**&#x200B;圖示，在顯示您的選件資料夾結構或不顯示您的資料夾結構之間切換。<P>如需詳細資訊，請參閱[建立選件資料夾](/help/main/c-experiences/c-manage-content/create-content-folder.md)。 |
| [!UICONTROL 顯示篩選器]圖示<P>![顯示篩選器圖示](/help/main/assets/icons/Filter.svg) | 按一下「**[!UICONTROL 顯示篩選器]**」圖示，依[!UICONTROL 型別]、[!UICONTROL Source]和[!UICONTROL AEM型別]來篩選選件。<P>如需詳細資訊，請參閱下面的[將篩選器套用至選件清單](#filters)。 |
| 搜尋欄位 | 使用&#x200B;**[!UICONTROL 搜尋]**&#x200B;欄位來快速尋找選件或減少[!UICONTROL 選件]資料庫中顯示的選件數目。 您可以依[!UICONTROL 選件名稱]、[!UICONTROL AEM路徑]或[!UICONTROL AEM標籤]來搜尋。 搜尋選項會持續工作階段。 |
| [!UICONTROL 建立資料夾] | 按一下「**[!UICONTROL 建立資料夾]**」以在[!UICONTROL 選件]資料庫中建立資料夾，以保留代碼選件、影像選件以及其他資料夾以建立子資料夾結構。<P>如需詳細資訊，請參閱[建立選件資料夾](/help/main/c-experiences/c-manage-content/create-content-folder.md)。 |
| [!UICONTROL [!UICONTROL 建立產品建議]] | 按一下&#x200B;**[!UICONTROL 建立選件]**&#x200B;以建立選件。<P>如需建立各種選件型別的詳細資訊，請參閱： <ul><li>HTML 產品建議</li><li>[JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| 大量作業核取方塊<P>![大量作業圖示](/help/main/assets/icons/Rectangle.svg) | 按一下[!UICONTROL 大量作業]核取方塊，以針對所有選件或選取的選件執行大量作業。<P>如需可用動作的清單（視您的許可權和選件狀態而定），請參閱下方的[執行快速動作](#quick-actions)。 |
| [!UICONTROL 名稱] | 每個選件的名稱。<P>按一下每個優惠方案名稱旁的&#x200B;**[!UICONTROL 快速資訊]**&#x200B;圖示（![快速資訊圖示](/help/main/assets/icons/InfoOutline.svg) ），在快顯示卡中檢視有關該優惠方案的詳細資訊，包括優惠方案ID、型別、上次修改優惠方案的日期及修改者等等。<p>按一下每個選件名稱旁的&#x200B;**[!UICONTROL 更多動作]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ）以開啟功能表，讓您對活動執行快速動作。 下列動作可供使用（視您的許可權和選件狀態而定）： [!UICONTROL 編輯]、[!UICONTROL 複製]、[!UICONTROL 刪除]和[!UICONTROL 移動]。 如需每個動作的詳細資訊，請參閱下面的[執行快速動作](#quick-actions)。<P>按一下表格標題，依名稱的字母遞增或遞減順序排序清單。 |
| [!UICONTROL 類型] | 選件型別： [!UICONTROL HTML選件]、[[!UICONTROL 重新導向選件]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL 遠端選件]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)和[[!UICONTROL JSON選件]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。 |
| [!UICONTROL Source] | 顯示建立選件的位置： [!DNL Adobe Target]、[!DNL Adobe Target Classic]和[!DNL Adobe Experience Manager]。 |
| [!UICONTROL 上次更新時間] | 顯示上次修改優惠方案的日期與時間以及修改者。<P>按一下表格標題，依日期以遞增或遞減順序排序清單。 |

## 套用篩選器至選件程式庫 {#filters}

按一下&#x200B;**[!UICONTROL 顯示篩選器]**&#x200B;圖示（![顯示篩選器圖示在選件頁面](/help/main/assets/icons/Filter.svg)）以依[!UICONTROL 型別]、[!UICONTROL Source]和[!UICONTROL AEM型別]篩選選件。

**[!UICONTROL 顯示篩選器]**&#x200B;圖示可讓您依下列類別篩選選件：

* **[!UICONTROL 型別]**： [!UICONTROL HTML選件]、[[!UICONTROL 重新導向選件]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL 遠端選件]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)和[[!UICONTROL JSON選件]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。

* **[!UICONTROL Source]**： [!DNL Adobe Target]、[!DNL Adobe Target Classic]和[!DNL Adobe Experience Manager]。

* **AEM型別**： [內容片段](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md)和[體驗片段](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)。 如需不同片段型別的詳細資訊，請參閱[AEM體驗片段和內容片段概觀](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

篩選器是工作階段持續性的。

## 執行快速動作 {#quick-actions}

您可以按一下適當的圖示來執行下列快速動作：

### 快速資訊

按一下每個優惠方案名稱旁的&#x200B;**[!UICONTROL 快速資訊]**&#x200B;圖示（![快速資訊圖示](/help/main/assets/icons/InfoOutline.svg) ），在快顯示卡中檢視有關該優惠方案的詳細資訊，包括優惠方案ID、型別、上次修改優惠方案的日期及修改者等等。 可用的選項取決於選件型別： [!UICONTROL HTML選件]、[[!UICONTROL JSON選件]](/help/main/c-experiences/c-manage-content/create-json-offer.md)、[[!UICONTROL 重新導向選件]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL 遠端選件]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

### 更多動作

[!UICONTROL 代碼選件]和[!UICONTROL 影像選件]的可用動作稍有不同。 以下章節包含更多資訊:

#### [!UICONTROL 代碼選件]選項

按一下每個選件名稱旁的&#x200B;**[!UICONTROL 更多動作]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg)）以開啟功能表，讓您對活動執行快速動作。

下列動作可供使用（視您的許可權和選件狀態而定）：

* [!UICONTROL 編輯]
* [!UICONTROL 副本]
* [!UICONTROL 刪除]
* [!UICONTROL 移動] （例如，若要將一或多個專案移動到資料夾中，請按一下所要專案旁的&#x200B;**[!UICONTROL 移動]**，按一下所要的資料夾，然後按一下&#x200B;**[!UICONTROL 移動]**。）

視您的許可權而定，您可能不會看到所有選項的圖示。 例如，具有[!UICONTROL 觀察者]許可權的使用者無權使用[!UICONTROL 複製]選項。

如需您可以在選件和資料夾上執行之工作的詳細資訊，請參閱[使用資產庫中的內容](/help/main/c-experiences/c-manage-content/assets-working.md)。

#### [!UICONTROL 影像選件]選項

將游標停留在[!UICONTROL 影像選件]索引標籤上所需的影像選件或資料夾上，然後按一下所需的圖示，以執行其他工作。

選項包括:

* [!UICONTROL Select]
* [!UICONTROL 下載]
* [!UICONTROL 檢視屬性]
* [!UICONTROL 更多動作]
* [!UICONTROL 編輯]
* [!UICONTROL 註釋]
* [!UICONTROL 副本]

如需您可以在選件和資料夾上執行之工作的詳細資訊，請參閱[使用資產庫中的內容](/help/main/c-experiences/c-manage-content/assets-working.md)。

>[!NOTE]
>
>影像選件不是[企業使用者許可權](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)模型的一部分。

## 檢視選件定義 {#section_6B059DD121434E6292CAB393507D010E}

若要在[!UICONTROL 選件]資料庫中的快顯示卡片上檢視選件定義詳細資訊，而不開啟選件，請按一下（ ![快速資訊圖示](/help/main/assets/icons/InfoOutline.svg) ）。

可使用下列資訊:

* [!UICONTROL 名稱]
* [!UICONTROL 選件ID]
* [!UICONTROL 類型]
* [!UICONTROL 上次修改時間]

按一下[!UICONTROL 檢視完整詳細資料]連結，以檢視在每一個選件定義快顯示卡片中參考代碼選件的選件屬性和活動。 此功能不適用影像產品建議。 這樣可讓您在編輯產品建議時，避免影響其他活動。 資訊包含[!UICONTROL 已上線活動]和[!UICONTROL 非使用中活動]的詳細資料。

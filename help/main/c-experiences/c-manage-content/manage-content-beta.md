---
keywords: 內容; 資產; 管理內容; 選件; 管理資產; 進入選擇模式; 選擇模式
description: 探索如何使用[!UICONTROL Offers]資料庫有效管理程式碼和影像選件。
title: 我該如何管理程式碼和影像選件？
feature: Experiences and Offers
badgeBeta: label="Beta 版" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 有哪些 Beta 版功能。"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: 0c86e142b7d459d07af51ec0c3454611564c8e08
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 8%

---

# 選件

探索如何使用[!DNL Adobe Target]中的[!UICONTROL Offers]資料庫有效管理程式碼和影像選件。

>[!NOTE]
>
>本文包含[!DNL Target]使用者介面的更新資訊，該介面目前是Beta程式的一部分。 [!DNL Adobe Target]團隊經常為特定客戶啟用新功能，以進行測試和提供意見回饋。 在測試期間完成後，這些功能會在未來[!DNL Target]版本中針對所有客戶啟用，並在[發行說明](/help/main/r-release-notes/release-notes.md)中宣佈。

若要顯示[!UICONTROL Offers]資料庫，請按一下[!DNL Target] UI頂端的&#x200B;**[!UICONTROL Offers]**&#x200B;標籤。

![選件頁面](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

[!UICONTROL Offers]資料庫包含已透過[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] (AMS)和API設定的選件。 在 [!DNL Target Classic] 或其他解決方案中建立的選件，都可以在 [!DNL Target Standard/Premium] 中編輯。

[!UICONTROL Offers]資料庫提供所有程式碼和影像選件的概觀，並讓您執行各種動作：

| 元素 | 說明 |
|--- |--- |
| 左側導覽邊欄 | 在顯示[!UICONTROL Code Offers]或[!UICONTROL Image Offers]之間切換。 |
| [!UICONTROL Show Folders] / [!UICONTROL Hide Folders]<P>![顯示篩選器/隱藏篩選器圖示](/help/main/assets/icons/RailLeft.svg) | 按一下&#x200B;**[!UICONTROL Show Folders]**&#x200B;或&#x200B;**[!UICONTROL Hide Folders]**&#x200B;圖示，在顯示您的選件資料夾結構或不顯示您的資料夾結構之間切換。<P>如需詳細資訊，請參閱[建立選件資料夾](/help/main/c-experiences/c-manage-content/create-content-folder.md)。 |
| [!UICONTROL Show filters]圖示<P>![顯示篩選器圖示](/help/main/assets/icons/Filter.svg) | 按一下「**[!UICONTROL Show filters]**」圖示，依[!UICONTROL Type]、[!UICONTROL Source]和[!UICONTROL AEM Type]篩選優惠方案。<P>如需詳細資訊，請參閱下面的[將篩選器套用至選件清單](#filters)。 |
| 搜尋欄位 | 使用&#x200B;**[!UICONTROL Search in]**&#x200B;欄位快速尋找優惠方案或減少[!UICONTROL Offers]資料庫中顯示的優惠方案數目。 您可以依[!UICONTROL Offer Name]、[!UICONTROL AEM Paths]或[!UICONTROL AEM Tags]搜尋。 |
| [!UICONTROL Create Folder] | 按一下&#x200B;**[!UICONTROL Create Folder]**&#x200B;在[!UICONTROL Offer]資料庫中建立資料夾以保留代碼選件、影像選件以及其他資料夾以建立子資料夾結構。<P>如需詳細資訊，請參閱[建立選件資料夾](/help/main/c-experiences/c-manage-content/create-content-folder.md)。 |
| [!UICONTROL [!UICONTROL Create Offer]] | 按一下&#x200B;**[!UICONTROL Create Offer]**&#x200B;以建立選件。<P>如需建立各種選件型別的詳細資訊，請參閱： <ul><li>HTML 選件</li><li>[JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| 大量作業核取方塊<P>![大量作業圖示](/help/main/assets/icons/Rectangle.svg) | 按一下[!UICONTROL Bulk Operations]核取方塊，以針對所有選件或選取的選件執行大量作業。<P>如需可用動作的清單（視您的許可權和選件狀態而定），請參閱下方的[執行快速動作](#quick-actions)。 |
| [!UICONTROL Name] | 每個選件的名稱。<P>按一下每個優惠方案名稱旁的&#x200B;**[!UICONTROL Quick Info]**&#x200B;圖示（ ![快速資訊圖示](/help/main/assets/icons/InfoOutline.svg) ），即可在快顯示卡中檢視有關該優惠方案的詳細資訊，包括優惠方案ID、型別、上次修改優惠方案的日期及修改者等等。<p>按一下每個選件名稱旁的&#x200B;**[!UICONTROL More Actions]**&#x200B;圖示（ ![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ）以開啟功能表，讓您對活動執行快速動作。 下列動作可供使用（視您的許可權和選件狀態而定）： [!UICONTROL Edit]、[!UICONTROL Copy]、[!UICONTROL Delete]和[!UICONTROL Move]。 如需每個動作的詳細資訊，請參閱下面的[執行快速動作](#quick-actions)。<P>按一下表格標題，依名稱的字母遞增或遞減順序排序清單。 |
| [!UICONTROL Type] | 選件型別： [!UICONTROL HTML Offers]、[[!UICONTROL Redirect Offers]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL Remote Offers]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)和[[!UICONTROL JSON Offers]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。 |
| [!UICONTROL Source] | 顯示建立選件的位置： [!DNL Adobe Target]、[!DNL Adobe Target Classic]和[!DNL Adobe Experience Manager]。 |
| [!UICONTROL Last updated] | 顯示上次修改優惠方案的日期與時間以及修改者。<P>按一下表格標題，依日期以遞增或遞減順序排序清單。 |

## 套用篩選器至選件程式庫 {#filters}

按一下「**[!UICONTROL Show filters]**」圖示（「選件」頁面](/help/main/assets/icons/Filter.svg)上的「![顯示篩選器」圖示）以依[!UICONTROL Type]、[!UICONTROL Source]和[!UICONTROL AEM Type]篩選選件。

**[!UICONTROL Show filters]**&#x200B;圖示可讓您依下列類別篩選優惠方案：

* **[!UICONTROL Type]**： [!UICONTROL HTML Offer]、[[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)和[[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md)。

* **[!UICONTROL Source]**： [!DNL Adobe Target]、[!DNL Adobe Target Classic]和[!DNL Adobe Experience Manager]。

* **AEM型別**： [內容片段](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md)和[體驗片段](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)。 如需不同片段型別的詳細資訊，請參閱[AEM體驗片段和內容片段概觀](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 執行快速動作 {#quick-actions}

您可以按一下適當的圖示來執行下列快速動作：

### 快速資訊

按一下每個優惠方案名稱旁的&#x200B;**[!UICONTROL Quick Info]**&#x200B;圖示（ ![快速資訊圖示](/help/main/assets/icons/InfoOutline.svg) ），即可在快顯示卡中檢視有關該優惠方案的詳細資訊，包括優惠方案ID、型別、上次修改優惠方案的日期及修改者等等。 可用的選項取決於選件型別： [!UICONTROL HTML Offer]、[[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md)、[[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

### 更多動作

[!UICONTROL Code Offers]和[!UICONTROL Image Offers]可用的動作稍有不同。 以下章節包含更多資訊: 

#### [!UICONTROL Code Offer]選項

按一下每個選件名稱旁的&#x200B;**[!UICONTROL More actions]**&#x200B;圖示（ ![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ）以開啟功能表，讓您對活動執行快速動作。

下列動作可供使用（視您的許可權和選件狀態而定）：

* [!UICONTROL Edit]
* [!UICONTROL Copy]
* [!UICONTROL Delete]
* [!UICONTROL Move] （例如，若要將一或多個專案移至資料夾，請按一下所要專案旁的&#x200B;**[!UICONTROL Move]**，按一下所要的資料夾，然後按一下&#x200B;**[!UICONTROL Move]**。）

視您的許可權而定，您可能不會看到所有選項的圖示。 例如，具有[!UICONTROL Observer]許可權的使用者無權使用[!UICONTROL Copy]選項。

如需您可以在選件和資料夾上執行之工作的詳細資訊，請參閱[使用資產庫中的內容](/help/main/c-experiences/c-manage-content/assets-working.md)。

#### [!UICONTROL Image Offer]選項

將游標暫留在[!UICONTROL Image Offers]標籤上所需的影像選件或資料夾上，然後按一下所需的圖示，以執行其他工作。

選項包括:

* [!UICONTROL Select]
* [!UICONTROL Download]
* [!UICONTROL View Properties]
* [!UICONTROL More Actions]
* [!UICONTROL Edit]
* [!UICONTROL Annotate]
* [!UICONTROL Copy]

如需您可以在選件和資料夾上執行之工作的詳細資訊，請參閱[使用資產庫中的內容](/help/main/c-experiences/c-manage-content/assets-working.md)。

>[!NOTE]
>
>影像選件不是[企業使用者許可權](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)模型的一部分。

## 檢視選件定義 {#section_6B059DD121434E6292CAB393507D010E}

若要在[!UICONTROL Offers]資料庫中的快顯示卡片上檢視選件定義詳細資訊，而不開啟選件，請按一下（ ![快速資訊圖示](/help/main/assets/icons/InfoOutline.svg) ）。

可使用下列資訊:

* [!UICONTROL Name]
* [!UICONTROL Offer ID]
* [!UICONTROL Type]
* [!UICONTROL Last Modified]

按一下[!UICONTROL View Full Details]連結，以檢視在每一選件的定義快顯示卡片中參考代碼選件的選件屬性和活動。 此功能不適用影像選件。這樣可讓您在編輯選件時，避免影響其他活動。資訊包含[!UICONTROL Live Activities]和[!UICONTROL Inactive Activities]的詳細資料。

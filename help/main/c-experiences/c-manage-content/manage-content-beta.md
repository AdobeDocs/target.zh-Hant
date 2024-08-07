---
keywords: 內容; 資產; 管理內容; 選件; 管理資產; 進入選擇模式; 選擇模式
description: 瞭解如何使用選件資料庫來管理程式碼和影像選件。
title: 我該如何管理程式碼和影像選件？
feature: Experiences and Offers
badgeBeta: label="Beta 版" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 有哪些 Beta 版功能。"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: 5d14dfd700cb1cec0fa62f66da1400bc8d7fd109
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 17%

---

# 選件

在[!DNL Adobe Target]中使用[!UICONTROL Offers]資料庫來管理您的程式碼和影像選件內容。

>[!NOTE]
>
>本文包含[!DNL Target]使用者介面的更新資訊，該介面目前是Beta程式的一部分。 [!DNL Adobe Target]團隊經常為特定客戶啟用新功能，以進行測試和提供意見回饋。 在測試期間完成後，這些功能會在未來[!DNL Target Standard/Premium]版本中針對所有客戶啟用，並在發行說明中宣佈。

按一下[!DNL Target] UI頂端的&#x200B;**[!UICONTROL Offers]**&#x200B;索引標籤以顯示[!UICONTROL Offers]資料庫。

Adobe Target中的![選件程式庫](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

[!UICONTROL Offers]資料庫包含已透過[!DNL Target Standard/Premium]、[!DNL Target Classic]、[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] (AMS)和API設定的選件。 在 [!DNL Target Classic] 或其他解決方案中建立的選件，都可以在 [!DNL Target Standard/Premium] 中編輯。

選件資料庫提供所有程式碼和影像選件的概觀，可讓您執行各種動作：

| 元素 | 說明 |
|--- |--- |
| 左側導覽邊欄 | 在清單[!UICONTROL Code Offers]或[!UICONTROL Image Offers]之間切換。 |
| [!UICONTROL Show filters]圖示<P>![顯示篩選器圖示](/help/main/c-activities/assets/show-filters-icon.png) | 按一下「**[!UICONTROL Show filters]**」圖示，依[!UICONTROL Type]、[!UICONTROL Source]和[!UICONTROL AEM Type]篩選優惠方案<P>如需詳細資訊，請參閱下面的[將篩選器套用至選件清單](#filters)。 |
| 搜尋欄位 | 使用&#x200B;**[!UICONTROL Search in]**&#x200B;欄位快速尋找優惠方案或減少[!UICONTROL Offers]資料庫中顯示的優惠方案數目。 您可以依[!UICONTROL Offer Name]、[!UICONTROL AEM Paths]或[!UICONTROL AEM Tags]搜尋。 |
| [!UICONTROL Create Folder] | 按一下「建立資料夾」在[!UICONTROL Offer]資料庫中建立資料夾，以保留代碼選件、影像選件以及其他資料夾以建立子資料夾結構。 如需詳細資訊，請參閱[建立選件資料夾](/help/main/c-experiences/c-manage-content/create-content-folder.md)。 |
| [!UICONTROL [!UICONTROL Create Offer]] | 建立優惠方案。 如需建立各種選件型別的詳細資訊，請參閱： <ul><li>HTML 選件</li><li>[JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| 大量作業核取方塊 | 針對所有活動或選取的活動執行大量作業。<P>如需可用動作的清單（視您的許可權和選件狀態而定），請參閱下方的[執行快速動作](#quick-actions)。 |
| [!UICONTROL Name] | 每個選件的名稱。<P>按一下每個優惠方案名稱旁的&#x200B;**[!UICONTROL Quick Info]**&#x200B;圖示，即可在快顯示卡中檢視該優惠方案的詳細資訊，包括優惠方案ID、型別、上次修改優惠方案的日期及修改者等等。<p>按一下每個選件名稱旁的&#x200B;**[!UICONTROL More actions]**&#x200B;圖示（水準省略符號）以開啟功能表，讓您對活動執行快速動作。 下列動作可供使用（視您的許可權和選件狀態而定）： [!UICONTROL Edit]、[!UICONTROL Copy]、[!UICONTROL Delete]和[!UICONTROL Move]。 如需每個動作的詳細資訊，請參閱下面的[執行快速動作](#quick-actions)。<P>按一下表格標題，依名稱的字母遞增或遞減順序排序清單。 |
| [!UICONTROL Type] | 選件型別：HTML選件、[重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)和[JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)。 |
| [!UICONTROL Source] | 顯示建立選件的位置： [!DNL Adobe Target]、[!DNL Adobe Target Classic]和[!DNL Adobe Experience Manager]。 |

## 套用篩選器至選件程式庫 {#filters}

按一下「**[!UICONTROL Show filters]**」圖示（「選件」頁面上的「![顯示篩選器」圖示](/help/main/c-experiences/c-manage-content/assets/show-filters-icon.png)）以依[!UICONTROL Type]、[!UICONTROL Source]和[!UICONTROL AEM Type]篩選選件。

![offers_filter影像](assets/offers-filter-new.png)

**[!UICONTROL Show filters]**&#x200B;圖示可讓您依下列類別篩選優惠方案：

* **型別**：HTML選件，[JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)，[重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)，[遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

* **Source**： [!DNL Adobe Target]、[!DNL Adobe Target Classic]和[!DNL Adobe Experience Manager]。

* **AEM型別**： [內容片段](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md)和[體驗片段](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)。 如需不同片段型別的詳細資訊，請參閱[AEM體驗片段和內容片段概觀](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 執行快速動作 {#quick-actions}

您可以按一下適當的圖示來執行下列快速動作：

### 快速資訊

按一下每個優惠方案名稱旁的&#x200B;**[!UICONTROL Quick Info]**&#x200B;圖示，即可在快顯示卡中檢視該優惠方案的詳細資訊，包括優惠方案ID、型別、上次修改優惠方案的日期及修改者等等。 可用的選項取決於選件型別：HTML選件、[JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)、[重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)、[遠端選件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

![](/help/main/c-experiences/c-manage-content/assets/quick-actions.png)

### 更多動作

代碼選件和影像選件的可用動作稍有不同。 以下章節包含更多資訊: 

#### [!UICONTROL Code Offer]選項

按一下每個選件名稱旁的&#x200B;**[!UICONTROL More actions]**&#x200B;圖示（水準省略符號）以開啟功能表，讓您對活動執行快速動作。 下列動作可供使用（視您的許可權和選件狀態而定）： [!UICONTROL Edit]、[!UICONTROL Copy]、[!UICONTROL Delete]和[!UICONTROL Move]。

Target選件資料庫中有![個其他動作選項](/help/main/c-experiences/c-manage-content/assets/more-actions.png)

* 編輯
* 複製
* 刪除
* 移動（例如，若要將一或多個專案移至資料夾，請按一下所需專案的&#x200B;**[!UICONTROL Move]**&#x200B;圖示、按一下所需的資料夾，然後按一下&#x200B;**[!UICONTROL Drop]**）。

視您的許可權而定，您可能不會看到所有選項的圖示。 例如，具有[!UICONTROL Observer]許可權的使用者無權使用[!UICONTROL Copy]選項。

如需您可以在選件和資料夾上執行之工作的詳細資訊，請參閱[使用資產庫中的內容](/help/main/c-experiences/c-manage-content/assets-working.md)。

#### [!UICONTROL Image Offer]選項

將游標暫留在[!UICONTROL Image Offers]標籤上所需的影像選件或資料夾上，然後按一下所需的圖示，以執行其他工作。

![影像選件選項](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

選項包括:

* 選擇
* 下載
* 檢視屬性
* 編輯
* 注釋
* 複製

如需您可以在選件和資料夾上執行之工作的詳細資訊，請參閱[使用資產庫中的內容](/help/main/c-experiences/c-manage-content/assets-working.md)。

>[!NOTE]
>
>影像選件不是[企業使用者許可權](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)模型的一部分。

## 檢視選件定義 {#section_6B059DD121434E6292CAB393507D010E}

您可以在[!UICONTROL Offers]資料庫中的快顯示卡片上檢視選件定義詳細資料，而不需要開啟選件。

例如，將游標移至[!UICONTROL Content]清單上的選件上，然後按一下資訊圖示，即可存取HTML選件的下列選件定義卡片：

![offer-card-html影像](assets/offer-card-html.png)

可使用下列資訊:

* 名稱
* 來源
* 類型
* 選件 ID
* 選件路徑
* 上次修改

按一下[!UICONTROL Offer Usage]索引標籤，以檢視參照每個選件定義快顯示卡片中的程式碼選件的活動。 此功能不適用影像選件。這樣可讓您在編輯選件時，避免影響其他活動。資訊包括[!UICONTROL Live Activities]和[!UICONTROL Inactive Activities]。

![優惠卡使用狀況影像](assets/offer-card-usage.png)

以下是「重新導向」選件的選件定義卡片:

![優惠卡重新導向影像](assets/offer-card-redirect.png)

可使用下列資訊:

* 名稱
* 來源
* 類型
* 選件 ID
* 選件路徑
* 上次修改
* 重新導向 URL
* 包含所有URL引數（開啟或關閉）
* 傳遞mbox工作階段ID （開啟或關閉）

以下是「遠端」選件的選件定義卡片:

![優惠卡遠端影像](assets/offer-card-remote.png)

可使用下列資訊:

* 名稱
* 來源
* 類型
* 選件 ID
* 選件路徑
* 上次修改
* 重新導向 URL 類型
* 絕對或相對 URL

## 訓練影片：內容存放庫![Overview badge](/help/main/assets/overview.png)

此影片包含管理選件的相關資訊。

* [Experience Cloud 資產資料庫](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) 與 Target 內容庫之間的連線
* 自訂 HTML 選件
* 可視化體驗撰寫器中的自訂 HTML 選件

>[!VIDEO](https://video.tv.adobe.com/v/17387)

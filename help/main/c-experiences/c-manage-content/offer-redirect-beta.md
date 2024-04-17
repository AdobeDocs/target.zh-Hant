---
keywords: 重新導向選件; 建立重新導向選件; 新增 html 選件; 在重新導向中傳入所有 URL 參數; 在重新導向中傳入 mboxSessionId (只有在要重新導向至不同網域時才需要)
description: 瞭解如何在中建立重新導向選件 [!DNL Target] ，使瀏覽器重新導向至新頁面。
title: 如何建立重新導向選件？
feature: Experiences and Offers
badgeBeta: label="Beta 版" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 有哪些 Beta 版功能。"
hide: true
hidefromtoc: true
source-git-commit: bd19686d2aa716af64f520fb0be798a300ed9fa3
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 31%

---

# 建立重新導向選件

在中建立重新導向選件 [!DNL Adobe Target] ，使瀏覽器重新導向至新頁面。

>[!NOTE]
>
>本文包含更新的 [!DNL Target] 目前是Beta版計劃一部分的使用者介面。 此 [!DNL Adobe Target] 團隊通常會為特定客戶啟用新功能，以進行測試和提供回饋。 在測試期間完成後，這些功能將在未來為所有客戶啟用 [!DNL Target Standard/Premium] 發行版本和發行說明中宣佈。

您可能擁有兩個完全不同的測試頁面，而非只是改變同一頁面中的某部分內容。若是這種情況，您的A/B測試會比較頁面A和頁面B。設定 [!UICONTROL A/B Test] 具有兩個體驗的活動：一個指向預設頁面A，另一個重新導向至頁面B。選件已設定為將訪客重新導向至不同頁面。

>[!NOTE]
>
> * 您可在以下位置建立重新導向選件： [!UICONTROL Offers] > [!UICONTROL Code Offers] 頁面或中的 [Forms體驗撰寫器](/help/main/c-experiences/form-experience-composer.md). 您無法在中建立或套用重新導向選件 [!UICONTROL Visual Experience Composer] (VEC)。 內容會插入至 [!DNL Target] 要求位置，因此這些位置可能不適合全域 [!DNL Target] 要求。
>
>* 您無法在AJAX mbox中使用重新導向選件(`mboxUpdate`)。
>
>* 對於使用Analytics作為報表來源(A4T)的活動中的重新導向選件，您的實作必須符合某些最低需求。 此外，還有需要您知道的重要資訊。如需詳細資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
>
>* 如需設定可重新導向的體驗的相關資訊，請參閱[重新導向至 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。

重新導向選件會執行 JavaScript 程式碼來重新導向瀏覽器。此選件會使用 `window.location.replace();` 方法，所以訪客被重新導向的來源頁面不會儲存在瀏覽器記錄中。此程式可讓訪客在其瀏覽器中使用「上一步」按鈕。

>[!NOTE]
>
>如果您想要傳遞登入頁面的反向連結值，請使用HTML選件，而非重新導向選件。

## 從建立重新導向選件 [!UICONTROL Code Offers] 頁面

1. 按一下 **[!UICONTROL Offers]**，然後選取 **[!UICONTROL Code Offers]** 標籤。

   ![代碼選件索引標籤](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. 按一下 **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.

   ![建立重新導向選件對話方塊](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer-new.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人快速在中找到選件 [!UICONTROL Assets] 資料庫。

1. （視條件而定）如果您擁有 [Target Premium帳戶](/help/main/c-intro/intro.md#premium)，選取所需的 [工作區](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. 指定唯一內容或您要重新導向的目的地URL。 此URL必須是絕對URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向選件會導致無窮迴圈。確保重新導向使用者後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向選件:

   * **包含所有URL引數：** 如果要將上一個頁面上存在的所有URL引數都傳播到重新導向的頁面，請滑動切換以啟用此選項。

     例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也會想要傳遞 URL 中的動態參數，因為這是您追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或組織化方法達到您網站的方式。啟用此選項，即可在頁面上重新導向選件 `https://www.mycompany.com/mens.html?emailId=123` 自動變成 `https://www.mycompany.com/mensShirts.html?emailId=123` 當您在URL方塊中輸入 `https://www.mycompany.com/mensShirts.html`.

   * **傳遞mbox工作階段ID：** 必須重新導向至其他網域。 滑動切換以啟用此選項(如果您想要 `sessionId` 自動包含在重新導向中。 只有在測試來自電子郵件的點按或從某個網域到另一個網域的點按時，才需要此選項。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

     如果您使用第一方和第三方Cookie設定，則跨網域時不需要傳遞mbox工作階段ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下 **[!UICONTROL Create]**。

>[!NOTE]
>
>在啟動這些測試之前，請洽詢您的實作顧問。

## 使用建立重新導向選件 [!UICONTROL Form-Based Experience Composer]

1. 使用建立活動時 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，選取要顯示的位置 **[!UICONTROL Content]** 區段。

   ![表單式體驗撰寫器中的內容區段](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 按一下 **[!UICONTROL Default Content]** 下拉式清單，然後按一下 **[!UICONTROL Change Redirect Offer]**.

   ![變更重新導向選件選項](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. 按一下 **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![建立重新導向選件對話方塊](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人快速在中找到選件 [!UICONTROL Assets] 資料庫。

1. 指定唯一內容或您要重新導向的目的地URL。 此URL必須是絕對URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向選件會導致無窮迴圈。確保重新導向使用者後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向選件:

   * **包含所有URL引數：** 如果要將上一個頁面上存在的所有URL引數都傳播到重新導向的頁面，請滑動切換以啟用此選項。

     例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也會想要傳遞 URL 中的動態參數，因為這是您追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或組織化方法達到您網站的方式。啟用此選項，即可在頁面上重新導向選件 `https://www.mycompany.com/mens.html?emailId=123` 自動變成 `https://www.mycompany.com/mensShirts.html?emailId=123` 當您在URL方塊中輸入 `https://www.mycompany.com/mensShirts.html`.

   * **傳遞mbox工作階段ID：** 必須重新導向至其他網域。 滑動切換以啟用此選項(如果您想要 `sessionId` 自動包含在重新導向中。 只有在測試來自電子郵件的點按或從某個網域到另一個網域的點按時，才需要此選項。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

     如果您使用第一方和第三方Cookie設定，則跨網域時不需要傳遞mbox工作階段ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下 **[!UICONTROL Save]**。

>[!NOTE]
>
>在啟動這些測試之前，請洽詢您的實作顧問。

## 在活動中使用重新導向選件

您必須使用套用重新導向選件 [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md). 您目前無法使用套用重新導向選件 [!UICONTROL Visual Experience Composer] (VEC)。

此 [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] 是非視覺化體驗和選件建立介面，對於建立在中使用的體驗非常有用。 [!UICONTROL A/B Tests]， [!UICONTROL Experience Targeting] (XT)， [!UICONTROL Automated Personalization] (AP)，以及 [!UICONTROL Recommendations] 視覺化體驗撰寫器無法使用或不實用的活動。 例如，您可以使用 [!UICONTROL Form-Based Experience Composer] ，以建立使用重新導向選件的體驗。

1. 在中建立或編輯活動 [!UICONTROL Form-Based Experience Composer].

   另請參閱 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md) 以取得詳細的逐步指示。

1. 指定所需位置，並視需要新增任何對象細分。

1. 按一下 **[!UICONTROL Content]** 區段，然後按一下 **[!UICONTROL Change Redirect Offer]**.

   ![變更重新導向選件選項](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. 從中選擇所需的重新導向選件 [!UICONTROL Select Remote Offer] 對話方塊，然後按一下 **[!UICONTROL Done]**.

1. 完成活動的設定。

## 訓練影片：表單式撰寫器 ![教學課程徽章](/help/main/assets/tutorial.png)

本影片提供 [!UICONTROL Form-Based Experience Composer]，可用來建立重新導向選件。

* 使用建立活動 [!UICONTROL Form-Based Experience Composer]
* 瞭解何時使用 [!UICONTROL Form-Based Experience Composer] 與 [!UICONTROL Visual Experience Composer]
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)
---
keywords: 重新導向選件; 建立重新導向選件; 新增 html 選件; 在重新導向中傳入所有 URL 參數; 在重新導向中傳入 mboxSessionId (只有在要重新導向至不同網域時才需要)
description: 我是否可以使用重新導向選件來讓瀏覽器重新導向至新頁面？
title: 建立重新導向選件
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 49%

---


# 建立重新導向選件

重新導向[!DNL Adobe Target]中的選件會導致瀏覽器重新導向至新頁面。

您可能擁有兩個完全不同的測試頁面，而非只是改變同一頁面中的某部分內容。在此情況下，您的A/B測試會比較頁面A和頁面B。設定A/B測試活動，提供兩種體驗：一個指向預設頁面A，另一個指向頁面B。選件已設定為將訪客重新導向至不同的頁面。

>[!NOTE]
>
> * 重新導向選件可在[!UICONTROL 選件] > [!UICONTROL 代碼選件]頁面或[表單型體驗撰寫器](/help/c-experiences/form-experience-composer.md)中建立。 您無法在Visual Experience Composer(VEC)中建立或套用重新導向選件。 內容會插入至[!DNL Target]請求位置，因此這些位置很可能不適用於全域[!DNL Target]請求。
   >
   >
* 您無法在 ajax mbox (`mboxUpdate`) 中使用重新導向選件。
   >
   >
* 針對使用 A4T 活動中的重新導向選件，您的實施必須符合某些最低需求。此外，還有需要您知道的重要資訊。如需詳細資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
   >
   >
* 如需設定可重新導向的體驗的相關資訊，請參閱[重新導向至 URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。


重新導向選件會執行 JavaScript 程式碼來重新導向瀏覽器。此選件會使用 `window.location.replace();` 方法，所以訪客被重新導向的來源頁面不會儲存在瀏覽器記錄中。這可讓訪客仍然可以使用瀏覽器中的上一步按鈕。

>[!NOTE]
>
>如果要傳入登陸頁面的反向連結值，建議您使用 HTML 選件，而不要使用重新導向選件。

## 從「程式碼選件」頁面建立重新導向選件

1. 按一下&#x200B;**[!UICONTROL 「選件」]**，然後選取&#x200B;**[!UICONTROL 「代碼選件」]**&#x200B;索引標籤。

   ![代碼選件標籤](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]**>**[!UICONTROL 「重新導向選件」]**。

   ![「建立重新導向選件」對話方塊](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在資產資料庫中快速尋找選件。

1. 輸入唯一內容或您要重新導向的目的地的 URL。此 URL 必須是絕對 URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向選件會導致無窮迴圈。您應該確保在將使用者重新導向之後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向選件:

   * **包含所有URL參數：如果您** 想要將上一頁所有顯示的URL參數傳播至重新導向頁面，請滑動切換以啟用此選項。

      例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也會想要傳遞 URL 中的動態參數，因為這是您追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或組織化方法達到您網站的方式。啟用此選項後，當您在URL方塊中輸入的所有內容為`https://www.mycompany.com/mensShirts.html`時，您在頁面`https://www.mycompany.com/mens.html?emailId=123`上的重新導向選件會自動變成`https://www.mycompany.com/mensShirts.html?emailId=123`。

   * **傳遞mbox作業ID：必** 要，以重新導向至不同網域。如果您希望`sessionId`自動包含在重新導向中，請滑動切換以啟用此選項。 只有在您測試電子郵件點按次數或網域點按次數時，才需要此項。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

      如果您使用第一方和第三方Cookie設定，在跨網域時不需要傳遞mbox作業ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>
>在啟動這些測試前，請聯絡您的實作顧問。

## 使用表單型體驗撰寫器建立重新導向選件

1. 使用[表單型體驗撰寫器](/help/c-experiences/form-experience-composer.md)建立活動時，選取要顯示&#x200B;**[!UICONTROL 內容]**&#x200B;區段的位置。

   ![表單型體驗撰寫器中的內容區段](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. 按一下「預設內容」下拉式清單，然後按一下「變更重新導向選件」。********

   ![變更重新導向選件選項](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]**>**[!UICONTROL 「重新導向選件」]**。

   ![「建立重新導向選件」對話方塊](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在資產資料庫中快速尋找選件。

1. 輸入唯一內容或您要重新導向的目的地的 URL。此 URL 必須是絕對 URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向選件會導致無窮迴圈。您應該確保在將使用者重新導向之後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向選件:

   * **包含所有URL參數：如果您** 想要將上一頁所有顯示的URL參數傳播至重新導向頁面，請滑動切換以啟用此選項。

      例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也會想要傳遞 URL 中的動態參數，因為這是您追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或組織化方法達到您網站的方式。啟用此選項後，當您在URL方塊中輸入的所有內容為`https://www.mycompany.com/mensShirts.html`時，您在頁面`https://www.mycompany.com/mens.html?emailId=123`上的重新導向選件會自動變成`https://www.mycompany.com/mensShirts.html?emailId=123`。

   * **傳遞mbox作業ID：必** 要，以重新導向至不同網域。如果您希望`sessionId`自動包含在重新導向中，請滑動切換以啟用此選項。 只有在您測試電子郵件點按次數或網域點按次數時，才需要此項。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

      如果您使用第一方和第三方Cookie設定，在跨網域時不需要傳遞mbox作業ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>
>在啟動這些測試前，請聯絡您的實作顧問。

## 在活動中使用重新導向選件

您必須使用[!UICONTROL 表單型體驗撰寫器]套用重新導向選件。 您目前無法使用VEC套用重新導向選件。

[!DNL Adobe Target][!UICONTROL 表單型體驗撰寫器]是非視覺化體驗和選件建立介面，對於建立用於[!UICONTROL A/B測試]、[!UICONTROL 體驗定位](XT)、[!UICONTROL 自動個人化](XT)的體驗非常有用AP)和[!UICONTROL Recommendations]活動（當視覺體驗視覺化視覺化調整器無法使用或實際使用時）。 例如，您可以使用[!UICONTROL 表單型體驗撰寫器]來建立使用重新導向選件的體驗。

1. 在[!UICONTROL 表單型體驗撰寫器]中建立或編輯活動。

   如需詳細的逐步指示，請參閱[表單式體驗撰寫器](/help/c-experiences/form-experience-composer.md)。

1. 指定所需位置，並視需要新增任何受眾調整。

1. 按一下&#x200B;**[!UICONTROL Content]**&#x200B;區段中的下拉式清單，然後按一下&#x200B;**[!UICONTROL 變更重新導向選件]**。

   ![變更重新導向選件選項](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. 從[!UICONTROL 選擇遠端選件]對話方塊中選擇所要的重新導向選件，然後按一下&#x200B;**[!UICONTROL 完成]**。

1. 完成活動的設定。

## 訓練影片：表單式撰寫器![教學課程標章](/help/assets/tutorial.png)

此影片提供表單型撰寫器的示範，您可使用它來建立重新導向選件。

* 使用表單式體驗撰寫器建立活動
* 瞭解使用表單式體驗撰寫器與可視化體驗撰寫器的時機
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)

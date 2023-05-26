---
keywords: 重新導向選件; 建立重新導向選件; 新增 html 選件; 在重新導向中傳入所有 URL 參數; 在重新導向中傳入 mboxSessionId (只有在要重新導向至不同網域時才需要)
description: 瞭解如何在Adobe中建立重新導向選件 [!DNL Target] ，使瀏覽器重新導向至新頁面。
title: 如何建立重新導向選件？
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 48%

---

# 建立重新導向選件

重新導向選件於 [!DNL Adobe Target] 導致瀏覽器重新導向至新頁面。

您可能擁有兩個完全不同的測試頁面，而非只是改變同一頁面中的某部分內容。在此情況下，您的A/B測試會比較頁面A與頁面B。使用兩個體驗設定A/B測試活動：一個指向預設頁面A，另一個重新導向至頁面B。選件已設定為將訪客重新導向至不同頁面。

>[!NOTE]
>
> * 重新導向選件可建立於 [!UICONTROL 選件] > [!UICONTROL 代碼選件] 頁面或中的 [Forms體驗撰寫器](/help/main/c-experiences/form-experience-composer.md). 您無法在視覺化體驗撰寫器(VEC)中建立或套用重新導向選件。 內容將插入至 [!DNL Target] 要求位置，因此這些可能不適合全域 [!DNL Target] 要求。
>
>* 您無法在 ajax mbox (`mboxUpdate`) 中使用重新導向選件。
>
>* 針對使用 A4T 活動中的重新導向選件，您的實施必須符合某些最低需求。此外，還有需要您知道的重要資訊。如需詳細資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
>
>* 如需設定可重新導向的體驗的相關資訊，請參閱[重新導向至 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。


重新導向選件會執行 JavaScript 程式碼來重新導向瀏覽器。此選件會使用 `window.location.replace();` 方法，所以訪客被重新導向的來源頁面不會儲存在瀏覽器記錄中。這可讓訪客仍然可以使用瀏覽器中的上一步按鈕。

>[!NOTE]
>
>如果要傳入登陸頁面的反向連結值，建議您使用 HTML 選件，而不要使用重新導向選件。

## 從代碼選件頁面建立重新導向選件

1. 按一下&#x200B;**[!UICONTROL 「選件」]**，然後選取&#x200B;**[!UICONTROL 「代碼選件」]**&#x200B;索引標籤。

   ![代碼選件索引標籤](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]**>**[!UICONTROL 「重新導向選件」]**。

   ![建立重新導向選件對話方塊](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在資產資料庫中快速尋找選件。

1. 輸入唯一內容或您要重新導向的目的地的 URL。此 URL 必須是絕對 URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向選件會導致無窮迴圈。您應該確保在將使用者重新導向之後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向選件:

   * **包含所有URL引數：** 如果要將出現在上一頁上的所有URL引數都傳播到重新導向的頁面，請滑動切換以啟用此選項。

      例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也會想要傳遞 URL 中的動態參數，因為這是您追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或組織化方法達到您網站的方式。啟用此選項，即可在頁面上重新導向選件 `https://www.mycompany.com/mens.html?emailId=123` 將自動變成 `https://www.mycompany.com/mensShirts.html?emailId=123` 當您在URL方塊中輸入的是 `https://www.mycompany.com/mensShirts.html`.

   * **傳遞mbox工作階段ID：** 必須重新導向至其他網域。 滑動切換以啟用此選項(如果您需要 `sessionId` 自動包含在重新導向中。 只有在測試來自電子郵件的點按或從某個網域到另一個網域的點按時，才需要此屬性。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

      如果您使用第一方和第三方Cookie設定，則跨網域時不需要傳遞mbox工作階段ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

>[!NOTE]
>
>在啟動這些測試前，請聯絡您的實作顧問。

## 使用表單式體驗撰寫器建立重新導向選件

1. 使用建立活動時 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，選取要顯示的位置 **[!UICONTROL 內容]** 區段。

   ![表單式體驗撰寫器中的內容區段](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 按一下 **[!UICONTROL 預設內容]** 下拉式清單，然後按一下 **[!UICONTROL 變更重新導向選件]**.

   ![變更重新導向選件選項](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]**>**[!UICONTROL 「重新導向選件」]**。

   ![建立重新導向選件對話方塊](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在資產資料庫中快速尋找選件。

1. 輸入唯一內容或您要重新導向的目的地的 URL。此 URL 必須是絕對 URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向選件會導致無窮迴圈。您應該確保在將使用者重新導向之後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向選件:

   * **包含所有URL引數：** 如果要將出現在上一頁上的所有URL引數都傳播到重新導向的頁面，請滑動切換以啟用此選項。

      例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也會想要傳遞 URL 中的動態參數，因為這是您追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或組織化方法達到您網站的方式。啟用此選項，即可在頁面上重新導向選件 `https://www.mycompany.com/mens.html?emailId=123` 將自動變成 `https://www.mycompany.com/mensShirts.html?emailId=123` 當您在URL方塊中輸入的是 `https://www.mycompany.com/mensShirts.html`.

   * **傳遞mbox工作階段ID：** 必須重新導向至其他網域。 滑動切換以啟用此選項(如果您需要 `sessionId` 自動包含在重新導向中。 只有在測試來自電子郵件的點按或從某個網域到另一個網域的點按時，才需要此屬性。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

      如果您使用第一方和第三方Cookie設定，則跨網域時不需要傳遞mbox工作階段ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

>[!NOTE]
>
>在啟動這些測試前，請聯絡您的實作顧問。

## 在活動中使用重新導向選件

您必須使用套用重新導向選件 [!UICONTROL 表單式體驗撰寫器]. 您目前無法使用VEC套用重新導向選件。

此 [!DNL Adobe Target] [!UICONTROL 表單式體驗撰寫器] 是非視覺體驗和選件建立介面，對於建立在中使用的體驗很有幫助。 [!UICONTROL A/B測試]， [!UICONTROL 體驗鎖定] (XT)， [!UICONTROL Automated Personalization] (AP)，和 [!UICONTROL Recommendations] 視覺化體驗撰寫器無法使用或不實用的活動。 例如，您可以使用 [!UICONTROL 表單式體驗撰寫器] 以建立使用重新導向選件的體驗。

1. 在中建立或編輯活動 [!UICONTROL 表單式體驗撰寫器].

   另請參閱 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md) 以取得詳細的逐步指示。

1. 指定所需位置，並視需要新增任何對象細分。

1. 按一下 **[!UICONTROL 內容]** 區段，然後按一下 **[!UICONTROL 變更重新導向選件]**.

   ![變更重新導向選件選項](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. 從中選擇所需的重新導向選件 [!UICONTROL 選取遠端選件] 對話方塊，然後按一下 **[!UICONTROL 完成]**.

1. 完成活動的設定。

## 訓練影片：表單式撰寫器 ![教學課程徽章](/help/main/assets/tutorial.png)

此影片提供表單式撰寫器的示範，您可以用它來建立重新導向選件。

* 使用表單式體驗撰寫器建立活動
* 瞭解使用表單式體驗撰寫器與可視化體驗撰寫器的時機
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)

---
keywords: 重新導向選件; 建立重新導向選件; 新增 html 選件; 在重新導向中傳入所有 URL 參數; 在重新導向中傳入 mboxSessionId (只有在要重新導向至不同網域時才需要)
description: '瞭解如何在Adobe中建立重定向服務 [!DNL Target] 以使瀏覽器重定向到新頁面。 '
title: 如何建立重定向優惠？
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 48%

---

# 建立重新導向選件

重定向服務 [!DNL Adobe Target] 導致瀏覽器重定向到新頁面。

您可能擁有兩個完全不同的測試頁面，而非只是改變同一頁面中的某部分內容。在這種情況下，您的A/Btest會比較頁A與頁B。設定A/BTest活動，具備兩種經驗：一個指向預設頁A，另一個指向B。該優惠配置為將訪問者重定向到其他頁面。

>[!NOTE]
>
> * 可在 [!UICONTROL 優惠] > [!UICONTROL 代碼優惠] 或 [Forms經驗作曲家](/help/main/c-experiences/form-experience-composer.md)。 無法在Visual Experience Composer(VEC)中建立或應用重定向優惠。 將在 [!DNL Target] 請求位置，因此這些位置很可能不適合於全球 [!DNL Target] 請求。
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

## 從「代碼優惠」頁建立重定向優惠

1. 按一下&#x200B;**[!UICONTROL 「選件」]**，然後選取&#x200B;**[!UICONTROL 「代碼選件」]**&#x200B;索引標籤。

   ![「代碼優惠」頁籤](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]**>**[!UICONTROL 「重新導向選件」]**。

   ![「建立重定向優惠」對話框](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在資產資料庫中快速尋找選件。

1. 輸入唯一內容或您要重新導向的目的地的 URL。此 URL 必須是絕對 URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向選件會導致無窮迴圈。您應該確保在將使用者重新導向之後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向選件:

   * **包括所有URL參數：** 如果希望將上一頁上的所有URL參數傳播到重定向頁面，請滑動切換以啟用此選項。

      例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也會想要傳遞 URL 中的動態參數，因為這是您追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或組織化方法達到您網站的方式。通過啟用此選項，您的重定向服務將在頁面上提供 `https://www.mycompany.com/mens.html?emailId=123` 會自動 `https://www.mycompany.com/mensShirts.html?emailId=123` 在URL框中輸入的所有內容 `https://www.mycompany.com/mensShirts.html`。

   * **傳遞mbox會話ID:** 需要重定向到其他域。 如果希望 `sessionId` 自動包含在重定向中。 僅當您測試從電子郵件的按一下或從一個域到另一個域的按一下時，才需要此選項。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

      如果使用第1和第3方Cookie設定，則跨域時無需傳遞mbox會話ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>
>在啟動這些測試前，請聯絡您的實作顧問。

## 使用基於表單的體驗合成器建立重定向服務

1. 使用建立活動時 [基於表單的體驗作曲家](/help/main/c-experiences/form-experience-composer.md)，選擇顯示 **[!UICONTROL 內容]** 的子菜單。

   ![基於表單的體驗作曲家中的內容部分](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 按一下 **[!UICONTROL 預設內容]** 下拉清單，然後按一下 **[!UICONTROL 更改重定向服務]**。

   ![更改重定向優惠選項](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]**>**[!UICONTROL 「重新導向選件」]**。

   ![「建立重定向優惠」對話框](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在資產資料庫中快速尋找選件。

1. 輸入唯一內容或您要重新導向的目的地的 URL。此 URL 必須是絕對 URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向選件會導致無窮迴圈。您應該確保在將使用者重新導向之後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向選件:

   * **包括所有URL參數：** 如果希望將上一頁上的所有URL參數傳播到重定向頁面，請滑動切換以啟用此選項。

      例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也會想要傳遞 URL 中的動態參數，因為這是您追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或組織化方法達到您網站的方式。通過啟用此選項，您的重定向服務將在頁面上提供 `https://www.mycompany.com/mens.html?emailId=123` 會自動 `https://www.mycompany.com/mensShirts.html?emailId=123` 在URL框中輸入的所有內容 `https://www.mycompany.com/mensShirts.html`。

   * **傳遞mbox會話ID:** 需要重定向到其他域。 如果希望 `sessionId` 自動包含在重定向中。 僅當您測試從電子郵件的按一下或從一個域到另一個域的按一下時，才需要此選項。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

      如果使用第1和第3方Cookie設定，則跨域時無需傳遞mbox會話ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>
>在啟動這些測試前，請聯絡您的實作顧問。

## 在活動中使用重定向服務

您必須使用 [!UICONTROL 基於表單的體驗作曲家]。 您當前無法使用VEC應用重定向服務。

的 [!DNL Adobe Target] [!UICONTROL 基於表單的體驗作曲家] 是一種非視覺體驗，提供建立介面，在建立體驗時非常有用，可在 [!UICONTROL A/BTest]。 [!UICONTROL 體驗目標] (XT), [!UICONTROL Automated Personalization] （美聯社） [!UICONTROL Recommendations] 當視覺體驗作曲家不可用或無法使用時進行活動。 例如，您可以使用 [!UICONTROL 基於表單的體驗作曲家] 建立使用重定向服務的體驗。

1. 建立或編輯 [!UICONTROL 基於表單的體驗作曲家]。

   請參閱 [基於表單的體驗作曲家](/help/main/c-experiences/form-experience-composer.md) 詳細的逐步說明。

1. 指定所需位置並根據需要添加任何訪問群體細化。

1. 按一下 **[!UICONTROL 內容]** ，然後按一下 **[!UICONTROL 更改重定向服務]**。

   ![更改重定向優惠選項](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. 從 [!UICONTROL 選擇遠程優惠] 對話框，然後按一下 **[!UICONTROL 完成]**。

1. 完成活動的設定。

## 培訓視頻：基於表單的作曲家 ![教程徽章](/help/main/assets/tutorial.png)

此視頻提供了基於表單的作曲家的演示，您可以使用它建立重定向產品。

* 使用表單式體驗撰寫器建立活動
* 瞭解使用表單式體驗撰寫器與可視化體驗撰寫器的時機
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)

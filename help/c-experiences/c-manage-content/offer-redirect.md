---
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going to a different domain)
description: 關於 Adobe Target 中導致瀏覽器重新導向至新頁面之重新導向選件的資訊。
title: 建立重新導向選件
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 95%

---


# 建立重新導向選件

重新導向Adobe Target中的選件會導致瀏覽器重新導向至新頁面。

您可能擁有兩個完全不同的測試頁面，而非只是改變同一頁面中的某部分內容。若是這種情況，您的 A/B 測試會比較頁面 A 和頁面 B。使用兩個體驗來設定 A/B 測試促銷活動: 一個指向預設的頁面 A，另一個重新導向至頁面 B。選件則設定為將訪客重新導向至不同頁面。

>[!NOTE]
>
>您無法在 ajax mbox (`mboxUpdate`) 中使用重新導向選件。
>
>針對使用 A4T 活動中的重新導向選件，您的實施必須符合某些最低需求。此外，還有需要您知道的重要資訊。如需詳細資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。

如需設定可重新導向的體驗的相關資訊，請參閱[重新導向至 URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。

重新導向選件會執行 JavaScript 程式碼來重新導向瀏覽器。此選件會使用 `window.location.replace();` 方法，所以訪客被重新導向的來源頁面不會儲存在瀏覽器記錄中。這可讓訪客仍然可以使用瀏覽器中的上一步按鈕。

>[!NOTE]
>
>如果要傳入登陸頁面的反向連結值，建議您使用 HTML 選件，而不要使用重新導向選件。

**若要建立重新導向選件:**

1. 按一下&#x200B;**[!UICONTROL 「選件」]**，然後選取&#x200B;**[!UICONTROL 「代碼選件」]**&#x200B;索引標籤。
1. 按一下&#x200B;**[!UICONTROL 「建立」]**>**[!UICONTROL 「重新導向選件」]**。
1. 輸入選件名稱。
1. 輸入唯一內容或您要重新導向的目的地的 URL。此 URL 必須是絕對 URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向選件會導致無窮迴圈。您應該確保在將使用者重新導向之後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向選件:

* **包含所有 URL 參數:** 如果您要所有出現在上一頁的 URL 參數皆傳播到重新導向的頁面，請勾選此方塊。

   例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也會想要傳遞 URL 中的動態參數，因為這是您追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或組織化方法達到您網站的方式。當您在 URL 方塊中所輸入的是 [!DNL `https://www.mycompany.com/mens.html?emailId=123`]，則勾選此方塊會使在 [!DNL `https://www.mycompany.com/mensShirts.html?emailId=123`] 頁面上的重新導向選件自動變成 [!DNL `https://www.mycompany.com/mensShirts.html`]。

* **傳遞 mbox 工作階段 ID (要重新導向至不同的網域為必要):**&#x200B;如果您要在重新導向中自動包括 `sessionId`，請勾選此方塊。只有在測試來自電子郵件的點按或從在網域間的點按時，才需要勾選此方塊。`sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

   如果使用第一方與第三方的 Cookie 設定，則在跨網域時便不需要傳遞 mbox 工作階段 ID。它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

>[!NOTE]
>
>在啟動這些測試前，請聯絡您的實作顧問。

## 訓練影片：內容儲存庫(4:56)![概述徽章](/help/assets/overview.png)

此影片包括關於管理內容的資訊。

* [Experience Cloud 資產資料庫](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) 與 Target 內容庫之間的連線
* 自訂 HTML 選件
* 可視化體驗撰寫器中的自訂 HTML 選件

>[!VIDEO](https://video.tv.adobe.com/v/17387)

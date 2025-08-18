---
keywords: 重新導向選件；建立重新導向選件；新增html選件；在重新導向中傳遞所有URL引數
description: 瞭解如何建立重新導向選件，以順暢地引導瀏覽器瀏覽新頁面。
title: 如何建立重新導向選件？
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 25%

---

# 建立重新導向產品建議

瞭解如何建立重新導向選件，以順暢地引導瀏覽器瀏覽新頁面。

您可能擁有兩個完全不同的測試頁面，而非只是改變同一頁面中的某部分內容。在此案例中，您的A/B測試會比較頁面A與頁面B。使用兩個體驗來設定[!UICONTROL A/B Test]活動：一個指向預設頁面A，另一個重新導向至頁面B。選件已設定為將訪客重新導向至不同頁面。

>[!NOTE]
>
> * 可以在[!UICONTROL Offers] > [!UICONTROL Code Offers]頁面或[Forms體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)中建立重新導向選件。 您無法在[!UICONTROL Visual Experience Composer] (VEC)中建立或套用重新導向選件。 內容會插入[!DNL Target]要求位置，因此這些位置可能不適合全域[!DNL Target]要求。
>
>* 您無法在AJAX mbox (`mboxUpdate`)中使用重新導向選件。
>
>* 對於使用[[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活動中的重新導向選件，您的實作必須符合某些最低需求。 此外，還有需要您知道的重要資訊。請參閱[重新導向選件 — A4T常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
>
>* 如需設定可重新導向的體驗的相關資訊，請參閱[重新導向至 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。

重新導向產品建議會執行 JavaScript 程式碼來重新導向瀏覽器。此產品建議會使用 `window.location.replace();` 方法，所以訪客被重新導向的來源頁面不會儲存在瀏覽器記錄中。此程式可讓訪客在其瀏覽器中使用「上一步」按鈕。

>[!NOTE]
>
>如果您想要傳遞登入頁面的反向連結值，請使用HTML選件，而非重新導向選件。

## 從[!UICONTROL Code Offers]頁面建立重新導向選件

1. 按一下「**[!UICONTROL Offers]**」，然後選取「**[!UICONTROL Code Offers]**」標籤。
1. 按一下&#x200B;**[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**。
1. 為產品建議提供描述性名稱。

   描述性名稱可協助您和其他人快速在[!UICONTROL Assets]資料庫中找到選件。

1. （視條件而定）如果您有[Target Premium帳戶](/help/main/c-intro/intro.md#premium)，請選取所需的[工作區](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC)。

1. 指定唯一內容或您要重新導向的目的地URL。 此URL必須是絕對URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向產品建議會導致無窮迴圈。確保重新導向使用者後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向產品建議:

   * **[!UICONTROL Include all URL parameters]：**&#x200B;如果您要所有出現在上一頁的URL引數皆傳播到重新導向的頁面，請啟用此選項。

     例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也想要傳遞URL中的動態引數，因為此方法可追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或自然前往您的網站。 啟用此選項後，當您在URL方塊中所輸入的是`https://www.mycompany.com/mens.html?emailId=123`時，頁面`https://www.mycompany.com/mensShirts.html?emailId=123`上的重新導向選件會自動變成`https://www.mycompany.com/mensShirts.html`。

   * **[!UICONTROL Pass mbox session ID]：**&#x200B;必須重新導向至其他網域。 如果您希望`sessionId`自動包含在重新導向中，請滑動切換以啟用此選項。 只有在測試來自電子郵件的點按或從某個網域到另一個網域的點按時，才需要此選項。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

     如果您使用第一方和第三方Cookie設定，則跨網域時不需要傳遞mbox工作階段ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下 **[!UICONTROL Create]**。

>[!IMPORTANT]
>
>在啟動這些測試之前，請洽詢您的實作顧問。

## 使用[!UICONTROL Form-Based Experience Composer]建立重新導向選件

1. 使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)建立活動時，請選取位置以顯示&#x200B;**[!UICONTROL Content]**&#x200B;區段。
1. 按一下&#x200B;**[!UICONTROL Content]**&#x200B;下拉式清單，按一下&#x200B;**[!UICONTROL List]**&#x200B;圖示（ ![清單](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下&#x200B;**[!UICONTROL Change Redirect Offer]**。
1. 按一下&#x200B;**[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**。
1. 為產品建議提供描述性名稱。

   描述性名稱可協助您和其他人快速在[!UICONTROL Assets]資料庫中找到選件。

1. 指定唯一內容或您要重新導向的目的地URL。 此URL必須是絕對URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向產品建議會導致無窮迴圈。確保重新導向使用者後，使用者不會重新取得活動的資格。

1. 選取需要的選項來自訂您的重新導向產品建議:

   * **[!UICONTROL Include all URL parameters]：**&#x200B;如果您想要將上個頁面上存在的所有URL引數都傳播到重新導向的頁面，請切換以啟用此選項。

     例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也想要傳遞URL中的動態引數，因為此方法可追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或自然前往您的網站。 啟用此選項後，當您在URL方塊中所輸入的是`https://www.mycompany.com/mens.html?emailId=123`時，頁面`https://www.mycompany.com/mensShirts.html?emailId=123`上的重新導向選件會自動變成`https://www.mycompany.com/mensShirts.html`。

   * **[!UICONTROL Pass mbox session ID]：**&#x200B;必須重新導向至其他網域。 如果您希望`sessionId`自動包含在重新導向中，請滑動切換以啟用此選項。 只有在測試來自電子郵件的點按或從某個網域到另一個網域的點按時，才需要此選項。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

     如果您使用第一方和第三方Cookie設定，則跨網域時不需要傳遞mbox工作階段ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下 **[!UICONTROL Create]**。

>[!IMPORTANT]
>
>在啟動這些測試之前，請洽詢您的實作顧問。

## 在活動中使用重新導向選件

使用[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)套用重新導向選件。 您目前無法使用[!UICONTROL Visual Experience Composer] (VEC)套用重新導向選件。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer]是非視覺化體驗和選件建立介面，當[!UICONTROL A/B Tests]無法使用或不實用的情況下，它有助於建立可在[!UICONTROL Experience Targeting]、[!UICONTROL Automated Personalization] (XT)、[!UICONTROL Recommendations] (AP)和[!UICONTROL Visual Experience Composer]活動中使用的體驗。 例如，您可能會使用[!UICONTROL Form-Based Experience Composer]來建立使用重新導向選件的體驗。

1. 在[!UICONTROL Form-Based Experience Composer]中建立或編輯活動。

   如需詳細逐步指示，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

1. 指定所需位置，並視需要新增任何對象細分。

1. 按一下&#x200B;**[!UICONTROL Content]**&#x200B;下拉式清單，按一下&#x200B;**[!UICONTROL List]**&#x200B;圖示（ ![清單](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下&#x200B;**[!UICONTROL Change Redirect Offer]**。
1. 從[!UICONTROL Select Redirect Offer]對話方塊中選取所需的重新導向選件，然後按一下&#x200B;**[!UICONTROL Add]**。
1. 完成活動的設定。

---
keywords: 重新導向選件；建立重新導向選件；新增html選件；在重新導向中傳遞所有URL引數
description: 瞭解如何建立重新導向選件，以順暢地引導瀏覽器瀏覽新頁面。
title: 如何建立重新導向選件？
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e42173fb4fe48e1ba74daaa8bae37da5799f9dc7
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 23%

---

# 建立重新導向產品建議

瞭解如何建立重定向服務以無縫引導瀏覽器到新頁面。

您可能擁有兩個完全不同的測試頁面，而非只是改變同一頁面中的某部分內容。在此案例中，您的A/B測試會比較頁面A與頁面B。使用兩個體驗來設定[!UICONTROL A/B Test]活動：一個指向預設頁面A，另一個重新導向至頁面B。選件已設定為將訪客重新導向至不同頁面。

>[!NOTE]
>
> * 可以在[!UICONTROL Offers] > [!UICONTROL Code Offers]頁面或[Forms體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)中建立重新導向選件。 您無法在[!UICONTROL Visual Experience Composer] (VEC)中建立或套用重新導向選件。 內容會插入[!DNL Target]要求位置，因此這些位置可能不適合全域[!DNL Target]要求。
>
>* 您無法在AJAX mbox (`mboxUpdate`)中使用重新導向選件。
>
>* 對於使用[[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活動中的重新導向選件，您的實作必須符合某些最低需求。 此外，還有需要您知道的重要資訊。請參閱[重定向優惠 — A4T常見問題](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)。
>
>* 如需設定可重新導向的體驗的相關資訊，請參閱[重新導向至 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。

重新導向產品建議會執行 JavaScript 程式碼來重新導向瀏覽器。此產品建議會使用 `window.location.replace();` 方法，所以訪客被重新導向的來源頁面不會儲存在瀏覽器記錄中。此過程允許訪問者在其瀏覽器中使用「後退」按鈕。

>[!NOTE]
>
>如果要傳遞登錄頁的引用值，請使用HTML優惠，而不是重定向優惠。

## 從[!UICONTROL Code Offers]頁建立重定向優惠

1. 按一下&#x200B;**[!UICONTROL Offers]**，然後選擇&#x200B;**[!UICONTROL Code Offers]**&#x200B;頁籤。
1. 按一下&#x200B;**[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**。
1. 為產品建議提供描述性名稱。

   描述性名稱可幫助您和其他人在[!UICONTROL Assets]庫中快速找到此服務。

1. （條件）如果您有[目標高級帳戶](/help/main/c-intro/intro.md#premium)，請選擇所需的[工作區](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC)。

1. 指定唯一內容或您要重新導向的目的地URL。 此URL必須是絕對URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向產品建議會導致無窮迴圈。若要避免此問題，請將查詢引數新增至重新導向URL （例如，`?redirect=true`）。 然後，在活動訪問群體或模板規則中，檢查此查詢參數是否不存在。 這可確保用戶在重定向後不再重新獲得活動資格。

1. 選取需要的選項來自訂您的重新導向產品建議:

   * **[!UICONTROL Include all URL parameters]：**&#x200B;如果您要所有出現在上一頁的URL引數皆傳播到重新導向的頁面，請啟用此選項。

     例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您也想要傳遞URL中的動態引數，因為此方法可追蹤使用者是否透過電子郵件、橫幅廣告、搜尋廣告或自然前往您的網站。 啟用此選項後，當您在URL方塊中所輸入的是`https://www.mycompany.com/mens.html?emailId=123`時，頁面`https://www.mycompany.com/mensShirts.html?emailId=123`上的重新導向選件會自動變成`https://www.mycompany.com/mensShirts.html`。

   * **[!UICONTROL Pass mbox session ID]：**&#x200B;必須重新導向至其他網域。 如果您希望`sessionId`自動包含在重新導向中，請滑動切換以啟用此選項。 只有在測試來自電子郵件的點按或從某個網域到另一個網域的點按時，才需要此選項。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

     如果使用第1和第3方Cookie設定，則跨域時無需傳遞mbox會話ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下 **[!UICONTROL Create]**。

>[!IMPORTANT]
>
>在啟動這些測試之前，請咨詢您的實施顧問。

## 使用[!UICONTROL Form-Based Experience Composer]建立重定向服務

1. 使用[基於表單的體驗作曲家](/help/main/c-experiences/form-experience-composer.md)建立活動時，選擇顯示&#x200B;**[!UICONTROL Content]**&#x200B;節的位置。
1. 按一下&#x200B;**[!UICONTROL Content]**&#x200B;下拉清單，按一下&#x200B;**[!UICONTROL List]**&#x200B;表徵圖（![清單](/help/main/assets/icons/MoreSmallList.svg)），然後按一下&#x200B;**[!UICONTROL Change Redirect Offer]**。
1. 按一下&#x200B;**[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**。
1. 為產品建議提供描述性名稱。

   描述性名稱可幫助您和其他人在[!UICONTROL Assets]庫中快速找到此服務。

1. 指定要重定向到的唯一內容或目標的URL。 此URL必須是絕對URL。

   >[!NOTE]
   >
   >如果重新導向 URL 也會讓使用者符合相同活動的資格，重新導向產品建議會導致無窮迴圈。若要避免此問題，請將查詢引數新增至重新導向URL （例如，`?redirect=true`）。 然後，在活動訪問群體或模板規則中，檢查此查詢參數是否不存在。 這可確保用戶在重定向後不再重新獲得活動資格。

1. 選取需要的選項來自訂您的重新導向產品建議:

   * **[!UICONTROL Include all URL parameters]:**&#x200B;如果希望將上一頁上存在的所有URL參數傳播到重定向頁面，請滑動切換以啟用此選項。

     例如，您要將使用者直接從男性頁面重新導向至男性襯衫類別頁面。您還希望傳遞URL中的動態參數，因為此方法是您跟蹤通過電子郵件、橫幅廣告、搜索廣告或有機方式訪問您站點的人員的方式。 啟用此選項後，當您在URL方塊中所輸入的是`https://www.mycompany.com/mens.html?emailId=123`時，頁面`https://www.mycompany.com/mensShirts.html?emailId=123`上的重新導向選件會自動變成`https://www.mycompany.com/mensShirts.html`。

   * **[!UICONTROL Pass mbox session ID]:**&#x200B;需要重定向到其他域。 如果希望將`sessionId`自動包含在重定向中，請滑動切換以啟用此選項。 僅當您測試從電子郵件中按一下或從一個域到另一個域的按一下時，才需要此選項。 `sessionId` 會比對訪客的 Cookie，這樣就可以繼續追蹤訪客，並顯示正確的內容。

     如果使用第1和第3方Cookie設定，則跨域時無需傳遞mbox會話ID。 它會在第三方 Cookie 中持續存在，所以不需要出現在 URL 中。

1. 按一下 **[!UICONTROL Create]**。

>[!IMPORTANT]
>
>在啟動這些測試之前，請咨詢您的實施顧問。

## 在活動中使用重定向服務

使用[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)應用重定向服務。 您當前無法使用[!UICONTROL Visual Experience Composer]&#x200B;(VEC)應用重定向服務。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer]是非視覺體驗，當[!UICONTROL A/B Tests]不可用或不實用時，它可用於建立在[!UICONTROL Experience Targeting]、[!UICONTROL Automated Personalization]&#x200B;(XT)、[!UICONTROL Recommendations]&#x200B;(AP)和[!UICONTROL Visual Experience Composer]活動中使用的體驗。 例如，您可能使用[!UICONTROL Form-Based Experience Composer]建立使用重定向優惠的體驗。

1. 在[!UICONTROL Form-Based Experience Composer]中建立或編輯活動。

   如需詳細逐步指示，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

1. 指定所需位置，並視需要新增任何對象細分。

1. 按一下&#x200B;**[!UICONTROL Content]**&#x200B;下拉式清單，按一下&#x200B;**[!UICONTROL List]**&#x200B;圖示（ ![清單](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下&#x200B;**[!UICONTROL Change Redirect Offer]**。
1. 從[!UICONTROL Select Redirect Offer]對話方塊中選取所需的重新導向選件，然後按一下&#x200B;**[!UICONTROL Add]**。
1. 完成活動的設定。

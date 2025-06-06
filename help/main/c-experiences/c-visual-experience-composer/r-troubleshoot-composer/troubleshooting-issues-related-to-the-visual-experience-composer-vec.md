---
keywords: 鎖定目標；視覺化體驗撰寫器； VEC；疑難排解視覺化體驗撰寫器；疑難排解； TLS； TLS 1.2
description: 瞭解如何疑難排解[!UICONTROL Visual Experience Composer] (VEC)中的問題。
title: 如何疑難排解[!UICONTROL Visual Experience Composer]的相關問題？
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: ef5df0ae37ca1d07c0e51c06ed78739b2d2983fc
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 23%

---

# 疑難排解[!UICONTROL Visual Experience Composer]的相關問題

顯示在某些情況下，有時候會在[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)中發生問題。

## 當我在[!UICONTROL Visual Experience Composer]中開啟我的網站時，[!DNL Target]資料庫未載入。 (僅限 VEC) {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

+++詳細資料
在[!UICONTROL Visual Experience Composer]中開啟網站時，[!DNL Target]新增兩個引數（`mboxEdit=1`和`mboxDisable=1`）。

如果您的網站（特別是單頁應用程式）在從一個頁面導覽至另一個頁面時（而沒有重新載入頁面），修剪引數或實際移除引數，[!DNL Target]功能會中斷，且[!DNL Target]資料庫不會載入。

若要避免此問題，請確保您不會修剪或移除這兩個參數。

+++

## 我的頁面不會在 EEC 中開啟，或載入緩慢。活動或體驗在 VEC 中載入緩慢。(僅限 VEC) {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

+++詳細資料
數個問題可能會影響[!UICONTROL Target]體驗撰寫器中的頁面效能。 一些常見問題包括:

* 您的頁面上沒有 mbox。
* 您的網站使用 Proxy 封鎖，它不允許在這兩個體驗撰寫器中開啟頁面。
* 您的網站不允許在 iFrame 中開啟網站本身。

如果[!UICONTROL Enhanced Experience Composer]發生問題，請嘗試關閉[!UICONTROL Enhanced Experience Composer]並改用[!UICONTROL Visual Experience Composer]。

若要停用[!UICONTROL Enhanced Experience Composer]，請前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**&#x200B;並關閉&#x200B;**[!UICONTROL Enable Enhanced Experience Composer]**&#x200B;選項。

有些使用者在主控台中看見下列錯誤訊息:

![Console 錯誤訊息](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

如果[!UICONTROL Visual Experience Composer]和[!UICONTROL Enhanced Experience Composer]都無法運作，請使用瀏覽器擴充功能，例如[!DNL Requestly] （[!DNL Chrome]或[!DNL Firefox]）或Modify Response Headers (Firefox)，此擴充功能可覆寫網站的X-Frames標頭選項，並允許這些選項載入iFrames中，以啟用VEC。 如果您無法使用瀏覽器延伸模組，請使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

>[!NOTE]
>
>除了下列資訊外，您還可以為[!DNL Google Chrome]使用[[!DNL Adobe Target] [!UICONTROL Visual Editing Helper]副檔名](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

>[!NOTE]
>
>這些外掛程式僅應用於 VEC 編輯環境中。
>
>對於[!DNL Requestly]擴充功能，每當需要移除標題時，您應該執行下列其中一項作業：
>
>* 為要在 VEC 中開啟的 URL 新增 URL 規則，如此一來，便僅有那些 URL 的標頭會移除。
>
>* 在 VEC 中編輯時啟用規則，並在不使用 VEC 時停用規則。
>
>對於[!UICONTROL Modify Response Header]副檔名([!DNL Firefox])，因為您無法新增URL規則，所以必須執行下列動作：
>
>* 在 VEC 中編輯時啟用規則，並在不使用 VEC 時停用規則。

**若要在[!DNL Chrome]或[!DNL Firefox]上使用[!DNL Requestly]延伸模組：**

1. 關閉[!UICONTROL Enhanced Experienced Composer]。
1. 在[!DNL Chrome]或[!DNL Firefox]上安裝[!DNL Requestly]瀏覽器延伸模組。
1. 開啟擴充功能並使用下列項目來設定它:
1. 選取&#x200B;**[!UICONTROL Modify headers]**。
1. 輸入下列:

   * 規則名稱
   * 修改規則

      * 將&#x200B;**[!UICONTROL Add]**&#x200B;切換為&#x200B;**[!UICONTROL Remove]**。
      * 將&#x200B;**[!UICONTROL Request]**&#x200B;切換為&#x200B;**[!UICONTROL Response]**。
      * 輸入 &quot;X-Frame-Options&quot; 作為標頭名稱。
      * 重複先前的步驟並輸入 &quot;x-frame-options&quot; 作為標頭名稱。

        >[!NOTE]
        >
        >透過[!DNL Requestly]處理的標頭須區分大小寫。

      * 將&#x200B;**[!UICONTROL Equals]**&#x200B;變更為&#x200B;**[!UICONTROL Contains]**&#x200B;作為來源URL的條件，並輸入您嘗試在VEC中載入之活動的URL。

     ![chrome_extension影像](assets/chrome_extension.png)

1. 按一下 **[!UICONTROL Save]**。

   ![要求影像](assets/requestly.png)

   您現在應該能夠使用[!UICONTROL Visual Experience Composer]快速載入頁面。

**若要在[!UICONTROL Firefox]上使用[!DNL Modify Response Headers]延伸模組：**

1. 在[!DNL Firefox]上安裝[!UICONTROL Modify Response Headers]並重新啟動瀏覽器。
1. 從您的[!DNL Firefox]擴充功能中，選取Modify Response Headers擴充功能。
1. 按一下 **[!UICONTROL Preferences]**。
1. 從[!UICONTROL Action]下拉式清單中選取&#x200B;**[!UICONTROL Filter]**。
1. 在[!UICONTROL Header Name]欄位中，輸入： **[!UICONTROL X-Frame-Options]**。
1. 重複步驟4和5，新增具有&#x200B;**[!UICONTROL x-frame-options]**&#x200B;的篩選器。
1. 按一下 **[!UICONTROL Add]**。
1. 按一下 **[!UICONTROL Start]**。

![Firefox擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

設定擴充功能後，請開啟[!DNL Target]。 您的頁面現在應在[!UICONTROL Visual Experience Composer]中載入，即使[!UICONTROL Enhanced Experience Composer]已停用。

+++

## 我的頁面未在 VEC 中顯示 (僅限 VEC) {#does-not-load}

+++詳細資料
* 最新版本的擴充功能可確保與VEC的最佳相容性： [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper extension]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

  若要確認您是否使用最新版本，請前往[!UICONTROL Extensions] > [!UICONTROL Manage Extensions]，然後按一下[!UICONTROL Details]。

* [!UICONTROL Visual Experience Composer]需要編寫程式庫，才能在網頁上執行修改。 這些程式庫內嵌於at.js程式庫中，並在每次使用VEC時由擴充功能從[!DNL Adobe]伺服器下載。

  無論at.js或[!DNL Adobe Experience Platform Web SDK]是否已包含在頁面中，擴充功能都會下載at.js資料庫。

  確保未將無效的變更新增到[!UICONTROL Administration] > [!UICONTROL Implementation]區段中設定的at.js標頭。

* 確保網頁內嵌於iFrame中時，不會封鎖載入的必要請求。 這包括使用frame-ancestors CSP指示詞或內嵌在客戶網站中的自訂JS程式碼、meta HTML標籤或x-frame-options標頭。

* 請確認網頁的Javascript不會干擾編寫程式庫。 請勿使用或包含使用下列保留名稱的檔案：

   * `target-vec-helper.js`
   * `target-vec.js`
   * `target.js`
   * `admin.css`
   * `sizzle.js`
   * `mixContentCheck.html`

     此外，意外覆寫這些檔案中定義的變數或事件可能會導致VEC發生問題。

* 瀏覽器正在封鎖安全網站上不安全的頁面。

  按一下瀏覽器位址列URL左側的圖示，然後按一下&#x200B;**[!UICONTROL Disable protection on this page]**

* 您輸入了無效的 URL。
* 如果您的網站無法在VEC中載入，或發生意外行為，可能的修正是在嘗試在[!DNL Target]中載入網站之前，先在瀏覽器中接受您網站上的Cookie。

+++

## 當我使用[!UICONTROL Browse]模式時，VEC似乎損毀。 (僅限 VEC) {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

+++詳細資料
使用[!UICONTROL Browse]模式時，如果您存取的URL未實作[!DNL Target]資料庫([at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank}或[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank})或包含frame-buster標頭，VEC會顯示為損毀。 由於瀏覽器安全性的顧慮，[!DNL Target]無法正確存取您導覽到的URL，或如果頁面載入，VEC URL無法一致更新。

發生此問題的原因是VEC在`<iframe>`中載入網頁。 由於相同來源原則，瀏覽器的目前安全性機制導致[!DNL Target] UI無法存取指定框架的專案。 瀏覽器會封鎖嘗試存取具有不同來源且包含`location.href`等資訊之框架的Script。

您必須使用新的[Visual Editing Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)，將[!DNL Target]資料庫插入頁面，才能以最佳方式瀏覽頁面。

+++

## [!UICONTROL Visual Experience Composer]中的CSS衝突所造成的問題

+++詳細資料
驗證在編輯器中載入網頁時，是否有任何可能影響可見性的CSS檔案。 例如，在頁面本文上使用`overflow: hidden`屬性可能會導致捲動問題或觸發點選事件，這些事件可能會干擾編寫功能表。

+++

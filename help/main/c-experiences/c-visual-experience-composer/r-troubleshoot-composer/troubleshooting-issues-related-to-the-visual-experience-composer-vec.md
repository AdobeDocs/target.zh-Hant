---
keywords: 鎖定目標；視覺化體驗撰寫器； VEC；疑難排解視覺化體驗撰寫器；疑難排解； TLS； TLS 1.2
description: 瞭解如何疑難排解中的問題 [!UICONTROL Visual Experience Composer] (VEC)。
title: 如何疑難排解相關問題 [!UICONTROL Visual Experience Composer]？
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: 7c0d0154b81fbd3f89a82b31cd18541a7f0ea1a7
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 24%

---

# 疑難排解相關問題 [!UICONTROL Visual Experience Composer]

顯示問題有時發生在 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)在一定條件下。

## 當我在 [!UICONTROL Visual Experience Composer]，則 [!DNL Target] 程式庫不載入。 (僅限 VEC) {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

[!DNL Target] 新增兩個引數(`mboxEdit=1` 和 `mboxDisable=1`)在中開啟網站時 [!UICONTROL Visual Experience Composer].

如果您的網站（特別是單頁應用程式）在從一個頁面導覽至另一個頁面時（而沒有重新載入頁面），修剪引數或實際上將引數移除， [!DNL Target] 功能中斷和 [!DNL Target] 程式庫不載入。

若要避免此問題，請確保您不會修剪或移除這兩個參數。

## 我的頁面不會在 EEC 中開啟，或載入緩慢。活動或體驗在 VEC 中載入緩慢。(僅限 VEC) {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

有幾個問題可能會影響 [!UICONTROL Target] 體驗撰寫器。 一些常見問題包括:

* 您的頁面上沒有 mbox。
* 您的網站使用 Proxy 封鎖，它不允許在這兩個體驗撰寫器中開啟頁面。
* 您的網站不允許在 iFrame 中開啟網站本身。

如果發生問題 [!UICONTROL Enhanced Experience Composer]，請嘗試關閉 [!UICONTROL Enhanced Experience Composer] 並使用 [!UICONTROL Visual Experience Composer] 而非。

若要停用 [!UICONTROL Enhanced Experience Composer]，前往 **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** 並關閉 **[!UICONTROL Enable Enhanced Experience Composer]** 選項。

有些使用者在主控台中看見下列錯誤訊息:

![Console 錯誤訊息](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

如果兩者都不 [!UICONTROL Visual Experience Composer] 也不是 [!UICONTROL Enhanced Experience Composer] 有效，使用瀏覽器擴充功能，例如 [!DNL Requestly] ([!DNL Chrome] 或 [!DNL Firefox])，或修改可覆寫網站X-Frames標題選項並允許載入iFrames中的回應標題(Firefox)，進而啟用VEC。 如果您無法使用瀏覽器擴充功能，請使用 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>除了下列資訊外，您還可以使用 [[!DNL Adobe Target] [!UICONTROL Visual Editing Helper] 副檔名](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) 的 [!DNL Google Chrome].


>[!NOTE]
>
>這些外掛程式僅應用於 VEC 編輯環境中。
>
>對於 [!DNL Requestly] 擴充功能時，每當需要移除標題時，您應執行下列其中一項作業：
>
>* 為要在 VEC 中開啟的 URL 新增 URL 規則，如此一來，便僅有那些 URL 的標頭會移除。
>
>* 在 VEC 中編輯時啟用規則，並在不使用 VEC 時停用規則。
>
>對於 [!UICONTROL Modify Response Header] 副檔名([!DNL Firefox])，因為您無法新增URL規則，您必須執行下列動作：
>
>* 在 VEC 中編輯時啟用規則，並在不使用 VEC 時停用規則。

**若要使用 [!DNL Requestly] 擴充功能於 [!DNL Chrome] 或 [!DNL Firefox]：**

1. 關閉 [!UICONTROL Enhanced Experienced Composer].
1. 安裝 [!DNL Requestly] 瀏覽器延伸模組於 [!DNL Chrome] 或 [!DNL Firefox].
1. 開啟擴充功能並使用下列項目來設定它:
1. 選取 **[!UICONTROL Modify headers]**.
1. 輸入下列:

   * 規則名稱
   * 修改規則

      * 切換 **[!UICONTROL Add]** 至 **[!UICONTROL Remove]**.
      * 切換 **[!UICONTROL Request]** 至 **[!UICONTROL Response]**.
      * 輸入 &quot;X-Frame-Options&quot; 作為標頭名稱。
      * 重複先前的步驟並輸入 &quot;x-frame-options&quot; 作為標頭名稱。

        >[!NOTE]
        >
        >處理的標頭 [!DNL Requestly] 區分大小寫。

      * 變更 **[!UICONTROL Equals]** 至 **[!UICONTROL Contains]** 作為來源URL的條件，並輸入您嘗試在VEC中載入之活動的URL。

     ![chrome_extension圖片](assets/chrome_extension.png)

1. 按一下 **[!UICONTROL Save]**。

   ![requestly影像](assets/requestly.png)

   您現在應該可以使用快速載入頁面 [!UICONTROL Visual Experience Composer].

**若要使用 [!DNL Modify Response Headers] 擴充功能於 [!UICONTROL Firefox]：**

1. 安裝 [!UICONTROL Modify Response Headers] 於 [!DNL Firefox] 並重新啟動瀏覽器。
1. 從您的 [!DNL Firefox] 擴充功能中，選取Modify Response Headers擴充功能。
1. 按一下 **[!UICONTROL Preferences]**。
1. 選取 **[!UICONTROL Filter]** 從 [!UICONTROL Action] 下拉式清單。
1. 在 [!UICONTROL Header Name] 欄位，輸入： **[!UICONTROL X-Frame-Options]**.
1. 重複步驟4和5來新增篩選器 **[!UICONTROL x-frame-options]**.
1. 按一下 **[!UICONTROL Add]**。
1. 按一下 **[!UICONTROL Start]**。

![Firefox擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

設定擴充功能後，請開啟 [!DNL Target]. 您的頁面現在應載入到 [!UICONTROL Visual Experience Composer]，即使 [!UICONTROL Enhanced Experience Composer] 已停用。

## 我的頁面未在 VEC 中顯示 (僅限 VEC) {#does-not-load}

* 最新版本的擴充功能可確保與VEC的最佳相容性： [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper extension]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

  若要確認您是否使用最新版本，請前往 [!UICONTROL Extensions] > [!UICONTROL Manage Extensions] 然後按一下 [!UICONTROL Details].

* 此 [!UICONTROL Visual Experience Composer] 需要編寫程式庫，才能在網頁上執行修改。 這些程式庫內嵌於at.js程式庫中，並由中的擴充功能下載 [!DNL Adobe] 伺服器。

  擴充功能會下載at.js資料庫，不論at.js或 [!DNL Adobe Experience Platform Web SDK] 已包含在頁面中。

  確保沒有將無效的變更新增到中設定的at.js標頭 [!UICONTROL Administration] > [!UICONTROL Implementation] 區段。

* 確保網頁內嵌於iFrame中時，不會封鎖載入的必要請求。 這包括使用frame-ancestors CSP指示詞或內嵌在客戶網站中的自訂JS程式碼、中繼HTML標籤或x-frame-options標頭。

* 請確認網頁的Javascript不會干擾編寫程式庫。 請勿使用或包含使用下列保留名稱的檔案：

   * `target-vec-helper.js`
   * `target-vec.js`
   * `target.js`
   * `admin.css`
   * `sizzle.js`
   * `mixContentCheck.html`

     此外，意外覆寫這些檔案中定義的變數或事件可能會導致VEC發生問題。

* 瀏覽器正在封鎖安全網站上不安全的頁面。

  按一下瀏覽器位址列URL左側的圖示，然後按一下 **[!UICONTROL Disable protection on this page]**

* 您輸入了無效的 URL。
* 如果您的網站無法在VEC中載入，或行為發生意外，潛在的修正措施是先在瀏覽器中接受您網站上的Cookie，然後再嘗試在中載入網站 [!DNL Target].

## 當我使用瀏覽模式時，VEC 似乎損毀。(僅限 VEC) {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

使用瀏覽模式時，如果您存取的URL沒有 [!DNL Target] 已實作程式庫([at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank})或包含frame-buster標頭，則VEC會顯示為已損毀。 由於瀏覽器安全性的顧慮， [!DNL Target] 無法正確存取您導覽至的URL，或如果頁面載入，VEC URL無法一致更新。

發生此問題是因為VEC在中載入網頁 `<iframe>`. 目前瀏覽器的安全機制防止 [!DNL Target] UI無法存取指定框架元素，因為相同來源原則。 瀏覽器會封鎖嘗試存取具有不同來源且包含 `location.href`.

您必須使用新的 [Visual Editing Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) （建議）或 [舊擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) 以插入 [!DNL Target] 以最佳方式瀏覽頁面。

## 中由CSS衝突造成的問題 [!UICONTROL Visual Experience Composer]

驗證在編輯器中載入網頁時，是否有任何可能影響可見性的CSS檔案。 例如，使用 `overflow: hidden` 屬性在頁面本文上可能會導致捲動問題或觸發點選事件，這些事件可能會干擾編寫選單。

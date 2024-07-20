---
keywords: 鎖定目標；視覺化體驗撰寫器；白名單；允許清單；允許清單；增強視覺化體驗撰寫器； VEC；疑難排解視覺化體驗撰寫器；疑難排解； EEC；增強體驗撰寫器； TLS； TLS 1.2
description: 瞭解如何疑難排解Adobe [!DNL Target] 視覺化體驗撰寫器(VEC)和增強體驗撰寫器(EEC)在某些情況下有時發生的問題。
title: 如何疑難排解視覺化體驗撰寫器和增強體驗撰寫器的相關問題？
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1401'
ht-degree: 45%

---

# 疑難排解[!UICONTROL Visual Experience Composer]和[!UICONTROL Enhanced Experience Composer]的相關問題

在某些情況下，[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)和[!UICONTROL Enhanced Experience Composer] (EEC)有時會發生顯示問題和其他問題。

## Google Chrome SameSite cookie 執行政策對 VEC 和 EEC 有何影響？ {#samesite}

使用下列Chrome版本時，請注意會影響VEC和EEC的變更：

>[!NOTE]
>
>下列變更會影響下列所有三項更新：
>
> * *無法*&#x200B;在沒有安裝VEC Helper擴充功能並啟用網站受密碼保護頁面的情況下，使用VEC。 您的網站登入Cookie會視為第三方Cookie，且不會在瀏覽模式的VEC編輯器中，與登入要求一併傳送。 唯一的例外是您的網站登入Cookie已設定`SameSite=None`和`Secure`屬性。

**Chrome 94 （2021年9月21日）**：由於Chrome 94版本（2021年9月21日）即將推出的變更，下列變更將影響具有Chrome 94+瀏覽器版本的所有使用者：

* 將移除命令列旗標`--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`。

**Chrome 91 （2021年5月25日）**：隨著變更在Chrome 91版本（2021年5月25日）上實施，下列變更將會影響具有Chrome 91+瀏覽器版本的所有使用者：

* 旗標`#same-site-by-default-cookies`和`#cookies-without-same-site-must-be-secure`已從`chrome://flags`中移除。 此行為現在預設為啟用。

**Chrome 80 （2020年8月）**：隨著變更在2020年8月實作，所有具有Chrome 80+瀏覽器版本的使用者：

* 編輯活動時，*無法*&#x200B;下載[!DNL Target]資料庫嗎（當這些資料庫不在網站上時）。 這是因為下載呼叫是從客戶網域向安全的[!DNL Adobe]網域發出的，而且會以未經驗證的方式遭到拒絕。
* EEC無法為`adobemc.com domain`上的Cookie設定SameSite屬性，因此不會為所有使用者&#x200B;*設定*&#x200B;函式。 若沒有此屬性，瀏覽器會拒絕這些Cookie，導致EEC失敗。

### 判斷封鎖哪些Cookie

若要判斷哪些Cookie因SameSite Cookie執行政策而遭到封鎖，請使用Chrome中的開發人員工具。

1. 若要存取開發人員工具，在Chrome中檢視VEC時，請按一下Chrome > **[!UICONTROL More Tools]** > **[!UICONTROL Developer Tools]**&#x200B;右上角的&#x200B;**[!UICONTROL ellipsis]**&#x200B;圖示。
1. 按一下「**[!UICONTROL Network]**」標籤> ，然後尋找封鎖的Cookie。

   >[!NOTE]
   >
   >使用&#x200B;**[!UICONTROL Has blocked cookies]**&#x200B;核取方塊可更輕鬆找到封鎖的Cookie。

   下圖顯示封鎖的Cookie：

   ![開發人員工具>網路索引標籤顯示封鎖的Cookie](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### [!DNL Adobe Target] VEC Helper擴充功能

從0.7.1版開始，當在擴充功能UI中開啟「Cookie」切換開關時，[!DNL Adobe Target] VEC Helper瀏覽器擴充功能會將`SameSite=None`和`Secure`屬性新增至源自於VEC內編輯之網頁的回應上的所有Cookie：

![Adobe Target VEC Helper擴充功能UIAdobe Target VEC Helper擴充功能UI](assets/cookies-vec-helper.png)

### 替代和因應措施

使用下列其中一個選項，確保VEC和EEC可繼續如預期運作：

* 下載並使用更新的[VEC Helper擴充功能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en)。
* 使用Mozilla Firefox瀏覽器。 Firefox尚未強制執行此原則。
* 使用下列旗標從命令列執行Google Chrome，直到2021年9月21日。 9月21日之後，需要Cookie的功能在VEC中將不再運作，例如登入或Cookie同意快顯視窗。 如果您更新至Chrome 94，則必須在您的網站上手動產生具有`SameSite=none`和`Secure`的Cookie。

  ```
  --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
  ```

## [!DNL Target]是否支援多重層級iframe？

[!DNL Target]不支援多重層級iframe。 如果您的網站載入具有子項iframe的iframe，at.js只會與父項iframe互動。 [!DNL Target]資料庫不會與子項iframe互動。

作為因應措施，您可以使用子項 iframe 的 URL 在體驗中新增頁面。

## 當我嘗試編輯頁面時，我只看到了進度環而非我的頁面。(VEC 和 EEC) {#section_313001039F79446DB28C70D932AF5F58}

如果URL包含#個字元，就可能發生這種情況。 若要修正問題，請在可視化體驗撰寫器中切換至「瀏覽」模式，然後切換回「撰寫」模式。進度環應該會消失，並且頁面應該會載入。

## 內容安全性原則(CSP)標頭會封鎖我網站上的[!DNL Target]資料庫。 (VEC 和 EEC) {#section_89A30C7A213D43BFA0822E66B482B803}

如果您的網站的 CSP 標頭封鎖 Target 資料庫，然後載入網站但防止編輯，請確保 Target 資料庫未遭到封鎖。

>[!NOTE]
>
>除了下列資訊外，您還可以使用適用於 Google Chrome 的 [Adobe Target VEC Helper 瀏覽器擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

![cps_headers影像](assets/cps_headers.png)

作為解決方案，您可以設定 Requestly 規則來移除 CSP 標頭，如下所示:

![cps_headers_2圖片](assets/cps_headers_2.png)

您可以為造成資源無法在 VEC 內載入的任何標頭設定類似的 Requestly 規則。

對於 Requestly，一旦需要移除標頭，您就應該執行下列任一動作:

* 為要在 VEC 中開啟的 URL 新增 URL 規則，如此一來，便僅有那些 URL 的標頭會移除。
* 在 VEC 中編輯時啟用規則，並在不使用 VEC 時停用規則。

## 重新編輯已儲存的活動時，VEC 或 EEC 似乎損毀或未初始化。(VEC 和 EEC) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

如果在定義體驗之後，於可視化體驗撰寫器外部變更了網站，開啟活動進行重新編輯時，會找不到稍早採取動作所在的選取器。頁面似乎損毀，並且未顯示警告。

## VEC 或 EEC 未顯示我的旋轉橫幅和包含 JavaScript 的其他內容。(VEC 和 EEC) {#section_8B5BE6EB050B42D6A14A054724C41330}

依預設，可視化體驗撰寫器會封鎖 JavaScript 元素。如果您在可視化體驗撰寫器設定中停用 JavaScript，則可以使用這些元素。根據網站的設定方式，一些項目可能會繼續不正確地顯示或保持無法使用。

## 在頁面上變更一個元素時，變更了多個元素。(VEC 和 EEC) {#section_309188ACF34942989BE473F63C5710AF}

如果您在頁面的多個元素上使用相同的 DOM 元素 ID，變更這些元素中的一個會變更具有該 ID 的所有元素。若要防止發生此問題，一個 ID 應該僅在每個頁面上使用一次。此慣例為標準HTML最佳慣例。 如需詳細資訊，請參閱[頁面修改案例](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 我無法編輯 iFrame-busting 網站的體驗。(VEC 和 EEC) {#section_9FE266B964314F2EB75604B4D7047200}

此問題可透過啟用增強體驗撰寫器來解決。按一下&#x200B;**[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]**，然後選取可啟用增強體驗撰寫器的核取方塊。 增強體驗撰寫器使用 Adobe 管理的 Proxy 來載入您的頁面進行編輯。此Proxy可讓您在iFrame-busting網站上進行編輯，也可讓您在尚未新增Adobe Target程式碼的網站和頁面上進行編輯。 在新增程式碼之後，才會將活動傳送至網站。有些網站可能無法透過增強體驗撰寫器載入，在此情況下，您可以取消勾選此選項，以透過iFrame載入視覺化體驗撰寫器。

>[!NOTE]
>
>對於您在本機託管的頁面或無法從您的網路外部存取的頁面，Adobe Proxy 伺服器無法存取這類頁面，且無法在 EEC 中開啟。這些頁面可能包括測試 URL、使用者接受測試 (UAT) URL，或本機主控的頁面。

## 我想要在尚未完成 mbox/target 實施的頁面上設定測試。(VEC 和 EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

請參閱以上的「我無法編輯 iFrame-busting 網站的體驗」。

## 具有「編輯文字/HTML」或「變更文字/HTML」的粗體和斜體文字樣式未在我的頁面上顯示。有時文字會在套用這些樣式變更之後消失。(VEC 和 EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

如果您在視覺化體驗撰寫器中對A/B或體驗鎖定目標活動使用&#x200B;**[!UICONTROL Edit Text/HTML]**，或對Automated Personalization或多變數測試活動使用&#x200B;**[!UICONTROL Change Text/HTML]**，以讓文字粗體或斜體，這些樣式可能無法在頁面上套用，或文字會從視覺化體驗撰寫器中的頁面消失。 之所以發生此情況，是因為RTF編輯器套用這些樣式的方式，可能會干擾網站標籤。

如果您看見此問題:

1. 按一下RTF編輯器中的&#x200B;**[!UICONTROL HTML]**&#x200B;按鈕以進入來源編輯模式。
1. 尋找樣式文字元素。

   * 針對粗體文字，將 `<strong>` 元素變更為 `<b>`。

   * 針對斜體文字，將 `<em>` 元素變更為 `<i>`。

## 針對自動個人化活動，影像交換在 VEC 或 EEC 中似乎損毀。(VEC 和 EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

新增影像選件至位置以取得 VEC 或 EEC 中原始影像空間的完整尺寸。在傳遞時，影像不會展開並且如原樣顯示，因此對傳遞沒有影響。

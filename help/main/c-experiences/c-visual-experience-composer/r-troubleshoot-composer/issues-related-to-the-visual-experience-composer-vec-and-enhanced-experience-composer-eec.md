---
keywords: 鎖定目標；視覺化體驗撰寫器；白名單；允許清單；允許清單；增強視覺化體驗撰寫器； VEC；疑難排解視覺化體驗撰寫器；疑難排解； EEC；增強體驗撰寫器； TLS； TLS 1.2
description: 瞭解如何疑難排解 [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC)和[!UICONTROL Enhanced Experience Composer] (EEC)在某些情況下有時會發生的問題。
title: 如何疑難排解[!UICONTROL Visual Experience Composer]和[!UICONTROL Enhanced Experience Composer]的相關問題？
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: ef5df0ae37ca1d07c0e51c06ed78739b2d2983fc
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 26%

---

# 疑難排解[!DNL Adobe Target] [!UICONTROL Visual Experience Composer]和[!UICONTROL Enhanced Experience Composer]的相關問題

在某些情況下，[!DNL Target] [!UICONTROL Visual Experience Composer] (VEC)和[!UICONTROL Enhanced Experience Composer] (EEC)有時會發生顯示問題和其他問題。

## Google Chrome SameSite cookie 執行政策對 VEC 和 EEC 有何影響？ {#samesite}

+++詳細資料
使用下列[!DNL Chrome]發行版本時，請注意會影響VEC和EEC的變更：

>[!NOTE]
>
>下列變更會影響下列所有三項更新：
>
> * *無法*&#x200B;在沒有安裝[VEC Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)且已啟用網站受密碼保護頁面的情況下，使用VEC。 您的網站登入Cookie會視為第三方Cookie，不會在[!UICONTROL Browse]模式的VEC編輯器中連同登入要求一起傳送。 唯一的例外是您的網站登入Cookie已設定`SameSite=None`和`Secure`屬性。

**Chrome 94 （2021年9月21日）**：由於Chrome 94版本（2021年9月21日）即將推出的變更，下列變更將影響具有Chrome 94+瀏覽器版本的所有使用者：

* 將移除命令列旗標`--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`。

**Chrome 91 （2021年5月25日）**：隨著變更在Chrome 91版本（2021年5月25日）上實施，下列變更將會影響具有Chrome 91+瀏覽器版本的所有使用者：

* 旗標`#same-site-by-default-cookies`和`#cookies-without-same-site-must-be-secure`已從`chrome://flags`中移除。 此行為現在預設為啟用。

**Chrome 80 （2020年8月）**：隨著變更在2020年8月實作，所有具有Chrome 80+瀏覽器版本的使用者：

* 編輯活動時，*無法*&#x200B;下載[!DNL Target]資料庫嗎（當這些資料庫不在網站上時）。 這是因為下載呼叫是從客戶網域向安全的[!DNL Adobe]網域發出的，而且會以未經驗證的方式遭到拒絕。

* EEC無法為`adobemc.com domain`上的Cookie設定SameSite屬性，因此不會為所有使用者&#x200B;*設定*&#x200B;函式。 若沒有此屬性，瀏覽器會拒絕這些Cookie，導致EEC失敗。

+++

### 判斷封鎖哪些Cookie

+++詳細資料
若要判斷哪些Cookie因SameSite Cookie執行原則而遭到封鎖，請在[!DNL Chrome]中使用[!DNL Developer Tools]。

1. 若要存取[!DNL Developer Tools]，在[!DNL Chrome]中檢視VEC時，請按一下Chrome > **[!UICONTROL More Tools]** > **[!UICONTROL Developer Tools]**&#x200B;右上角的&#x200B;**[!UICONTROL ellipsis]**&#x200B;圖示。
1. 按一下「**[!UICONTROL Network]**」標籤> ，然後尋找封鎖的Cookie。

   >[!NOTE]
   >
   >使用&#x200B;**[!UICONTROL Has blocked cookies]**&#x200B;核取方塊可更輕鬆找到封鎖的Cookie。

+++

## [!DNL Target]是否支援多重層級iframe？

+++詳細資料
[!DNL Target]不支援多重層級iframe。 如果您的網站載入具有子項iframe的iframe，at.js只會與父項iframe互動。 [!DNL Target]資料庫不會與子項iframe互動。

作為因應措施，您可以使用子項 iframe 的 URL 在體驗中新增頁面。

+++

## 當我嘗試編輯頁面時，我只看到了進度環而非我的頁面。(VEC 和 EEC) {#section_313001039F79446DB28C70D932AF5F58}

+++詳細資料
如果URL包含#個字元，就可能發生這種情況。 若要修正此問題，請在VEC或EEC中切換至[!UICONTROL Browse]模式，然後切換回[!UICONTROL Compose]模式。 進度環應該會消失，並且頁面應該會載入。

+++

## 內容安全性原則(CSP)標頭會封鎖我網站上的[!DNL Target]資料庫。 (VEC 和 EEC) {#section_89A30C7A213D43BFA0822E66B482B803}


+++詳細資料
如果您的網站的CSP標頭封鎖[!DNL Target]資料庫，然後載入網站但防止編輯，請確定[!DNL Target]資料庫未遭到封鎖。

>[!NOTE]
>
>除了下列資訊外，您還可以為[!DNL Google Chrome]使用[Adobe Target VEC Helper瀏覽器擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

![cps_headers影像](assets/cps_headers.png)

暫行解決方法是設定[!DNL Requestly]規則以移除CSP標頭，如下所示：

![cps_headers_2圖片](assets/cps_headers_2.png)

您可以為任何導致資源無法在VEC內載入的標頭設定類似的[!DNL Requestly]規則。

針對[!DNL Requestly]，每當需要移除標頭時，您應該執行下列其中一項作業：

* 為要在 VEC 中開啟的 URL 新增 URL 規則，如此一來，便僅有那些 URL 的標頭會移除。
* 在 VEC 中編輯時啟用規則，並在不使用 VEC 時停用規則。

+++

## 重新編輯已儲存的活動時，VEC 或 EEC 似乎損毀或未初始化。(VEC 和 EEC) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

+++詳細資料
如果定義體驗後，網站在VEC外部有所變更，則當活動開啟以進行重新編輯時，找不到先前已執行動作的選取器。 頁面似乎損毀，並且未顯示警告。

+++

## VEC 或 EEC 未顯示我的旋轉橫幅和包含 JavaScript 的其他內容。(VEC 和 EEC) {#section_8B5BE6EB050B42D6A14A054724C41330}

+++詳細資料
依預設，VEC會封鎖JavaScript元素。 如果您停用JavaScript，則可以使用這些元素。 根據網站的設定方式，一些項目可能會繼續不正確地顯示或保持無法使用。

+++

## 在頁面上變更一個元素時，變更了多個元素。(VEC 和 EEC) {#section_309188ACF34942989BE473F63C5710AF}

+++詳細資料
如果頁面上多個元素上使用相同的DOM元素ID，變更其中一個元素會變更具有該ID的所有元素。 若要防止發生此問題，一個 ID 應該僅在每個頁面上使用一次。此做法是標準的HTML最佳作法。 如需詳細資訊，請參閱[頁面修改案例](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

+++

## 我無法編輯 iFrame-busting 網站的體驗。(VEC 和 EEC) {#section_9FE266B964314F2EB75604B4D7047200}

+++詳細資料
啟用[!UICONTROL Enhanced Experience Composer] (EEC)即可解決此問題。 按一下&#x200B;**[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]**，然後選取啟用[!UICONTROL Enhanced Experience Composer]的核取方塊。 EEC使用[!DNL Adobe]管理的Proxy來載入您的頁面以進行編輯。 此Proxy允許在iFrame-busting網站上進行編輯，也允許在您尚未新增[!DNL Adobe Target]程式碼的網站和頁面上進行編輯。 在新增程式碼之後，才會將活動傳送至網站。有些網站可能無法透過EEC載入，在此情況下，您可以取消勾選此選項，以透過iFrame載入EEC。

>[!NOTE]
>
>[!DNL Adobe] Proxy伺服器無法存取您本機託管的頁面或無法從您的網路外部存取的頁面，且無法在EEC中開啟。 這些頁面可能包括測試 URL、使用者接受測試 (UAT) URL，或本機主控的頁面。

+++

## 我想在尚未完成mbox/[!DNL Target]實作的頁面上設定測試。 (VEC 和 EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

+++詳細資料
請參閱上方的「我無法編輯iFrame-bursting網站的體驗」。

+++

## 我的頁面上不會顯示具有[!UICONTROL Edit Text]/[!UICONTROL Edit HTML]或[!UICONTROL Change Text]/[!DNL Change HTML]的粗體和斜體文字樣式。 有時文字會在套用這些樣式變更之後消失。(VEC 和 EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

+++詳細資料
如果您在VEC中針對[!UICONTROL A/B Test]或[!UICONTROL Experience Targeting]活動使用&#x200B;**[!UICONTROL Edit Text]/[!UICONTROL Edit HTML]**，或針對[!UICONTROL Automated Personalization]或[!UICONTROL Multivariate Test]活動使用&#x200B;**[!UICONTROL Change Text]/[!UICONTROL Change HTML]**&#x200B;來使文字粗體或斜體，則這些樣式可能無法在頁面上套用，或文字會從VEC的頁面中消失。 之所以發生此情況，是因為RTF編輯器套用這些樣式的方式，可能會干擾網站標籤。

如果您看見此問題:

1. 按一下RTF編輯器中的&#x200B;**[!UICONTROL HTML]**&#x200B;按鈕以進入來源編輯模式。
1. 尋找樣式文字元素。

   * 針對粗體文字，將 `<strong>` 元素變更為 `<b>`。

   * 針對斜體文字，將 `<em>` 元素變更為 `<i>`。

+++

## 針對自動個人化活動，影像交換在 VEC 或 EEC 中似乎損毀。(VEC 和 EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

+++詳細資料
將影像選件新增至位置會採用VEC或EEC中原始影像空間的完整尺寸。 在傳遞時，影像不會展開並且如原樣顯示，因此對傳遞沒有影響。

+++

---
keywords: vec;可視化體驗撰寫器; vec;iframe;擴充功能;瀏覽器
description: 探索為什麼有些網站可能無法可靠地在 [!UICONTROL Visual Experience Composer] (VEC)。 VEC Helper瀏覽器擴充功能可讓您可靠地在VEC內載入網站。
title: 如何使用 [!UICONTROL Visual Experience Composer] (VEC) Helper擴充功能？
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 97b1d78de2d6ba33c1dd72494edcfc97fc3ba7e6
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 50%

---

# [!UICONTROL Visual Experience Composer] 協助程式擴充功能

此 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)的Helper瀏覽器擴充功能 [!DNL Google Chrome] 可讓您可靠地在VEC內載入網站，以快速撰寫網站體驗及評估品質。

VEC Helper瀏覽器是 [!DNL Chrome] 副檔名。 使用時，不需要使用此擴充功能 [!DNL Mozilla Firefox].

>[!IMPORTANT]
>
>舊版 [!DNL Target] 本文記錄的VEC Helper擴充功能是使用Manifest V2建立的。 [!DNL Google] 宣佈從2024年6月起，不再允許使用資訊清單V2建立的擴充功能。 如需詳細資訊，請參閱 [資訊清單V2支援時間表公告](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} 從 [!DNL Google] 於 *適用於開發人員的Chrome* 網站。
>
>自2024年6月起， [!DNL Google] 將開始停用使用資訊清單V2建立的擴充功能，包括本主題中紀錄的擴充功能。 [!DNL Adobe] 建議客戶改用較新的版本 [Visual Editing Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) 儘可能早。

## 某些網站可能無法可靠地在 VEC 中開啟的原因

* 網站的安全性原則過於嚴格。
* 網站架設在 iFrame 中。
* 網站尚未實作 at.js 資料庫。
* 客戶的 QA 或暫存網站無法供外部世界使用 (網站僅供內部使用)。
* 當嘗試使用VEC開啟使用中的網站時，目前有一些限制 [服務人員](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API){target=_blank} (SW)。

SW 是一種網路技術，可用於攔截網頁安裝所在網域的請求。SW 在該次頁面瀏覽中存活下來，並在隨後的頁面瀏覽中自我啟用。SW 決定允許哪些請求通過，以及攔截哪些請求，並改從快取提供服務。

SW 可以控制快取；可以快取網頁本身、靜態資源，如 JS、CSS、IMG、AJAX 請求、其內容及其回應標頭，包括我們的 [Target VEC Helper 擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)嘗試移除的回應標頭，如 X-Frame-Options: SAMEORIGIN、CSP (Content-Security-Policy) 或 Set-Cookie。

遺憾的是，攔截網路請求的Chrome擴充功能API不接收SW所攔截和處理的請求。 因此，如果網頁請求是由SW從快取中提供服務，則擴充功能無法修正標頭和Cookie，因為同時快取了X-Frame-Options或CSP標頭的緣故，網頁將不會載入VEC內。

您可以從Chrome的「開發人員工具」>「應用程式」標籤停用Service Worker，然後啟用「Service Worker」區段下的「略過網路」核取方塊，當作可能的因應措施。

* 您正在使用Google Chrome 80+搭配增強的SameSite Cookie執行政策。 如需詳細資訊，請參閱 [最近宣佈的Google Chrome SameSite Cookie執行政策對VEC和EEC有何影響](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)？

適用於Chrome的VEC Helper瀏覽器擴充功能解決了客戶現依賴 [!DNL Target] [增強體驗撰寫器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) 或協力廠商擴充功能，例如Requestly。

## 使用VEC Helper擴充功能的好處

* 所有的 iFrame 爆破標頭 (例如 X-Frame-Options 和 Content-Security-Policy) 會以隱含的方式從網站上移除。不再需要建立複雜的Requestly規則。
* 如果網站上未包含 [!DNL Target] at.js JavaScript 資料庫，您可以使用擴充功能來插入資料庫，這樣就能為網站撰寫體驗。接著可以使用預覽連結來建立活動和保證品質。

  請注意，使用增強型體驗撰寫器(EEC)時，此擴充功能不會插入at.js，但是SameSite Cookie功能依然存在。 若要在網頁上插入 at.js，請關閉 EEC。

* [行動檢視區](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) 即使不使用 [!UICONTROL Enhanced Experience Composer] (EEC)。
* 即使客戶的 IT 開發人員尚未在網站上實作 [!DNL Target]，剛接觸 [!DNL Target] 的客戶還是可以利用擴充功能來試驗 [!DNL Target]。
* 管理多位客戶網站與 [!DNL Target] 帳戶的合作夥伴現在擁有一套簡單的機制可支援 VEC 載入工作，而不必在第三方工作中管理多個規則。

## 取得並安裝 VEC Helper 瀏覽器擴充功能

1. 導覽至 [Chrome線上應用程式商店中的Adobe Target VEC Helper瀏覽器擴充功能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. 按一下 **[!UICONTROL Add to Chrome > Add Extension]**。
1. 在 [!DNL Target] 中開啟 VEC。
1. 若要使用擴充功能，請在 VEC 或 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)中時，按一下 Chrome 瀏覽器工具列上的 VEC Helper 瀏覽器擴充功能圖示 (![VEC Helper 圖示](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png))。
1. （視條件而定）滑動 **[!UICONTROL Inject Target Libraries]** 如果網頁尚未包含 [!DNL Target] at.js JavaScript資料庫。

   下圖顯示的VEC Helper具有 [!UICONTROL Inject Target Libraries] 啟用設定：

   ![VEC helper 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   下圖顯示詢問您是否要在頁面中插入 [!DNL Target] 資料庫以啟用編寫功能的 VEC Helper:

   ![VEC helper 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （視條件而定）滑動 **[!UICONTROL Cookies]** 切換至「開啟」位置以自動新增 `SameSite=None` 屬性瀏覽器修正。

   ![VEC Helper擴充功能中的Cookie切換](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   如需有關 `SameSite=None` 屬性瀏覽器修正的詳細資訊，請參閱[排解可視化體驗撰寫器和增強型體驗撰寫器的相關問題](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)中的「最近宣布的 Google Chrome SameSite cookie 執行政策對 VEC 和 EEC 有何影響？」。

## 附註

* 此 [!UICONTROL Inject Target libraries] 擴充功能中的標幟預設為OFF。 如果您要在尚未針對 [!DNL Target] 實作的網站上使用 VEC，可以啟用此標記。

  此旗標為全域設定。 VEC 中開啟的所有網站都會啟用或停用此標記。舉例來說，如果您將此標幟設為「開啟」，並開啟已使用at.js實作的網站，您會收到一則訊息，通知您at.js已載入。 Adobe預計大部分客戶都會在網頁上實作at.js，且預設值為「關閉」。

* 此擴充功能會載入最新版本的at.js （由提供） [!DNL Target UI] 在 [!UICONTROL Administration > Implementation].
* 在 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)下使用此擴充功能來插入 at.js 時，您必須另外開啟一個 Chrome 分頁。此 Chrome 分頁必須授權給您建立活動的相同 [!DNL Adobe Experience Cloud] 組織。
* 以下訊息有助於您瞭解:

   * 如果您嘗試使用 VEC 載入網站卻無法載入，系統會顯示訊息，建議您安裝 VEC Helper 瀏覽器擴充功能。
   * 如果網站尚未實作 at.js，VEC 會顯示訊息，建議您安裝擴充功能。
   * 如果擴充功能已啟用且在執行載入工作，當擴充功能插入 at.js 資料庫 (如有必要) 或協助以可靠的方式在 VEC 中開啟網站時，系統會顯示訊息。

---
keywords: VEC; 可視化體驗撰寫器; iFrame; 擴充功能; 瀏覽器
description: 探索為何某些網站可能無法在可視化體驗撰寫器(VEC)中可靠開啟。 VEC Helper瀏覽器擴充功能可讓您在VEC內以可靠的方式載入網站。
title: 如何使用可視化體驗撰寫器(VEC)Helper擴充功能？
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 8612928e647c6c11a40b499001261be3a8521648
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 55%

---

# 可視化體驗撰寫器 Helper 擴充功能

此 [!DNL Adobe Target] [!UICONTROL 可視化體驗撰寫器] (VEC)Google Chrome的Helper瀏覽器擴充功能可讓您在VEC內以可靠的方式載入網站，以快速撰寫網頁體驗及保證體驗品質。

VEC Helper瀏覽器是Chrome擴充功能。 使用Mozilla Firefox時不需要此擴充功能。

>[!IMPORTANT]
>
>自2023年1月起， [!DNL Target] VEC Helper擴充功能將在Google Chrome中停止運作，因為Google不允許使用資訊清單V2的擴充功能。 下載新的擴充功能，以繼續在中以視覺化方式撰寫您的網站 [!DNL Target] 從新年開始。 如需詳細資訊，請參閱 [Visual Editing Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

## 某些網站無法可靠地在 VEC 中開啟的可能原因

* 網站的安全性原則過於嚴格。
* 網站架設在 iFrame 中。
* 網站尚未實作 at.js 資料庫。
* 外部無法存取客戶的 QA 和/或預備網站 (網站為內部網站)。
* 當嘗試用 VEC 開啟使用 [Service Worker](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API){target=_blank} (SW) 的網站時，目前有一些限制。

SW 是一種網路技術，可用於攔截網頁安裝所在網域的請求。SW 在該次頁面瀏覽中存活下來，並在隨後的頁面瀏覽中自我啟用。SW 決定允許哪些請求通過，以及攔截哪些請求，並改從快取提供服務。

SW 可以控制快取；可以快取網頁本身、靜態資源，如 JS、CSS、IMG、AJAX 請求、其內容及其回應標頭，包括我們的 [Target VEC Helper 擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)嘗試移除的回應標頭，如 X-Frame-Options: SAMEORIGIN、CSP (Content-Security-Policy) 或 Set-Cookie。

很可惜，截取Web請求的Chrome擴充功能API不會收到軟體截取和處理的請求。 因此，如果軟體從快取提供網頁要求，由於X-Frame-Options或CSP標頭也經過快取，因此VEC內不會載入網頁，因此擴充功能無法修正標頭和Cookie。

可能的因應措施是，從 Chrome「開發人員工具」>「Application」索引標籤中停用 Service Worker，然後啟用「Service Workers」區段下的「Bypass for network」核取方塊。

* 您使用Google Chrome 80+搭配增強的SameSite Cookie實施原則。 如需詳細資訊，請參閱 [最近宣佈的Google Chrome SameSite Cookie實作原則對VEC和EEC有何影響](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

Chrome的VEC Helper瀏覽器擴充功能解決了客戶現在依賴的網站載入問題 [!DNL Target] [增強體驗撰寫器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) 或協力廠商擴充功能，例如Requestly。

## 使用 VEC Helper 擴充功能的好處

* 所有的 iFrame 爆破標頭 (例如 X-Frame-Options 和 Content-Security-Policy) 會以隱含的方式從網站上移除。不再需要建立複雜的Requestly規則。
* 如果網站上未包含 [!DNL Target] at.js JavaScript 資料庫，您可以使用擴充功能來插入資料庫，這樣就能為網站撰寫體驗。接著可以使用預覽連結來建立活動和保證品質。

   請注意，使用增強體驗撰寫器(EEC)時，擴充功能不會插入at.js，但仍有SameSite Cookie功能存在。 若要在網頁上插入at.js，請關閉EEC。

* [行動檢視區](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) 即使沒有 [!UICONTROL 增強體驗撰寫器] (EEC)。
* 即使客戶的 IT 開發人員尚未在網站上實作 [!DNL Target]，剛接觸 [!DNL Target] 的客戶還是可以利用擴充功能來試驗 [!DNL Target]。
* 管理多位客戶網站與 [!DNL Target] 帳戶的合作夥伴現在擁有一套簡單的機制可支援 VEC 載入工作，而不必在第三方工作中管理多個規則。

## 取得並安裝 VEC Helper 瀏覽器擴充功能

1. 導覽至 [Adobe Target Chrome線上應用程式商店中的VEC Helper瀏覽器擴充功能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. 按一下&#x200B;**[!UICONTROL 「新增至 Chrome > 新增擴充功能」]**。
1. 在中開啟VEC [!DNL Target].
1. 若要使用擴充功能，請在 VEC 或 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)中時，按一下 Chrome 瀏覽器工具列上的 VEC Helper 瀏覽器擴充功能圖示 (![VEC Helper 圖示](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png))。
1. （條件性）滑動 **[!UICONTROL 插入Target資料庫]** 如果網頁尚未包含 [!DNL Target] at.js JavaScript資料庫。

   下圖顯示已啟用[!UICONTROL 插入 Target 資料庫]設定的 VEC Helper:

   ![VEC helper 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   下圖顯示詢問您是否要在頁面中插入 [!DNL Target] 資料庫以啟用編寫功能的 VEC Helper:

   ![VEC helper 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （條件性）滑動 **[!UICONTROL Cookie]** 切換至「開啟」位置以自動新增 `SameSite=None` 屬性瀏覽器修正。

   ![Cookie在VEC Helper擴充功能中切換](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   如需 `SameSite=None` 屬性瀏覽器修正，請參閱「最近宣佈的Google Chrome SameSite Cookie實作原則如何影響VEC和EEC？」 [排解視覺體驗撰寫器和增強體驗撰寫器的相關問題](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)中的「最近宣佈的 Google Chrome SameSite Cookie 實施政策如何影響 VEC 和 EEC？」。

## 附註

* 擴充功能中的[!UICONTROL 「插入 Target 資料庫」]標記預設為「關閉」。如果您要在尚未針對 [!DNL Target] 實作的網站上使用 VEC，可以啟用此標記。

   此標幟為全域設定。 VEC 中開啟的所有網站都會啟用或停用此標記。因此，例如，若您將此標幟設為「on」，並開啟已使用at.js實作的網站，您會收到訊息，通知您at.js已載入。 Adobe預期大部分的客戶已在其頁面上實作at.js，並使用「off」的預設設定。

* 擴充功能會載入最新版的at.js(可從 [!DNL Target UI] in [!UICONTROL 管理>實作].
* 在 [QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)下使用此擴充功能來插入 at.js 時，您必須另外開啟一個 Chrome 分頁。此 Chrome 分頁必須授權給您建立活動的相同 [!DNL Adobe Experience Cloud] 組織。
* 以下訊息有助於您瞭解:

   * 如果您嘗試使用 VEC 載入網站卻無法載入，系統會顯示訊息，建議您安裝 VEC Helper 瀏覽器擴充功能。
   * 如果網站尚未實作 at.js，VEC 會顯示訊息，建議您安裝擴充功能。
   * 如果擴充功能已啟用且在執行載入工作，當擴充功能插入 at.js 資料庫 (如有必要) 或協助以可靠的方式在 VEC 中開啟網站時，系統會顯示訊息。

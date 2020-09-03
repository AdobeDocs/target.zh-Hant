---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: 提供使用 Adobe Target 可視化體驗撰寫器 (VEC) Helper 瀏覽器擴充功能，在 VEC 內以可靠的方式載入網站來迅速撰寫體驗和保證體驗品質的資訊。
title: Adobe Target 可視化體驗撰寫器 (VEC) Helper 擴充功能
feature: vec
topic: Standard
translation-type: tm+mt
source-git-commit: ee618961faa12a7352aaf9ed1d869f9e5ab39cdd
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 59%

---


# 可視化體驗撰寫器 Helper 擴充功能

The [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) Helper browser extension for Google Chrome lets you load websites reliably within the VEC to rapidly author and QA web experiences.

某些網站無法可靠地在 VEC 中開啟的可能原因:

* 網站的安全性原則過於嚴格。
* 網站架設在 iFrame 中。
* 網站尚未實作 at.js 資料庫。
* 外部無法存取客戶的 QA 和/或預備網站 (網站為內部網站)。
* 您使用的Google Chrome 80+搭配增強的SameSite Cookie實施政策。 如需詳細資訊，請 [參閱最近宣佈的Google Chrome SameSite Cookie實施政策如何影響VEC和EEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

The VEC Helper browser extension for Chrome solves site-loading issues for which customers now rely on the [!DNL Target] [Enhanced Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md#eec) or third-party extensions, such as Requestly.

使用 VEC Helper 擴充功能的好處:

* 所有的 iFrame 爆破標頭 (例如 X-Frame-Options 和 Content-Security-Policy) 會以隱含的方式從網站上移除。不再需要建立複雜的 Requestly 規則即可完成相同工作。
* 如果網站上未包含 [!DNL Target] at.js JavaScript 資料庫，您可以使用擴充功能來插入資料庫，這樣就能為網站撰寫體驗。接著可以使用預覽連結來建立活動和保證品質。
* [即使沒有](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) Enhanced Experience Composer [!UICONTROL (EEC)，也支援行動] 檢視區。
* 即使客戶的 IT 開發人員尚未在網站上實作 [!DNL Target]，剛接觸 [!DNL Target] 的客戶還是可以利用擴充功能來試驗 [!DNL Target]。
* 管理多位客戶網站與 [!DNL Target] 帳戶的合作夥伴現在擁有一套簡單的機制可支援 VEC 載入工作，而不必在第三方工作中管理多個規則。

## 取得並安裝 VEC Helper 瀏覽器擴充功能

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. 按一下&#x200B;**[!UICONTROL 「新增至 Chrome > 新增擴充功能」]**。
1. 在中開啟VEC [!DNL Target]。
1. 若要使用擴充功能，請在 VEC 或 [QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)中時，按一下 Chrome 瀏覽器工具列上的 VEC Helper 瀏覽器擴充功能圖示 (![VEC Helper 圖示](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png))。
1. （條件性）如果網頁 **[!UICONTROL 尚未包含at.js JavaScript程式庫，請投影片「注入目標程式庫]** 」切換至「開啟」 [!DNL Target] 位置。

   下圖顯示已啟用[!UICONTROL 插入 Target 資料庫]設定的 VEC Helper:

   ![VEC helper 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   下圖顯示詢問您是否要在頁面中插入 [!DNL Target] 資料庫以啟用編寫功能的 VEC Helper:

   ![VEC helper 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （條件性）投影片 **[!UICONTROL Cookie]** 切換至「開啟」位置，以自動新增SameSite=None屬性瀏覽器修正，然後指定Cookie名稱和網域。

   ![Cookie在VEC協助工具擴充功能中切換](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   下列連結提供其他資訊：

   * 如需SameSite=None屬性瀏覽器修正的詳細資訊，請參閱「最近宣佈的Google Chrome SameSite Cookie實施政策如何影響VEC和EEC?」 in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

   * Cookie名稱是「mbox」，而Cookie網域是您從中提供mbox之網域的第二層和最上層。 因為是使用公司所提供的網域，所以這些會是第一方 Cookie。範例: `mycompany.com`. 如需詳細資訊，請 [參閱Experience Cloud介面使](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-target.html) 用指南中的Adobe Target Cookie **。

## 附註

* 實作必須使用 [!DNL Target] at.js 資料庫。您無法將 mbox.js 實作用於擴充功能。
* 擴充功能中的[!UICONTROL 「插入 Target 資料庫」]標記預設為「關閉」。如果您要在尚未針對 [!DNL Target] 實作的網站上使用 VEC，可以啟用此標記。

   請注意，此標記為全域設定。VEC 中開啟的所有網站都會啟用或停用此標記。例如，如果您將此標幟設為「on」，並開啟已使用at.js實作的網站，您會收到一則訊息，通知您at.js已載入。 我們預計大部分客戶的頁面上都會實施at.js，並會使用預設的「off」設定。

* The extension loads the latest version of at.js that is available from the [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* 在 [QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)下使用此擴充功能來插入 at.js 時，您必須另外開啟一個 Chrome 分頁。此 Chrome 分頁必須授權給您建立活動的相同 [!DNL Adobe Experience Cloud] 組織。
* 以下訊息有助於您瞭解:

   * 如果您嘗試使用 VEC 載入網站卻無法載入，系統會顯示訊息，建議您安裝 VEC Helper 瀏覽器擴充功能。
   * 如果網站尚未實作 at.js，VEC 會顯示訊息，建議您安裝擴充功能。
   * 如果擴充功能已啟用且在執行載入工作，當擴充功能插入 at.js 資料庫 (如有必要) 或協助以可靠的方式在 VEC 中開啟網站時，系統會顯示訊息。


---
keywords: vec;可視化體驗撰寫器; vec;iframe;擴充功能;瀏覽器
description: 探索為什麼有些網站可能無法可靠地在[!UICONTROL 視覺化體驗撰寫器] (VEC)中開啟。 VEC Helper瀏覽器擴充功能可讓您可靠地在VEC內載入網站。
title: 如何使用[!UICONTROL 視覺化體驗撰寫器] (VEC) Helper擴充功能？
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
TQID: 'https://experienceleague.adobe.com/lqZGGWG1NVtKDzNGPq5k2bDPzxDfNWqPtJ-bYfLCr3Q'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
    internal-label: Web experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 5%
---
# [!UICONTROL 視覺化體驗撰寫器] Helper擴充功能 {#vec-helper-extension}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解舊版VEC Helper瀏覽器擴充功能如何在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)中載入網站，以及如何安裝及使用它。

>[!ENDSHADEBOX]

適用於[!DNL Google Chrome]的[!DNL Adobe Target] **[!UICONTROL 視覺化體驗撰寫器]** (VEC) Helper瀏覽器擴充功能會在VEC中以可靠的方式載入網站，讓製作和檢查網頁體驗的速度更快。 [!DNL Mozilla Firefox]中不需要副檔名。

>[!IMPORTANT]
>
>* 本文記錄的舊版[!DNL Target] VEC Helper擴充功能是使用Manifest V2建立的。 [!DNL Google]宣佈從2024年6月起，將停止允許以Manifest V2建立的擴充功能。 如需詳細資訊，請參閱&#x200B;*開發人員專用Chrome*&#x200B;網站上[!DNL Google]的[資訊清單V2支援時間表宣告](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank}。
>
>* 從2024年6月開始，[!DNL Google]會停用以Manifest V2建立的擴充功能，包括本文所述的擴充功能。 [!DNL Adobe]建議儘快移至較新的[Visual Editing Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

## 為什麼有些網站無法在VEC中以可靠的方式開啟

網站可能無法可靠地在VEC中開啟，原因如下：

* 網站的安全性原則過於嚴格。
* 網站架設在 iFrame 中。
* 網站尚未實作 at.js 資料庫。
* 客戶的QA或測試網站為內部網站，網路外部不可用。
* 網站使用[Service Worker](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API){target=_blank} (SW)，VEC目前僅支援此功能，但有限制。 請參閱下節。
* 網站會在[!DNL Chrome] 80或更新版本中開啟，這會強制執行SameSite Cookie原則。 如需詳細資訊，請參閱[Google Chrome SameSite Cookie原則](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)。

[!DNL Chrome]的VEC Helper瀏覽器擴充功能解決了客戶依賴於[!DNL Target] [增強體驗撰寫器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)或第三方擴充功能（例如Requestly）的網站載入問題。

### 服務人員

Service Worker (SW)是網頁安裝的網頁技術，可攔截其網域的請求。 SW 在該次頁面瀏覽中存活下來，並在隨後的頁面瀏覽中自我啟用。 它會決定哪些請求會通過，以及攔截哪些請求並從快取提供服務。

SW可以快取網頁本身、靜態資源（例如JS、CSS、IMG和AJAX請求）、其內容及其回應標頭。 這些標頭包含[Target VEC Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)嘗試移除的標頭，例如`X-Frame-Options: SAMEORIGIN`、CSP (`Content-Security-Policy`)和`Set-Cookie`。

攔截網路要求的[!DNL Chrome]擴充功能API不會接收SW已攔截及處理的要求。 因此，當SW從快取中提供網頁請求時，擴充功能無法修正標頭和Cookie，而且頁面不會因為快取的`X-Frame-Options`或CSP標頭而載入VEC內。

請停用[!DNL Chrome]開發人員工具> **應用程式**&#x200B;索引標籤中的Service Worker，然後啟用Service Worker區段中的[略過網路]核取方塊。

## VEC Helper擴充功能的優點

* **已移除Iframe-busting標頭：**&#x200B;擴充功能會隱含地從網站移除`X-Frame-Options`和`Content-Security-Policy`等標頭，因此不需要複雜的Requestly規則。
* **at.js插入：**&#x200B;當網頁尚未包含[!DNL Target] at.js JavaScript資料庫時，擴充功能可以插入該資料庫。 接著，您就可以為網站製作體驗，並透過預覽連結來建立及檢查活動。 使用增強型體驗撰寫器(EEC)時，此擴充功能不會插入at.js，但SameSite Cookie功能會保留。 若要在網頁上插入at.js，請關閉EEC。
* **行動檢視區：** [行動檢視區](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)即使沒有&#x200B;**[!UICONTROL 增強體驗撰寫器]** (EEC)也受到支援。
* **新[!DNL Target]客戶：**&#x200B;此擴充功能可讓您嘗試使用[!DNL Target]，即使IT開發人員尚未在網站上實作[!DNL Target]亦然。
* **合作夥伴：**&#x200B;為多位客戶的網站和[!DNL Target]帳戶提供服務的合作夥伴，可獲得一個支援VEC載入的機制，取代協力廠商工具中的多個規則。

## 取得並安裝 VEC Helper 瀏覽器擴充功能

在[!DNL Chrome]中安裝擴充功能可讓您可靠地在VEC中載入網站，包括封鎖iframe或尚未實作at.js的網站。

1. 移至Chrome網站商店中的[Adobe Target VEC Helper瀏覽器擴充功能](https://chromewebstore.google.com/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca)。
1. 按一下&#x200B;**[!UICONTROL 新增至Chrome]** > **[!UICONTROL 新增擴充功能]**。
1. 在 [!DNL Target] 中開啟 VEC。
1. 在VEC或[QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md)中，按一下[!DNL Chrome]工具列中的VEC Helper瀏覽器擴充功能圖示（ ![VEC Helper圖示](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)）。
1. （視條件而定）如果網頁尚未包含[!DNL Target] at.js JavaScript資料庫，請切換&#x200B;**[!UICONTROL 插入Target資料庫]**&#x200B;切換開關。

   下圖顯示已啟用&#x200B;**[!UICONTROL 插入Target資料庫]**&#x200B;設定的VEC Helper：

   ![VEC Helper擴充功能面板的「插入Target資料庫」切換功能為&#39;b6&#39;7d啟，「Cookie」切換功能為&#39;b6&#39;7d啟，表示「Cookie」設定會針對VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)內的請求在所有Cookie上設定SameSite=None和Secure標幟

   接著VEC Helper會詢問是否應將[!DNL Target]資料庫插入頁面以啟用編寫功能：

   ![插入Target資料庫提示，指出Target VEC Helper擴充功能想要在頁面中插入Target資料庫，以使用「取消」和「允許」按鈕啟用編寫功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （條件式）開啟&#x200B;**[!UICONTROL Cookie]**&#x200B;切換功能，以自動新增`SameSite=None`屬性瀏覽器修正。

   在顯示範例頁面的Visual Experience Composer上，![VEC Helper擴充功能面板（具有Cookie切換功能）開啟並反白顯示](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   如需`SameSite=None`屬性瀏覽器修正的詳細資訊，請參閱[Google Chrome SameSite Cookie原則](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)。

## 使用說明

* 擴充功能中的&#x200B;**[!UICONTROL 插入Target資料庫]**&#x200B;旗標預設為關閉。 開啟此功能以在尚未實作[!DNL Target]的網站上使用VEC。

  此旗標是全域設定，因此可針對VEC中開啟的所有網站啟用或停用。 例如，在開啟標幟時，開啟已實作at.js的網站會顯示已載入at.js的訊息。 [!DNL Adobe]預期大部分客戶已在其頁面上實作at.js，並使用預設設定（即「關閉」）。

* 此擴充功能會載入最新版本的at.js （可在&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 實作]**&#x200B;底下的[!DNL Target] UI中使用）。
* 若要使用擴充功能在[QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md)中插入at.js，必須開啟另一個Chrome索引標籤。 此索引標籤必須驗證給建立活動的相同[!DNL Adobe Experience Cloud]組織。
* VEC會在下列情況下顯示訊息：

  * 網站無法載入VEC。 此訊息會建議安裝VEC Helper瀏覽器擴充功能。
  * 網站上尚未實作at.js。 此訊息會建議安裝擴充功能。
  * 擴充功能已啟用並支援載入工作。 如有需要，擴充功能會插入at.js程式庫，或協助您可靠地在VEC中開啟網站，系統就會顯示訊息。

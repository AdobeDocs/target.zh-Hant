---
description: at.js 是新的 Adobe Target 實作資料庫，專為典型 Web 實作和單頁應用程式而設計。
keywords: Target Standard;at.js;實作
seo-description: at.js 是新的 Adobe Target 實作資料庫，專為典型 Web 實作和單頁應用程式而設計。
seo-title: 從 mbox.js 移轉至 at.js
solution: Target
title: 從 mbox.js 移轉至 at.js
topic: Standard
uuid: 10da01d7-d308-44e3-9c6e-ff4f713bd312
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 從 mbox.js 移轉至 at.js{#migrate-from-mbox-js-to-at-js}

at.js 是新的 [!DNL Adobe Target] 實作資料庫，專為典型 Web 實作和單頁應用程式而設計。

除了眾多優點以外，[!DNL at.js] 還能改進 Web 實施的頁面載入時間，並且為單頁應用程式提供更好的實施選項。

針對 [!DNL Target] 實作以 [!DNL at.js] 取代 [!DNL mbox.js]。[!DNL at.js] 程式庫也包含 [!DNL target.js] 中已有的元件，因此不需要再呼叫 [!DNL target.js]。

>[!NOTE]
>
>Adobe Experience Manager (AEM) 6.2 含 FP-11577 (或更新版) 在其 Adobe Target 雲端服務整合上支援 at.js 實作。如需詳細資訊，請參閱 *Adobe Experience Manager 6.2 說明文件*中的[功能套件](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html)以及[與 Adobe Target 整合](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html)。

若要使用 [!DNL at.js]，請在您要實作它的頁面上取代 [!DNL mbox.js] 參照。您無法在單一頁面上同時使用 [!DNL mbox.js] 和 [!DNL at.js]。不過，您可以在網站的每一個頁面上使用兩者之間任何一個。

[!DNL at.js] 資料庫適用於使用 `mboxDefine()`、`mboxCreate()` 和 `mboxUpdate()` 的現有實作，也支援以單頁應用程式型實作為重點的新功能。

您目前使用 [!DNL at.js] 的任何地方都可以使用 [!DNL mbox.js]。

[!DNL at.js] 程式庫有幾項優於 [!DNL mbox.js] 程式庫的改善，包括:

* 透過跨網域 AJAX 的完全非同步通訊

   >[!IMPORTANT]
   >
   >雖然 [!DNL at.js] 以非同步方式與 [!DNL Target] 伺服器通訊，但 [!DNL at.js] 檔案本身必須在頁面的 `<head>` 區段中同步載入。且最好是其中一個最先載入的指令碼。[!DNL at.js] 載入時會透過 `XMLHttpRequest`，非同步地執行 mbox 呼叫，而不會阻擋頁面呈現。

* 不會再封鎖呼叫
* 未使用 `document.write()`
* 在 [!DNL Target] 回應中不會立即執行 JavaScript
* 更妥善的逾時和錯誤處理

   * 可自訂[按呼叫來計算逾時](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)
   * 不因逾時而重新載入

* 特別針對單頁應用程式/MVC 架構來設計的函式

## 訓練影片: at.js - 優點與最佳實務實作

這支影片記錄了「[營業時間](../../../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」，這是一項 Adobe 客戶服務團隊主導的計劃。

* at.js 資料庫的運作原理
* At.js 勝過 mbox.js 之處
* At.js 處理忽隱忽現情況的方式
* At.js 對於錯誤的處理作法
* 偵錯方法
* 已知問題與未來發展

>[!VIDEO](https://video.tv.adobe.com/v/22223/)

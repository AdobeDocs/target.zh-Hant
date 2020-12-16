---
keywords: Target Standard;at.js;implementation
description: at.js 是新的 Adobe Target 實作資料庫，專為典型 Web 實作和單頁應用程式而設計。
title: 從 mbox.js 移轉至 at.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 96%

---


# 從 mbox.js 移轉至 at.js{#migrate-from-mbox-js-to-at-js}

at.js 是新的 [!DNL Adobe Target] 實作資料庫，專為典型 Web 實作和單頁應用程式而設計。

除了眾多優點以外，[!DNL at.js] 還能改進 Web 實施的頁面載入時間，並且為單頁應用程式提供更好的實施選項。

針對 [!DNL Target] 實作以 [!DNL at.js] 取代 [!DNL mbox.js]。[!DNL at.js] 程式庫也包含 [!DNL target.js] 中已有的元件，因此不需要再呼叫 [!DNL target.js]。

>[!NOTE]
>
>Adobe Experience Manager (AEM) 6.2 含 FP-11577 (或更新版) 在其 Adobe Target 雲端服務整合上支援 at.js 實作。如需詳細資訊，請參閱 *Adobe Experience Manager 6.2 說明文件*&#x200B;中的[功能套件](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html)以及[與 Adobe Target 整合](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html)。

## at.js 的優點 {#benefits}

下表說明兩個程式庫之間的差異:

| 程式庫參考 | 說明 |
|--- |--- |
| at.js | at.js 取代了 實施的 mbox.js。[!DNL Target]<br>除了眾多優點以外，at.js 還能改進 Web 實施的頁面載入時間、改進安全性、避免 Google Chrome 中的 document.write 警告，以及為單頁應用程式提供更好的實施選項。<br>如需詳細資訊，請參閱 [at.js 實作](#implement)。 |
| mbox.js | 在 [!DNL Target] 16.3.1 (2016 年 3 月) 之前的版本中，[!DNL Target] 需要呼叫 mbox.js 來建立全域 mbox，[!DNL Target] 需要此全域 mbox 才能傳送活動、追蹤點擊，以及追蹤大部分成功量度。此檔案包含所有活動所需的資料庫。您不需要維護不同的活動特定版本檔案。<br>如果您的頁面上已有來自舊型 [!DNL Target] 實作的包裝 mbox，則這些 mbox 仍可用在新介面中。仍需要更新的 mbox.js 檔案，但可以使用可視化體驗撰寫器為活動選取這些 mbox 並加以編輯。<br>[!DNL Target] Standard 和 Premium 會以 target.js 檔案的參照來更新和補充 mbox.js。target.js 檔案是由 Adobe 管理。此 Target.js 檔案可讓您使用可視化體驗撰寫器來編輯任何頁面的內容，即使該頁面不含預先定義的 mbox 也一樣。您必須在網站的每一個頁面上參照此檔案。<br>如需詳細資訊，請參閱 [mbox.js 實作](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)。<br>**重要**: 仍支援 mbox.js 資源庫，但將不會提供功能更新。所有客戶應該移轉至 at.js。如需詳細資訊，請參閱[從 mbox.js 移轉至 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)。 |

## 實作 at.js {#implement}

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

## 訓練影片: at.js - 優點與最佳實務實作  ![概述徽章](/help/assets/overview.png)

這支影片記錄了「[營業時間](/help/cmp-resources-and-contact-information.md)」，這是一項 Adobe 客戶服務團隊主導的計劃。

* at.js 資料庫的運作原理
* At.js 勝過 mbox.js 之處
* At.js 處理忽隱忽現情況的方式
* At.js 對於錯誤的處理作法
* 偵錯方法
* 已知問題與未來發展

>[!VIDEO](https://video.tv.adobe.com/v/22223/)

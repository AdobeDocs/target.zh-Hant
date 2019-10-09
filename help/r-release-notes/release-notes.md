---
description: 這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
keywords: 發行說明；新功能；發行；更新；更新；發行；增強；增強；修正；錯誤修正
seo-description: 這些版本說明提供關於每個 Adobe Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
seo-title: 'Adobe Target 版本說明 (最新) '
solution: Target
title: Target 版本說明 (最新)
topic: 建議
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 71d94ef5d2351dc8410c0d418096088a0a900f03

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

## 目標平台（2019年10月9日）

| 功能/增強功能 | 說明 |
| --- | --- |
| Node.js SDK 1.0版 | Target Node.js SDK可讓您部署Target伺服器端。<br>此Node.js SDK可協助您輕鬆將Target與其他Experience cloud解決方案整合，例如Adobe Experience Cloud Identity Service、Adobe Analytics和Adobe Audience Manager。<br>Node.js SDK透過我們的傳送API與Adobe Target整合時引入最佳實務並免除複雜性，讓您的工程團隊可專注在商業邏輯上。 以下是我們在最新版本中推出的主要功能：<ul><li>支援預取和通知，讓您透過快取最佳化效能。</li><li>支援在網頁和伺服器端混合整合Target時最佳化效能。 我們將引入一個名為 `serverState` 的設定，由透過伺服器端擷取的體驗填入，如此at.js 2.2就不會再進行額外的伺服器呼叫來擷取體驗。 此方法可最佳化頁面載入效能。</li><li> 支援透過Node.js SDK擷取VEC建立的活動，此為新的傳送API所提供。</li><li>開放來源，讓您的開發人員可以為Node.js SDK貢獻心力。</li></ul><br>如需詳細資訊，請 [參閱版本注意事項- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)。 |
| 傳送API | 生產環境中提供全新的傳送API端點（/v1/傳送）。 主要功能包括：<ul><li>一個端點，可擷取一或多個mbox的體驗。</li><li>透過API擷取VEC建立的活動。</li><li>支援稱為「檢視」的全新物件，用於單頁應用程式(SPA)和行動應用程式。</li></ul><br>如需詳細資訊，請 [參閱版本注意事項- Target伺服器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)。 |

## Target Standard/Premium 19.9.2 (2019 年 9 月 30 日)

本次維護發行包含下列增強功能:

* 多個安全性修正，包括可視化體驗撰寫器 (VEC) 中 RTF 編輯器 (RTE) 的安全新更新。(TGT-35383)
* A/B測試與體驗定位活動中，除了DIV外，現在還可將建議選件新增至DIV以外的元素（例如P、UL、H1）。 (TGT-34333)
* 事件通知（Target UI中的鈴鐺圖示）已不再可用。 新的通知功能即將推出。

## Target Standard/Premium 19.9.1 (2019 年 9 月 10 日)

| 功能/增強功能 | 說明 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) Enterprise Permissions | 在Target 2019年9月發行中，「企業權限」為客戶提供下列存取控制：<UL><li>您可以選擇要將整合套用到哪個工作區.</li><li>您可以將角色套用至 Adobe I/O 整合功能: 核准者、編輯者或觀察者。</li></ul>如需逐步指示和詳細資訊，請參閱[授予 Adobe I/O 整合功能對工作區的存取權並指派角色](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)。 |

## 其他發行說明和版本詳細資訊

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明——目標伺服器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 與Adobe Target伺服器端API相關的發行說明。 |
| [發行說明- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 與Adobe Target的Node.js SDK相關的發行說明。 |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobe Target at.js javaScript程式庫各版本變更的詳細資訊。 |
| [mbox.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 本頁面顯示每個 mbox.js 版本的變更。<br>請注意，mbox.js程式庫已不再開發。 所有客戶應該從 mbox.js 移轉至 at.js。 |

## 文件變更、過去的版本說明和 Experience Cloud 版本說明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視在版本說明中可能未涵蓋的手冊更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版版本說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本說明](../r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 版本說明 | 檢視 Adobe Experience Cloud 解決方案的最新版本說明。<br>如需詳細資訊，請參 [閱Experience cloud發行說明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先順序產品更新清單 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |

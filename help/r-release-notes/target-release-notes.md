---
description: 提供最新或即將發行的Adobe target版本功能、增強功能和修正資訊的發行說明。
keywords: 發行說明；發行；更新；未來發行；增強；新功能；修正
seo-description: 提供最新或即將發行的DNL Adobe target版本功能、增強功能和修正資訊的發行說明。
seo-title: Adobe target搶鮮版注意事項
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 9fa095b910b85f244b626c34cacdf9f4a13a6929

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新: 2019 年 10 月 2 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
>
>括號內的問題編號供 [!DNL Adobe] 內部使用。

## 目標平台

| 功能/增強功能 | 說明 |
| --- | --- |
| Node.js SDK 1.0版<br>（2019年10月9日） | Target Node.js SDK可讓您部署Target伺服器端。<br>此Node.js SDK可協助您輕鬆將Target與其他Experience cloud解決方案整合，例如Adobe Experience Cloud Identity Service、Adobe Analytics和Adobe Audience Manager。<br>Node.js SDK透過我們的傳送API與Adobe Target整合時引入最佳實務並免除複雜性，讓您的工程團隊可專注在商業邏輯上。 以下是我們在最新版本中推出的主要功能：<ul><li>支援預取和通知，讓您透過快取最佳化效能。</li><li>支援在網頁和伺服器端混合整合Target時最佳化效能。 我們將引入一個名為 `serverState` 的設定，由透過伺服器端擷取的體驗填入，如此at.js 2.2就不會再進行額外的伺服器呼叫來擷取體驗。 此方法可最佳化頁面載入效能。</li><li> 支援透過Node.js SDK擷取VEC建立的活動，此為新的傳送API所提供。</li><li>開放來源，讓您的開發人員可以為Node.js SDK貢獻心力。</li></ul>如需詳細資訊，請 [參閱版本注意事項- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)。 |
| 傳送API<br>（2019年10月9日） | 生產中將提供全新的傳送API端點（/v1/傳送）。 主要功能包括：<ul><li>一個端點，可擷取一或多個mbox的體驗。</li><li>透過API擷取VEC建立的活動。</li><li>支援稱為「檢視」的全新物件，用於單頁應用程式(SPA)和行動應用程式。</li></ul>如需詳細資訊，請 [參閱版本注意事項- Target伺服器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)。 |
| at.js 2.2<br><br>andat.js 1.8版<br>（待定日期） | 這些版本的at.js提供：<ul><li>已改善在網頁上同時使用Experience Cloud ID Service(ECID)v4.4和at.js 2.2或at.js 1.8時的效能。</li><li>之前，ECID曾進行兩次封鎖呼叫，之後at.js才能擷取體驗。 這已簡化為單一呼叫，可大幅提升效能。</li></ul> 為運用這些效能改良功能，請升級至at.js 2.2或at.js 1.8以及ECID Library v4.4。 |


## Target Standard/Premium 19.10.1 (2019 年 10 月 22 日)

| 功能/增強功能 | 說明 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) User-Based Recommendations | 根據每位訪客的瀏覽、檢視和購買記錄來建議項目。 這些項目通常稱為「為您推薦」。<br>此准則可讓您為新訪客和舊訪客提供個人化內容和體驗。 建議清單會針對訪客的最近活動加權，並會在工作階段中更新，當訪客瀏覽您的網站時，建議清單會變得更個人化。 |

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

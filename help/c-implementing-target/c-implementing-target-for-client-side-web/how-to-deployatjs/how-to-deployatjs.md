---
keywords: 實作;at.js;javascript 資料庫
description: 瞭解如何使用Adobe Experience Platform Launch或不使用標籤管理器來部署Adobe [!DNL Target] at.js JavaScript程式庫。
title: 如何部署at.js?
feature: 實作伺服器端
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 49%

---

# 如何部署 at.js

有關如何使用 Adobe Launch、不使用標記管理程式，或使用 Adobe 動態標籤管理 (DTM) 部署 Adobe Target JavaScript 程式庫和 at.js 的資訊。

您可使用下列方法部署 at.js:

* **[使用 Adobe Launch 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**: Launch 為 Adobe 新一代的標籤管理平台，且為實作 Adobe Target 的推薦方法。Launch 可讓客戶透過簡單的方式部署及管理所有必要的分析、行銷及廣告標籤功能，以便支援相關客戶體驗。
* **[不使用標籤管理員實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**: 您可以不使用標籤管理員 (Adobe Launch 或動態標籤管理) 實作 Target。
* **[使用動態標籤管理實作目標](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md)**:您可以使用Adobe動態標籤管理(DTM)(Adobe的舊版標籤管理器)來實作Target。Adobe Launch 為實作 Target 和 at.js 程式庫最新的推薦方法。如需進行新的 Target 實作，請使用 Launch。
* **使用協力廠商標籤管理器實作Target**: [Adobe](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) 啟動是實作Target的偏好方法；不過，您也可以使用協力廠商標籤管理器（例如Tealium、Ensighten、Google標籤等）來實作Target。如需使用Launch的優點清單，請參閱[使用Target Launch擴充功能實作at.js的優點](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304)。

   不過，如果您知道如何在沒有標籤管理程式的情況下實作Target，則可以輕鬆地使用協力廠商標籤管理程式來實作，而不是在網站程式碼中硬式編碼at.js。

   以下是兩個相關主題，可協助您使用協力廠商標籤管理器實作Target:

   * [實作之前](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [不使用標籤管理程式實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   如需詳細資訊，請務必檢查協力廠商標籤管理員的檔案。

若要在使用單頁應用程式 (SPA) 時實作 Target，請參閱[實作單頁應用程式](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

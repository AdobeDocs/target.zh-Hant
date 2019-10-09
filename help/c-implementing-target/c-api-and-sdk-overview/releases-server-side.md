---
description: 與Adobe Target伺服器端API和SDK相關的發行說明
keywords: at.js;api;release;updates;apis;sdks；伺服器端；伺服器端；api;delivery api
seo-description: 與Adobe Target伺服器端API相關的發行說明。
seo-title: 與Adobe Target伺服器端API相關的發行說明。
solution: Target
title: 發行說明——目標伺服器端API
topic: Standard
translation-type: tm+mt
source-git-commit: 434b103cee15e2e3efdb53febe15c689b5ccd48e

---


# 發行說明——目標伺服器端API

與 [Adobe Target伺服器端API相關的發行說明](https://developers.adobetarget.com/api/delivery-api/)。

## V1/傳送（2019年10月9日）

全新的傳送API端點已推出。

* New [documentation](https://developers.adobetarget.com/api/delivery-api/) is available.
* 一個端點，可擷取一或多個mbox的體驗。
* 透過API擷取VEC建立的活動。

   包含VEC建立之活動的回應包含選擇器，可用來僅預先隱藏頁面中需要個人化的部分。 這有助於最佳化您頁面的「第一個內容上色」量度 [，這是您企業在](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Google PageRank系統中獲得高分的重要KPI [](https://en.wikipedia.org/wiki/PageRank) 。

* 支援稱為「檢視」的全新物件，用於「單頁應 [用程式](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) (SPA)」和行 [動應用程式](/help/c-target-mobile-app/target-mobile-app.md)。
* 支援預取檢視和mbox，以透過快取最佳化效能。
* 支援傳送預取檢視和mbox的通知。

>[!IMPORTANT]
>
>您仍 [可存取舊版/v1/mbox和/v2/batchmbox API檔案](https://developers.adobetarget.com/api/legacy-api/index.html) 。 不過，新功能將在新的傳送API中開發，不會再移植回舊版API。

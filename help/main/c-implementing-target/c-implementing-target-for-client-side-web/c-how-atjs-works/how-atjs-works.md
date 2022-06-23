---
keywords: 系統圖;閃現;at.js;實作;javascript 程式庫;js;atjs
description: 了解  [!DNL Target] at.js JavaScript 程式庫如何運作，包括可幫助您了解頁面載入時的工作流程的系統圖。
title: at.js Javascript 程式庫如何運作？
feature: at.js
role: Developer
exl-id: 2193c02a-2a85-4ae1-bfbd-40fa7b87f0a0
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '1136'
ht-degree: 97%

---

# at.js 如何運作

若要在用戶端實作 [!DNL Adobe Target]，您必須使用 at.js JavaScript 程式庫。

在 [!DNL Adobe Target] 的用戶端實作中，[!DNL Target] 會將與活動相關聯的體驗直接提供給用戶端瀏覽器。瀏覽器會決定要顯示哪個體驗，然後顯示其內容。在用戶端實作中，您可以使用 WYSIWYG 編輯器、[視覺體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 或非視覺化介面[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，建立您的測試和個人化體驗。

## 什麼是 at.js?

at.js 程式庫是適用於 Target 的全新實作程式庫。 at.js 程式庫可加快網頁實作的頁面載入速度，並為單頁應用程式提供更好的實作選項。 at.js 為建議的實作程式庫，且經常更新功能。我們建議所有客戶實作或移轉至[最新版本的 at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)。

如需詳細資訊，請參閱 [Target JavaScript 程式庫](/help/main/c-intro/how-target-works.md#libraries)。

在下圖所示的 [!DNL Target] 實作中，已實作下列 [!DNL Adobe Experience Cloud] 解決方案：Analytics、Target 和 Audience Manager。 此外，也已實作下列 Experience Cloud 核心服務：[!DNL Adobe Experience Platform]、[!DNL Audiences] 和 [!DNL Visitor ID Service]。

## at.js 1.*x* 和 at.js 2.x 工作流程圖表之間有何差異？

請參閱[從 at.js 1.x 升級為 at.js 2.x](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)，深入瞭解 2.O 中引入哪些與 1.*x* 版有所差異之處。

從高階角度來看，兩個版本之間存在幾項差異:

* at.js 2.x 沒有全域 mbox 要求概念，而是採用頁面載入要求。頁面載入要求可視為要求擷取網站初始頁面載入時應套用的內容。
* at.js 2.x 可管理稱為「檢視」的概念，這些檢視會用於單頁應用程式 (SPA)。 at.js 1.*x* 不知道這個概念。

## at.js 2.x 圖表

下列圖表可協助您瞭解 at.js 2.x 搭配檢視的工作流程，以及如何藉由這套工作流程增強 SPA 整合。如需 at.js 2.x 中所使用概念的詳細介紹，請參閱[實作單頁應用程式](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/)。

![使用 at.js 2.x 的 Target 流程](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 步驟 | 詳細資料 |
| --- | --- |
| 1 | 如果使用者已通過驗證，呼叫會傳回 [!DNL Experience Cloud ID]，而另一個呼叫會同步客戶 ID。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>也能使用將頁面上實作的程式碼片段預先隱藏的選項，以非同步方式載入 at.js。 |
| 3 | 提出頁面載入要求，包含所有已設定的參數 (MCID、SDID 和客戶 ID)。 |
| 4 | 個人資料指令碼執行，然後注入個人資料存放區。存放區會從受眾資料庫中請求合格受眾 (例如，從 Adobe Analytics、受眾管理等共用的受眾)。<br>客戶屬性會透過批次程序傳送至個人資料存放區。 |
| 5 | [!DNL Target] 會根據 URL 要求參數和個人資料，決定可針對目前頁面和未來檢視傳回哪些活動和體驗給訪客。 |
| 6 | 目標內容會傳回至頁面，選擇性地包括其他個人化的個人資料值。<br>目前頁面上目標內容會儘快出現，不會有忽隱忽現的預設內容。<br>作為使用者在 SPA 中的操作結果而針對檢視顯示的內容將快取在瀏覽器中，這樣便可在透過 `triggerView()` 觸發檢視時立即套用，而不需要額外的伺服器呼叫。 |
| 7 | Analytics 資料傳送至「資料收集」伺服器。 |
| 8 | 目標資料會透過 SDID 來比對 Analytics 資料，然後經過處理放入 Analytics 報表儲存體中。然後就可以在 Analytics 與 Target 中，透過 Analytics for Target (A4T) 報表來檢視 <br>Analytics 資料。 |

現在，SPA 上只要是有實作 `triggerView()` 的位置，系統都會從快取擷取檢視和動作並向使用者顯示，不需要伺服器呼叫。`triggerView()` 也會對 [!DNL Target] 後端發出通知要求，以便增加和記錄曝光計數。如需針對採用檢視的 SPA 瞭解 at.js 的詳細資訊，請參閱[實作單頁應用程式](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/)。

![Target 流程 at.js 2.x triggerView](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 步驟 | 詳細資料 |
| --- | --- |
| 1 | 系統在 SPA 中呼叫 `triggerView()`，以便呈現檢視和套用動作來修改視覺元素。 |
| 2 | 從快取讀取檢視的目標內容。 |
| 3 | 目標內容會儘快出現，不會有忽隱忽現的預設內容。 |
| 4 | 通知要求會傳送至 [!DNL Target] 個人資料存放區，以計算活動中的訪客數和增加量度。 |
| 5 | Analytics 資料傳送至資料收集伺服器。 |
| 6 | Target 資料會透過 SDID 來比對 Analytics 資料，然後經過處理放入 Analytics 報表儲存體中。然後就可以在 Analytics 與 Target 中，透過 A4T 報表來檢視 Analytics 資料。 |

### 影片 - at.js 2.x 架構圖表

at.js 2.x 增強了Adobe Target 對 SPA 的支援，並與其他 Experience Cloud 解決方案整合。本影片說明整合方式。

>[!VIDEO](https://video.tv.adobe.com/v/26250)

如需詳細資訊，請參閱[ 了解 at.js 2.x 的運作方式](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html)。

## at.js 1.x 圖表

![Target 流程 - at.js 1.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/target-flow.png)

| 步驟 | 說明 | 呼叫 | 說明 |
|--- |--- |--- |--- |
| 1 | 如果使用者已驗證，呼叫會傳回 [!DNL Experience Cloud ID] (MCID)；另一個呼叫會同步客戶 ID。 | 2 | at.js 程式庫會同步載入並隱藏文件本文。 |
| 3 | 提出全域 mbox 請求，含所有已設定的參、MCID、SDID 和客戶 ID (可選)。 | 4 | 個人資料指令碼執行，然後注入個人資料存放區。存放區會從[!UICONTROL 受眾資料庫]中要求合格受眾 (例如從 [!DNL Adobe Analytics]、[!DNL Audience Manager] 等共用的受眾)。<br>客戶屬性會透過批次程序傳送至 [!DNL Profile Store]。 |
| 5 | [!DNL Target] 根據 URL、mbox 參數和個人資料，決定要傳回給訪客的活動和體驗。 | 6 | 已鎖定的目標內容會傳回至頁面，選擇性地包括其他個人化的個人資料值。<br>體驗會儘快出現，不會有忽隱忽現的預設內容。 |
| 7 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。 | 8 | [!DNL Target] 資料會透過 SDID 來比對 [!DNL Analytics] 資料，然後經過處理放入 [!DNL Analytics] 報表儲存體中。<br>[!DNL Analytics] 資料就可以透過 [!DNL Analytics for Target] (A4T) 報表在 [!DNL Analytics] 和 [!DNL Target] 中查看。 |

### 影片 - 辦公時間：at.js 提示與總覽 (2019 年 6 月 26 日)

這支影片記錄了「辦公時間」，「辦公時間」是一項由 Adobe 客戶服務團隊主導的計劃。

* 使用 at.js 的好處
* at.js 設定
* Flicker 處理
* 偵錯 at.js
* 已知問題
* 常見問答

>[!VIDEO](https://video.tv.adobe.com/v/27959)

## at.js 如何呈現具有 HTML 內容的選件 {#render}

呈現具有 HTML 內容的選件時，at.js 會套用下列演算法:

1. 預先載入影像 (如果 HTML 內容中有任何 `<img>` 標記)。

1. 將 HTML 內容附加至 DOM 節點。

1. 執行內嵌指令碼 (含括在 `<script>` 標記中的程式碼)。

1. 非同步載入並執行遠端指令碼 (具有 `src` 屬性的 `<script>` 標記)。

重要注意事項:

* at.js 不對遠端指令碼的執行順序提供任何保證，因為這些會以非同步的方式載入。
* 內嵌指令碼在遠端指令碼上不應有任何相依性，因為這些會在之後載入及執行。

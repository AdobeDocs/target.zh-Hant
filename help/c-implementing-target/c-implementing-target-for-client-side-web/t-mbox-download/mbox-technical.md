---
keywords: implementation;mbox.js;dom manipulation library;target.js;visual experience composer;iframe;angular sites;single page applications;single page app;SPA
description: 可協助您的技術人員瞭解 mbox.js 實作和它如何可能影響您的網站的資訊。
title: Mbox.js 的作用
feature: null
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 80%

---


# Mbox.js 的作用{#what-mbox-js-does}

可協助您的技術人員瞭解 mbox.js 實作和它如何可能影響您的網站的資訊。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 將不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>我們建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

Target Standard 需要 [!DNL mbox.js] 版本 58 或更新版。有關如何下載和更新 [!DNL mbox.js] 的指示，請參閱 [Mbox實作](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420)。

對於Target Standard，[!DNL mbox.js] 會呼叫另一個 JavaScript 檔案: [!DNL target.js]。[!DNL Target.js] 是由 Adobe 代管，也由 Adobe 自動更新。您不需要任何動作來更新 [!DNL target.js]，沒有用戶端特有的自訂。

[!DNL Target.js] 會在頁面的 `<head>` 區段中建立 mbox，稱為 `target-global-mbox`。

[!DNL Target.js] 是從 [!DNL mbox.js] 中，以 [!DNL mbox.js] 的 [!UICONTROL 額外 JavaScript] 欄位中新增的一行 JavaScript 程式碼來呼叫。停用 [!DNL target.js] 的唯一辦法是不要包含這行程式碼，因此也會停用 [!DNL Target]。

[!DNL Target.js] 在 [!DNL Target] 中有兩項功能:

* DOM 操作
* 啟用[!UICONTROL 可視化體驗撰寫器]的視覺化元素

## DOM 操作 {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] 控制 Standard 使用的 DOM 操作程式庫。為了顯示網站的內容，[!DNL target.js] 會參考 [!DNL sizzle.js] (1.10.8 版之前)。[!DNL Sizzle.js] 會啟用 HTML 元素選取器。除了 [!DNL sizzle.js]，只使用原生 JavaScript。不需要 jquery。

此外，使用下列程式碼片段來輪詢 DOM: 
`https://github.com/dperini/ContentLoaded`

## Target.js 和可視化體驗撰寫器 {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

當您使用[!UICONTROL 可視化體驗撰寫器]來設定活動的體驗時，您的網頁會在 iFrame 中開啟。載入 iFrame 時，Standard 會傳送 HTML5 `postMessage` API 呼叫。[!DNL Target.js] 會刪除任何 `postMessage` 呼叫，並在網站上包含下列 JavaScript 程式庫:

* 產生縮圖: [!DNL https://html2canvas.hertzen.com/]
* 跨網域查詢: [!DNL Admin.js]、[!DNL CDQ.base.js]、[!DNL CDQ.host.js]、[!DNL admin.css]，用於跨 iFrame 傳送訊息。這些指令碼可讓 Adobe 在頁面之間傳送資料。

## 關於 Angular 網站和單頁應用程式的考量  {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

如果您在 Angular 網站或任何單頁應用程式 (SPA) 中實作 Target，應該使用 at.js 程式庫，而不是 mbox.js。

如需詳細資訊，請參閱 [at.js 實作](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17)。

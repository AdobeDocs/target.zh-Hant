---
keywords: 實作;mbox.js;dom 操作資料庫;target.js;可視化體驗撰寫器;iframe;angular 網站;單頁應用程式;SPA
description: 了解Adobe Target的舊版mbox.js實作。 移轉至Adobe Experience Platform Web SDK(AEP Web SDK)或最新版at.js。
title: ' [!DNL Target] mbox.js程式庫有什麼作用？'
feature: at.js
role: Developer
exl-id: 62f0cbd2-17f0-43f4-98d3-ea39f314525e
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 78%

---

# Mbox.js 的作用

可協助您的技術人員瞭解 mbox.js 實作和它如何可能影響您的網站的資訊。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免您的網站出現任何潛在問題。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

## DOM 操作 {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] 控制 Standard 使用的 DOM 操作程式庫。為了顯示網站的內容，[!DNL target.js] 會參考 [!DNL sizzle.js] (1.10.8 版之前)。[!DNL Sizzle.js] 會啟用 HTML 元素選取器。除了 [!DNL sizzle.js]，只使用原生 JavaScript。不需要 jquery。

此外，使用下列程式碼片段來輪詢 DOM: 
`https://github.com/dperini/ContentLoaded`

## Target.js 和可視化體驗撰寫器 {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

當您使用[!UICONTROL 可視化體驗撰寫器]來設定活動的體驗時，您的網頁會在 iFrame 中開啟。載入 iFrame 時，Standard 會傳送 HTML5 `postMessage` API 呼叫。[!DNL Target.js] 會刪除任何 `postMessage` 呼叫，並在網站上包含下列 JavaScript 程式庫:

* 產生縮圖: [!DNL https://html2canvas.hertzen.com/]
* 跨網域查詢: [!DNL Admin.js]、[!DNL CDQ.base.js]、[!DNL CDQ.host.js]、[!DNL admin.css]，用於跨 iFrame 傳送訊息。這些指令碼可讓 Adobe 在頁面之間傳送資料。

## 關於 Angular 網站和單頁應用程式的考量 {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

如果您在 Angular 網站或任何單頁應用程式 (SPA) 中實作 Target，應該使用 at.js 程式庫，而不是 mbox.js。

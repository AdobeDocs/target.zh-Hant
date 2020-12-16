---
keywords: visual experience composer limitations;browser support;integrations;plugins;asynchronous considerations
description: at.js 與 mbox.js 之間有一些差異。此小節列出部分差異和限制，以協助您成功使用 at.js。
title: at.js 限制
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 100%

---


# at.js 限制{#at-js-limitations}

at.js 與 mbox.js 之間有一些差異。此小節列出部分差異和限制，以協助您成功使用 at.js。

## 可視化體驗撰寫器已知限制 {#section_4B63C97169DE4C93B22944E880FD3DF1}

* 在單頁應用程式中，應該避免使用可視化體驗撰寫器中的「插入元素」和「重新安排」選項。

   在單頁應用程式中的頁面載入事件上，因為 DOM 不會像在傳統網站中一樣地清除，所以「插入元素」和「重新安排」操作可能會重複套用多次，視訪客如何導覽 SPA 而定。

## 整合和外掛程式  {#section_D92E31170176406AAC7B5005F03D3425}

[!DNL mbox.js] 中沒有 [!DNL at.js] 內的某些函式。[!DNL at.js] 不再支援內部 [mbox.js 物件和方法](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) (例如 `mbox`、`mboxCurrent`、`mboxFactoryDefault`、`mboxFactories` 及其他，例如 `mboxFactoryDefault`)。這是刻意設計，目的是不勸阻您不要「駭入」[!DNL at.js] 來開發不受支援的功能，這些功能長期而言會削弱實施，導致實施無法升級。本說明文件的 API 頁面涵蓋唯一公開的方法。因此:

* 舊型頁面式[整合](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)搭配其他 Adobe 解決方案可能無法運作，應該升級至更新的伺服器端整合。
* [針對 mbox.js 開發的自訂外掛程式](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF)可能無法運作，除非針對 [!DNL at.js] 進行過更新。

   務必將所有[外掛程式](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF)均納入測試中。

## 非同步考量 {#section_B586360A3DD34E2995AE25A18E3FB953}

因為所有 mbox 現在非同步，它們將不會封鎖頁面呈現或在其觸發的訂單中傳回。

* 如果您在[表單式體驗撰寫器](/help/c-experiences/experiences.md#section_3643394BD424463C8768F2907DEBCC22)中使用全域 mbox，請注意 HTML 選件應該僅包含 `<style>`、`<script>` 以及 `<link>` 標籤。

   傳送期間，[!DNL at.js] 會在套用全域 mbox 選件時，篩選出所有其他的 HTML 標籤。全域 mbox 選件會套用至 HTML HEAD，不允許使用 DIV、SPAN 等。例如，無法套用 `<div>test</div>`，因為 `<div>` 標籤只能在 HTML BODY 中使用。

* 舊型頁面式 [!DNL Target] 與 [!DNL Analytics] 的整合將無法運作。

   此整合需要先執行 [!DNL Target] 呼叫之後才執行 [!DNL Analytics] 呼叫。

* 請注意選件和頁面之間的 JavaScript 相依性。

   請勿假定選件中的 JavaScript 會在 mbox 下方經過硬式編碼的 JavaScript 之前執行。

* 請注意頁面上多個選件之間的 JavaScript 相依性。

   您不能再假設第一個 mbox 傳送的選件將會在第二個 mbox 傳送的選件之前執行。

* DOM 操作和重新導向選件應該透過 [!DNL at.js] 中自動建立的全域 mbox 來傳送，並於 `<head>` 中傳送。

   `mboxCreate()` 頂端的 `<body>` 函數很可能導致預設內容忽隱忽現。


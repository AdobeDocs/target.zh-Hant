---
keywords: 實作；at.js;adobe experience platform web sdk;aep web sdk
description: 了解如何實作Adobe [!DNL Target] for client-side web using the Adobe Experience Platform Web SDK  (AEP Web SDK) or the [!DNL Target] at.js JavaScript資料庫。
title: 如何實作 [!DNL Target] 用於用戶端Web
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 47%

---

# 概述：實施 [!DNL Target] 用於用戶端web

在 [!DNL Adobe Target] 的用戶端實作中，[!DNL Target] 會將與活動相關聯的體驗直接提供給用戶端瀏覽器。瀏覽器會決定要顯示哪個體驗，然後顯示其內容。在用戶端實作中，您可以使用 WYSIWYG 編輯器、[可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 或非視覺化介面 ([表單式體驗撰寫器](/help/c-experiences/form-experience-composer.md))，建立您的活動和個人化體驗。

實作 [!DNL Adobe Target] 用戶端，您必須使用下列其中一個JavaScript程式庫：

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Target at.js JavaScript資料庫](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。Adobe 建議為避免網站出現任何潛在問題，請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本。
>
>* **Adobe Experience Platform Web SDK**:此 [!UICONTROL Adobe Experience Platform Web SDK] 可讓您與 [!DNL Experience Cloud] (包括 [!DNL Target])透過Adobe Experience Edge網路。 如果您選擇移轉至 [!DNL Adobe Experience Platform Web SDK]，請參閱 [什麼是Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) 在 *Web SDK指南*.
>
>* **at.js**:at.js JavaScript程式庫可改進Web實作的頁面載入時間、改進安全性，以及為單頁應用程式提供更好的實作選項。 如果您選擇移轉至at.js，請參閱 [At.js如何運作](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) 和 [Adobe Target技能培養者：開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).



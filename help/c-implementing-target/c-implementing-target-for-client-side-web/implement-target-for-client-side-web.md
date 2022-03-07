---
keywords: 實現；實現；at.js;adobe體驗平台web sdk;aep web sdk
description: 瞭解如何實施Adobe [!DNL Target] 用於客戶端Web，使用Adobe Experience PlatformWeb SDK(AEP Web SDK)或 [!DNL Target] at.js JavaScript庫。
title: 如何實施 [!DNL Target] 用於客戶端Web
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: 49bb4545f172af384c4b9a00248334b285632259
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 31%

---

# 概述：實施 [!DNL Target] 用於客戶端Web

在 [!DNL Adobe Target] 的用戶端實作中，[!DNL Target] 會將與活動相關聯的體驗直接提供給用戶端瀏覽器。瀏覽器會決定要顯示哪個體驗，然後顯示其內容。在用戶端實作中，您可以使用 WYSIWYG 編輯器、[可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 或非視覺化介面 ([表單式體驗撰寫器](/help/c-experiences/form-experience-composer.md))，建立您的活動和個人化體驗。

實施 [!DNL Adobe Target] 客戶端，必須使用以下JavaScript庫之一：

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)

   的 [!UICONTROL Adobe Experience PlatformWeb SDK] 允許您與 [!DNL Experience Cloud] (包括 [!DNL Target])。 如果選擇遷移到 [!DNL Adobe Experience Platform Web SDK]，請參閱 [什麼是Adobe Experience PlatformWeb SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) 的 *Web SDK指南*。

* [目標at.js JavaScript庫](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

   at.js JavaScript庫改進了Web實現的頁面載入時間，提高了安全性，並為單頁應用程式提供了更好的實現選項。 如果選擇遷移到at.js，請參閱 [At.js工作原理](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) 和 [Adobe Target技能構建器：開發人員聊天，將Adobe Target的mbox.js遷移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。




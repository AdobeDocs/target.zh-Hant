---
keywords: implement;implementation;at.js;adobe experience platform web sdk;aep web sdk
description: 有關使用at.js為用戶端網頁實作Adobe Target的資訊。
title: 為用戶端 Web 實作 Adobe Target
feature: at.js
translation-type: tm+mt
source-git-commit: a85a5c10c31fb0d7eb00c21ff03b2012d044de45
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 20%

---


# 概覽: 為用戶端 Web 實作 Target

在 [!DNL Adobe Target] 的用戶端實作中，[!DNL Target] 會將與活動相關聯的體驗直接提供給用戶端瀏覽器。瀏覽器會決定要顯示哪個體驗，然後顯示其內容。在用戶端實作中，您可以使用 WYSIWYG 編輯器、[可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 或非視覺化介面 ([表單式體驗撰寫器](/help/c-experiences/form-experience-composer.md))，建立您的活動和個人化體驗。

若要實作[!DNL Adobe Target]用戶端，您必須使用下列其中一個JavaScript程式庫：

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Target at.js JavaScript程式庫](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 將不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。 我們建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。
>
>* **Adobe Experience Platform Web SDK**:Adobe  [!UICONTROL Experience Platform Web ] SDK可讓您透過Adobe Experience Edge Network [!DNL Experience Cloud] (包括 [!DNL Target])與各種服務互動。如果您選擇移轉至[!DNL Adobe Experience Platform Web SDK]，請參閱&#x200B;*網頁SDK指南*&#x200B;中的[什麼是Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。
   >
   >
* **at.js**:at.js JavaScript程式庫提供許多優於mbox.js的優點。除了其他優點，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。 如果您選擇移轉至at.js，請參閱[At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[Adobe Target技能產生器：開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
>
>
雖然目前支援mbox.js（直到2021年3月31日），但自2017年7月起，我們尚未提供此程式庫的功能更新。 透過將所有客戶移至[!UICONTROL Adobe Experience Platform Web SDK]或at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。

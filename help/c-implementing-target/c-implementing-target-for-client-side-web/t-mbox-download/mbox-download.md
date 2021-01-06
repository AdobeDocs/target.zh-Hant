---
keywords: implementation;mbox;download mbox.js;download api;mbox.js api
description: 若要使用Adobe Target Standard或Target Premium，請新增一行程式碼以呼叫mbox.js。
title: mbox.js 實作
feature: null
translation-type: tm+mt
source-git-commit: 863c5137383d35b2eaa33082c2136b81793281ca
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 30%

---


# mbox.js 實作

若要使用[!DNL Adobe Target Standard]或[!DNL Target Premium]，請新增一行程式碼以呼叫mbox.js。

您可以使用兩個庫參照之一：[!DNL Adobe Experience Platform Web SDK]或[!DNL at.js]。 [at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsex的優點可彌補mbox.js和at.js程式庫的差異。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 將不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。 我們建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。
>
>* **Adobe Experience Platform Web SDK**:Adobe  [!UICONTROL Experience Platform Web ] SDK可讓您透過Adobe Experience Edge Network [!DNL Experience Cloud] (包括 [!DNL Target])與各種服務互動。如果您選擇移轉至[!DNL Adobe Experience Platform Web SDK]，請參閱&#x200B;*網頁SDK指南*&#x200B;中的[什麼是Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)。 如需[!DNL Target]特定資訊，請參閱[Target overview](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)。
   >
   >
* **at.js**:at.js JavaScript程式庫提供許多優於mbox.js的優點。除了其他優點，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。 如果您選擇移轉至at.js，請參閱[At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[Adobe Target技能產生器：開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
>
>
雖然目前支援mbox.js（直到2021年3月31日），但自2017年7月起，我們尚未提供此程式庫的功能更新。 透過將所有客戶移至[!UICONTROL Adobe Experience Platform Web SDK]或at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。

每個頁面上 [!DNL mbox.js] 的單一參考可提供您的所有活動所需的資料庫。[!DNL mbox.js] 會從參考 [!DNL Target] 檔案的每個頁面呼叫 [!DNL mbox.js]。如此可讓 [!DNL Target] 執行下列動作:

* 傳送 Target 活動
* 追蹤點擊
* 追蹤最成功量度

>[!TIP]
>
>若要簡化實作，您可以在全域標頭中參照 [!DNL mbox.js]。

您不需要維護不同的活動特定版本檔案。

1. 在網站上每個頁面的 [!DNL mbox.js] 區段參照 `<head>`。

   `<script src="/ *`目錄`*/ *`指令碼`*/mbox.js"></script>`

   ` *`目錄`*/ *`指令碼`*`為下載 [!DNL mbox.js] 檔案之後，儲存該檔案的所在目錄。如果您的頁面中已有來自舊版實施的 mbox，這些 mbox 仍可在新介面中使用。仍需要更新的 [!DNL mbox.js] 檔案，但可以使用[!UICONTROL 可視化體驗撰寫器]為活動選取這些 mbox 並加以編輯。
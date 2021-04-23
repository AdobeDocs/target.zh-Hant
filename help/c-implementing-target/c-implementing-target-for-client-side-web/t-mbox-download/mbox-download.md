---
keywords: 實施；mbox；下載mbox.js；下載api;mbox.js api
description: 瞭解Adobe Target的舊版mbox.js實作。 移轉至Adobe Experience Platform網頁SDK（AEP網頁SDK）或最新版的at.js。
title: 如何使用mbox.js實作 [!DNL Target] ?
feature: at.js
role: Developer
exl-id: 105095d7-8e29-413b-a7f4-e46e2e30e91f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 47%

---

# mbox.js 實作

若要使用[!DNL Adobe Target Standard]或[!DNL Target Premium]，請新增一行程式碼以呼叫mbox.js。

您可以使用兩個庫參照之一：[!DNL Adobe Experience Platform Web SDK]或[!DNL at.js]。 [at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsex的優點可彌補mbox.js和at.js程式庫的差異。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>我們建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

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

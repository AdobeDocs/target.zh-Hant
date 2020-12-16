---
keywords: Implementation;Mbox;download mbox.js;download api;mbox.js api
description: 若要使用 Target Standard 或 Target Premium，請新增一行程式碼以呼叫 mbox.js。
title: mbox.js 實作
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 55%

---


# mbox.js 實作{#mbox-js-implementation}

若要使用 Target Standard 或 Target Premium，請新增一行程式碼以呼叫 mbox.js。

您可以使用兩個資料庫參考中的一個: [!DNL mbox.js] 或 [!DNL at.js]。[at.js 的優點](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits)說明兩種資料庫之間的差異。

>[!NOTE]
>
>**mbox.js生命週期結束**:自2021年1月18日起，Adobe Target將不再支援mbox.js程式庫。在2021年1月18日後，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 如需詳細資訊，請參閱[At.js如何運作](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)。
>
>雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
>
>透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。

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
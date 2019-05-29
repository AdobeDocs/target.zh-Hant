---
description: 若要使用 Target Standard 或 Target Premium，請新增一行程式碼以呼叫 mbox.js。
keywords: 實作;Mbox;下載 mbox.js;下載 api;mbox.js api
seo-description: 若要使用 Target Standard 或 Target Premium，請新增一行程式碼以呼叫 mbox.js。
seo-title: mbox.js 實作
solution: Target
subtopic: 快速入門
title: mbox.js 實作
topic: Standard
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
translation-type: tm+mt
source-git-commit: ac86b0131b0c65f3367c47b3a1315c37d9b9aa93

---


# mbox.js 實作{#mbox-js-implementation}

若要使用 Target Standard 或 Target Premium，請新增一行程式碼以呼叫 mbox.js。

您可以使用兩個資料庫參考中的一個: [!DNL mbox.js] 或 [!DNL at.js]。[at. js的優點](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) 說明兩個程式庫之間的差異。

>[!NOTE]
>
>系統仍支援 mbox.js 程式庫，但將不會提供功能更新。所有客戶應該移轉至 at.js。如需詳細資訊，請參閱[從 mbox.js 移轉至 at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)。

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
---
keywords: 實作；mbox；下載mbox.js；下載api;mbox.js api
description: 了解Adobe Target的舊版mbox.js實作。 移轉至Adobe Experience Platform Web SDK(AEP Web SDK)或最新版at.js。
title: 如何使用mbox.js實作 [!DNL Target] ?
feature: at.js
role: Developer
exl-id: 105095d7-8e29-413b-a7f4-e46e2e30e91f
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 65%

---

# mbox.js 實作

若要使用[!DNL Adobe Target Standard]或[!DNL Target Premium]，請新增一行程式碼以呼叫mbox.js。

您可以使用兩個程式庫參考的其中一個：[!DNL Adobe Experience Platform Web SDK]或[!DNL at.js]。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免您的網站出現任何潛在問題。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

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

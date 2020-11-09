---
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox
description: 透過在網頁上參考 Target 資料庫 (at.js 或 mbox.js) 來實作 Target。
title: 瞭解 Target JavaScript 程式庫
feature: implementation general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 100%

---


# 瞭解 [!DNL Target]JavaScript 資料庫{#understand-the-target-javascript-libraries}

透過在網頁上參考 [!DNL Target] 資料庫 (at.js 或 mbox.js) 來實作 [!DNL Target]。

>[!NOTE]
>
>將不再開發 mbox.js 資料庫。所有客戶應該從 mbox.js 移轉至 at.js。如需詳細資訊，請參閱[從 mbox.js 移轉至 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)。

## 兩個程式庫之間的差異 {#section_40117C78C2F84FECAC4F1BA40CC4F171}

下表說明兩個程式庫之間的差異:

| 程式庫參考 | 說明 |
|--- |--- |
| at.js | at.js 取代了 實施的 mbox.js。[!DNL Target]<br>除了眾多優點以外，at.js 還能改進 Web 實施的頁面載入時間、改進安全性、避免 Google Chrome 中的 document.write 警告，以及為單頁應用程式提供更好的實施選項。<br>如需詳細資訊，請參閱 [at.js 實作](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md)。 |
| mbox.js | 在 [!DNL Target] 16.3.1 (2016 年 3 月) 之前的版本中，[!DNL Target] 需要呼叫 mbox.js 來建立全域 mbox，[!DNL Target] 需要此全域 mbox 才能傳送活動、追蹤點擊，以及追蹤大部分成功量度。此檔案包含所有活動所需的資料庫。您不需要維護不同的活動特定版本檔案。<br>如果您的頁面上已有來自舊型 [!DNL Target] 實作的包裝 mbox，則這些 mbox 仍可用在新介面中。仍需要更新的 mbox.js 檔案，但可以使用可視化體驗撰寫器為活動選取這些 mbox 並加以編輯。<br>[!DNL Target] Standard 和 Premium 會以 target.js 檔案的參照來更新和補充 mbox.js。target.js 檔案是由 Adobe 管理。此 Target.js 檔案可讓您使用可視化體驗撰寫器來編輯任何頁面的內容，即使該頁面不含預先定義的 mbox 也一樣。您必須在網站的每一個頁面上參照此檔案。<br>如需詳細資訊，請參閱 [mbox.js 實作](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)。<br>**重要**: 仍支援 mbox.js 資源庫，但將不會提供功能更新。所有客戶應該移轉至 at.js。如需詳細資訊，請參閱[從 mbox.js 移轉至 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)<br>。 |

## at.js 和 mbox.js 對頁面載入時間的影響 {#section_16630CD0FF0A498EB596A51381366A5A}

許多客戶和顧問都想要知道 [!DNL at.js] 和 [!DNL mbox.js] 對頁面載入時間的影響，尤其是在比較新使用者和再度訪問的使用者時。可惜，有關 [!DNL at.js] 或 [!DNL mbox.js] 如何影響頁面載入時間，由於每一個客戶的實施不同，很難測量和提出具體數字。

不過，如果頁面上有「訪客 API」，我們就能更充分的瞭解 [!DNL at.js] 和 [!DNL mbox.js] 如何影響頁面載入時間。

>[!NOTE]
>
>只有當使用全域 mbox 時，「訪客 API」和 [!DNL at.js] 或 [!DNL mbox.js] 才會影響頁面載入時間 (原因在於主體隱藏技術)。訪客 API 整合不影響地區 mbox。

以下小節說明新訪客和再度造訪的訪客的動作序列:

### 新訪客

1. 訪客 API 會載入、剖析和執行。
1. at.js / mbox.js 會載入、剖析和執行。
1. 如果已啟用全域 mbox 自動建立，Target JavaScript 資料庫:

   * 實體化訪客物件。
   * Target 資料庫會嘗試擷取 Experience Cloud 訪客 ID 資料。
   * 因為這是新訪客，「訪客 API」會向 demdex.net 發出跨網域請求。
   * 擷取 Experience Cloud 訪客 ID 資料之後，即會觸發對 Target 的要求。

### 再度訪問的訪客

1. 訪客 API 會載入、剖析和執行。
1. at.js / mbox.js 會載入、剖析和執行。
1. 如果已啟用全域 mbox 自動建立，Target JavaScript 資料庫:

   * 實體化訪客物件。
   * Target 資料庫會嘗試擷取 Experience Cloud 訪客 ID 資料。
   * 訪客 API 會從 Cookie 擷取資料。
   * 擷取 Experience Cloud 訪客 ID 資料之後，即會觸發對 Target 的要求。

>[!NOTE]
>
>對於新訪客，當「訪客 API」存在時，Target 必須通過網路許多次，以確定 Target 請求包含 Experience Cloud 訪客 ID 資料。對於再度訪問的訪客，Target 只會通過網路到 Target 來擷取個人化內容。

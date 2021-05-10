---
keywords: document.write;target;implement;target;dtm;at.js;mbox.js;mbox;adobe體驗平台Web skd;aep網頁sdk
description: 在您的網頁上實作Adobe [!DNL Target] by referencing the [!DNL Target] 程式庫（at.js或mbox.js）。
title: 瞭解  [!DNL Target] JavaScript 資料庫
feature: 實施
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 24%

---


# 瞭解 [!DNL Target]JavaScript 資料庫

在您的網頁上參考[!DNL Adobe Target]程式庫(Adobe Experience Platform網頁SDK或at.js)，實作[!DNL Adobe Target]。

>[!NOTE]
>
>將不再開發 mbox.js 資料庫。所有客戶必須在2021年3月31日之前從mbox.js移轉至at.js或[!UICONTROL Adobe Experience Platform網頁SDK]。 如需詳細資訊，請參閱「從mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)移轉至at.js」或「[Adobe Experience Platform網頁SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)」。[

## [!DNL Target] JavaScript程式庫{#section_40117C78C2F84FECAC4F1BA40CC4F171}之間的差異

下表說明[!DNL Target] JavaScript程式庫之間的差異：

| 程式庫參考 | 說明 |
|--- |--- |
| Adobe Experience Platform Web SDK | [!UICONTROL Adobe Experience Platform網頁SDK]可讓您透過Adobe Experience Edge Network與[!DNL Experience Cloud]（包括[!DNL Target]）中的各種服務互動。 如果您選擇移轉至[!DNL Adobe Experience Platform Web SDK]，請參閱&#x200B;*Web SDK指南*&#x200B;中的[什麼是Adobe Experience PlatformWeb SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。 |
| at.js | at.js取代[!DNL [!DNL Target]]實作的mbox.js。<br>除了眾多優點以外，at.js 還能改進 Web 實施的頁面載入時間、改進安全性、避免 Google Chrome 中的 document.write 警告，以及為單頁應用程式提供更好的實施選項。<br>如需詳細資訊，請參閱 [at.js 實作](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md)。 |

## at.js對頁面載入時間{#section_16630CD0FF0A498EB596A51381366A5A}的影響

許多客戶和顧問都想瞭解[!DNL at.js]對頁面載入時間的影響，尤其是在新使用者與舊使用者之間。 遺憾的是，很難測量並提供具體數字，說明[!DNL at.js]如何因每位客戶的實施而影響頁面載入時間。

但是，如果訪客API存在於頁面上，[!DNL Target]可更清楚瞭解[!DNL at.js]如何影響頁面載入時間。

>[!NOTE]
>
>訪客API和[!DNL at.js]僅在您使用全域mbox時（因為使用內文隱藏技術），才會影響頁面載入時間。 訪客 API 整合不影響地區 mbox。

以下小節說明新訪客和再度造訪的訪客的動作序列:

### 新訪客

1. 訪客 API 會載入、剖析和執行。
1. at.js會載入、剖析並執行。
1. 如果全域mbox自動建立已啟用，[!DNL Target] JavaScript程式庫：

   * 實體化訪客物件。
   * [!DNL Target]程式庫會嘗試擷取[!UICONTROL Experience Cloud訪客ID]資料。
   * 對於新訪客，訪客API會觸發`demdex.net`的跨網域請求。
   * 擷取[!UICONTROL Experience Cloud訪客ID]資料後，會引發對Target的請求。

### 再度訪問的訪客

1. 訪客 API 會載入、剖析和執行。
1. at.js會載入、剖析並執行。
1. 如果全域mbox自動建立已啟用，[!DNL Target] JavaScript程式庫：

   * 實體化訪客物件。
   * [!DNL Target]程式庫會嘗試擷取[!UICONTROL Experience Cloud訪客ID]資料。
   * 訪客 API 會從 Cookie 擷取資料。
   * 擷取[!UICONTROL Experience Cloud訪客ID]資料後，會引發對[!DNL Target]的請求。

>[!NOTE]
>
>對於新訪客，當訪客API存在時，[!DNL Target]會多次瀏覽網路，以確定[!DNL Target]請求包含[!UICONTROL Experience Cloud訪客ID]資料。 若是舊訪客，[!DNL Target]只會越線至[!DNL Target]以擷取個人化內容。

---
keywords: document;write；目標；實作；實作目標；dtm;at.js;mbox.js;target.js;mbox;adobe experience platform web skd;aep web sdk;web sdk
description: 在您的網頁上實作Adobe [!DNL Target] by referencing the [!DNL Target] 程式庫（at.js或mbox.js）。
title: 瞭解  [!DNL Target] JavaScript 資料庫
feature: 實施
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 24%

---


# 瞭解 [!DNL Target]JavaScript 資料庫

透過在網頁上參考[!DNL Adobe Target]資料庫(Adobe Experience Platform Web SDK或at.js)來實作[!DNL Adobe Target]。

>[!NOTE]
>
>將不再開發 mbox.js 資料庫。所有客戶必須在2021年3月31日之前從mbox.js移轉至at.js或[!UICONTROL Adobe Experience Platform Web SDK]。

## [!DNL Target] JavaScript程式庫之間的差異 {#section_40117C78C2F84FECAC4F1BA40CC4F171}

下表說明[!DNL Target] JavaScript程式庫之間的差異：

| 程式庫參考 | 說明 |
|--- |--- |
| Adobe Experience Platform Web SDK | [!UICONTROL Adobe Experience Platform Web SDK]可讓您透過Adobe Experience Edge Network與[!DNL Experience Cloud]（包括[!DNL Target]）中的各種服務互動。 如果您選擇移轉至[!DNL Adobe Experience Platform Web SDK]，請參閱&#x200B;*Web SDK指南*&#x200B;中的[什麼是Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。 |
| at.js | at.js取代了[!DNL [!DNL Target]]實作的mbox.js。<br>除了眾多優點以外，at.js 還能改進 Web 實施的頁面載入時間、改進安全性、避免 Google Chrome 中的 document.write 警告，以及為單頁應用程式提供更好的實施選項。 |

## at.js對頁面載入時間的影響 {#section_16630CD0FF0A498EB596A51381366A5A}

許多客戶和顧問都想知道[!DNL at.js]對頁面載入時間的影響，尤其是在新使用者和再度訪問的使用者的情境中。 很可惜，有關[!DNL at.js]如何影響頁面載入時間，由於每個客戶的實作不同，很難測量並提供具體數字。

不過，如果頁面上存在訪客API,[!DNL Target]可更清楚了解[!DNL at.js]如何影響頁面載入時間。

>[!NOTE]
>
>只有在您使用全域mbox時，「訪客API」和[!DNL at.js]才會影響頁面載入時間（原因在於主體隱藏技術）。 訪客 API 整合不影響地區 mbox。

以下小節說明新訪客和再度造訪的訪客的動作序列:

### 新訪客

1. 訪客 API 會載入、剖析和執行。
1. at.js會載入、剖析及執行。
1. 如果已啟用全域mbox自動建立，[!DNL Target] JavaScript程式庫：

   * 實體化訪客物件。
   * [!DNL Target]程式庫會嘗試擷取[!UICONTROL Experience Cloud訪客ID]資料。
   * 對於新訪客，訪客API會向`demdex.net`觸發跨網域請求。
   * 擷取[!UICONTROL Experience Cloud訪客ID]資料後，會引發對Target的要求。

### 再度訪問的訪客

1. 訪客 API 會載入、剖析和執行。
1. at.js會載入、剖析及執行。
1. 如果已啟用全域mbox自動建立，[!DNL Target] JavaScript程式庫：

   * 實體化訪客物件。
   * [!DNL Target]程式庫會嘗試擷取[!UICONTROL Experience Cloud訪客ID]資料。
   * 訪客 API 會從 Cookie 擷取資料。
   * 擷取[!UICONTROL Experience Cloud訪客ID]資料後，會引發對[!DNL Target]的要求。

>[!NOTE]
>
>若為新訪客，當訪客API存在時，[!DNL Target]會多次穿過電線，以確定[!DNL Target]請求包含[!UICONTROL Experience Cloud訪客ID]資料。 若為再度訪問的訪客，[!DNL Target]只會越線前往[!DNL Target]以擷取個人化內容。

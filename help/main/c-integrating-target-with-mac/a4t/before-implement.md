---
keywords: 建議
description: 瞭解Analytics的實作需求 [!DNL Target] (A4T)以及實作此整合前須考慮的事項。
title: 實作A4T之前，我應該瞭解什麼？
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 26%

---

# 使用 at.js 實作 Analytics for Target (A4T) 之前

啟用時，您的資料收集程式會發生一些變更 [!DNL Adobe Analytics] 作為的報表來源 [!DNL Adobe Target] (A4T)。

決定用此整合之前，請檢閱下列各節，並考量對報表程序造成的影響.

>[!NOTE]
>
>本文僅適用於at.js實作。

## 實作需求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>開始使用A4T之前，您必須要求您的帳戶已布建為整合。 使用 [Marketing Cloud整合布建表單](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank} 以要求布建帳戶。

視您是否要搭配A4T使用重新導向選件而定，此A4T整合需要您實作下列程式庫版本（或更新版本）。

>[!NOTE]
>
>下列需求列出 *最小值* 實作A4T所需的at.js版本。 此 [!DNL Target] team只會維護兩個版本的 [!DNL at.js] — 目前版本和次新版本。 請視需要升級 [!DNL at.js]，以確保您執行的是支援的版本。如需每個版本有何功能的詳細資訊，請參閱 [at.js版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

### *不*&#x200B;搭配 A4T 使用重新導向選件之情況下的需求

如果您不打算搭配 A4T 使用重新導向選件，則此整合需要您實作下列程式庫版本 (或更新版本)。列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]： visitorAPI.js版本1.8.0
* [!DNL Adobe Target]: at.js 0.9.1 版
* Adobe Analytics: appMeasurement.js 版本 1.7.0

如需有關使用實作A4T的資訊 [!DNL Platform Web SDK]，請參閱 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

### 搭配 A4T 使用重新導向選件之情況下的需求

若要搭配 A4T 來使用重新導向選件，您必須實作下列程式庫版本 (或更新版本).列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]： visitorAPI.js版本2.3.0

   >[!NOTE]
   >
   >at.js 1.8.0+ 和 at.js 2.x+ 不再搭配使用 2.5.0 之前的訪客 API 版本以傳遞 Adobe Audience Manager (AAM) 參數。

* [!DNL Adobe Target]: at.js 1.6.2 版

* Adobe Analytics: appMeasurement.js 版本 2.1

下載和部署指示列於 [Analytics for Target實作](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

如需有關使用實作A4T的資訊 [!DNL Platform Web SDK]，請參閱 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

## 實施前須知 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 當您選取使用時，會在新活動上啟用此整合 [!DNL Analytics] 作為報表來源。 當您如本文所述進行實作變更時，現有的活動不受影響。
* 設定程式 [!DNL Analytics] 作為的報表來源 [!DNL Target] 包含數個實作步驟，以及布建步驟。 實作之前，最好閱讀一遍如下所述的程序。完成這些步驟後，您就可以使用 [!DNL Analytics] 當您啟用報表來源時，可作為您的報表來源。 佈建程序最多可能需要五個工作天。
* 此 [!DNL Visitor ID service] 建立共用的 [!DNL Visitor ID] 橫跨 [!DNL Adobe Experience Cloud]. 雖然它不會取代 [!DNL Target] mboxPC ID或 [!DNL Audience Manager] UUID，它確實會取代 [!DNL Analytics] 會識別新訪客。 如果設定正確，請傳回 [!DNL Analytics] 訪客也應透過其舊身分識別 [!DNL Analytics] ID。 同樣地，因為 [!DNL Target] mboxPCid保持不變，否 [!DNL Target] 當您升級至 [!DNL Visitor ID service].
* 此 [!DNL Visitor ID service] 必須在您的之前 [!DNL Analytics] 和 [!DNL Target] 頁面代碼。 請確定 `VisitorAPI.js` 出現在所有其他標籤的標籤上方 [!DNL Experience Cloud] 解決方案。

## 延遲性 {#section_9489BE6FD21641A4844E591711E3F813}

啟用這項整合後，您會在以下專案遇到額外5至10分鐘的延遲： [!DNL Analytics]. 延遲增加可讓資料來自 [!DNL Analytics] 和 [!DNL Target] 將儲存在相同點選上，讓您能夠依頁面和網站區段劃分活動。

此增加會反映在所有 [!DNL Analytics] 服務和工具（包括即時資料流和即時報表），適用於下列情況：

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 對於轉換量度、最終完成的資料和資料摘要的目前資料，所有點選都會額外延遲5至7分鐘。

延遲增加會在您實作 [!DNL Experience Cloud] 訪客ID服務，即使您尚未完全實作此整合亦然。

## 補充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

全部 [!DNL Target] A4T活動用來傳遞內容或記錄目標量度的呼叫必須具有對應的 [!DNL Analytics] 共用A4T補充ID的點選可正常運作。

包含下列專案資料的點選： [!DNL Analytics] 和 [!DNL Target] 包含補充資料ID。 您可在以下連結中看到此ID： [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) 作為 `sdid` 引數。 例如: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`。只要符合下列條件即會產生此 ID:

* 已實作訪客 ID 服務

時間 [疑難排解](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)，請務必確認上存在補充ID [!DNL Analytics] 點選。

## 用戶端分析記錄 {#client-side}

如果at.js， [!DNL Experience Cloud Visitor ID Service]和appMeasurement.js位於頁面上， [!DNL Analytics]、和 [!DNL Target] 只要頁面中包含正確的補充ID，便可在後端正確地彙整事件，以用於報告和分析目的。 您不需要管理及執行任何其他操作，A4T就能正常運作。

在某些情況下，您可能會想要進一步掌控要傳送相關分析資料的時間和方式 [!DNL Target] 至 [!DNL Analytics] 以供製作報表之用。 您可能有供內部使用的內部分析工具。 不過，您也要將分析資料傳送至 [!DNL Analytics] 透過您的內部分析產品，讓貴組織的其他成員可以繼續使用 [!DNL Analytics] 作為視覺報表來源。 另請參閱 [步驟7：在所有網站頁面上參照at.js](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) 在 *Analytics for Target實作* 以取得詳細資訊。

## 共用對象

填入 [Marketing Cloud整合布建表單](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}，請留意以下有關 [!UICONTROL 共用受眾] 「 」下列出的選項[!UICONTROL 您請求布建哪些功能]？」

![請求表單](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

當您要求時 [!UICONTROL 共用受眾]，您啟用 [!UICONTROL Target] 和 [!UICONTROL Adobe Audience Manager] (AAM)以共用資訊，在此例中是受眾。

>[!IMPORTANT]
>
>此項整合介於 [!UICONTROL Target] 而AAM則提供額外費用。 您需為每個使用者付費 [!UICONTROL Target] 呼叫AAM。

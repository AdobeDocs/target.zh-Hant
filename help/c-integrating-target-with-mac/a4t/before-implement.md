---
keywords: Recommendations
description: 瞭解Analytics的 [!DNL Target] (A4T)實作需求，以及實施此整合前要考慮的事項。
title: 在實作A4T之前，我應該知道什麼？
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: b14c9bb4bc0363c77de084c7ae7110e73c5f2f13
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 33%

---

# 在您使用at.js實作Analytics for Target(A4T)之前

啟用[!DNL Adobe Analytics]作為[!DNL Adobe Target](A4T)的報告來源時，資料收集程式會發生數項變更。

決定用此整合之前，請檢閱下列各節，並考量對報表程序造成的影響.

>[!NOTE]
>
>本文僅適用於at.js實作。

## 實作需求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>您必須要求已布建您的帳戶以進行整合，才能開始使用A4T。 使用[Marketing Cloud整合布建表單](https://www.adobe.com/go/audiences_tw)請求布建。

視您是否要搭配 A4T 使用重新導向選件而定，此 A4T 整合需要您實作下列資料庫版本 (或更新版本):

### *不*&#x200B;搭配 A4T 使用重新導向選件之情況下的需求

如果您不打算搭配 A4T 使用重新導向選件，則此整合需要您實作下列程式庫版本 (或更新版本)。列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js 1.8.0版
* [!DNL Adobe Target] (根據您的實作): at.js 版本 0.9.1 或 mbox.js 版本 61
* Adobe Analytics: appMeasurement.js 版本 1.7.0

### 搭配 A4T 使用重新導向選件之情況下的需求

若要搭配 A4T 來使用重新導向選件，您必須實作下列程式庫版本 (或更新版本).列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js 2.3.0版
* [!DNL Adobe Target]: at.js 1.6.2 版

   **注意:** mbox.js 資料庫不支援使用 A4T 重新導向選件。您的實作必須使用 at.js。

* Adobe Analytics: appMeasurement.js 版本 2.1

下載和部署指示列在[Analytics for Target實施](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)中。

## 實施前須知 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 當您選擇使用[!DNL Analytics]作為報告來源時，此整合會在新活動上啟用。 當您如本文所述進行實作變更時，現有的活動不受影響。
* 將[!DNL Analytics]設為[!DNL Target]的報告來源的程式包括幾個實施步驟，然後是設定步驟。 實作之前，最好閱讀一遍如下所述的程序。完成這些步驟後，您就可以在為您啟用[!DNL Analytics]時，將其用作報告源。 佈建程序最多可能需要五個工作天。
* [!DNL Visitor ID service]會跨[!DNL Adobe Experience Cloud]建立共用的[!DNL Visitor ID]。 雖然它不會取代[!DNL Target] mboxPC id或[!DNL Audience Manager] UUID，但會取代[!DNL Analytics]識別新訪客的方式。 如果設定正確，還應透過舊的[!DNL Analytics] ID識別傳回的[!DNL Analytics]訪客。 同樣地，由於[!DNL Target] mboxPCid保持不變，因此升級至[!DNL Visitor ID service]時不會遺失[!DNL Target]訪客資料。
* [!DNL Visitor ID service]必須在[!DNL Analytics]和[!DNL Target]頁面代碼之前執行。 請確定`VisitorAPI.js`出現在所有其他[!DNL Experience Cloud]解決方案的標籤上方。

## 延遲性 {#section_9489BE6FD21641A4844E591711E3F813}

啟用此整合後，您會在[!DNL Analytics]中遇到5-10分鐘的額外延遲。 延遲增加可讓[!DNL Analytics]和[!DNL Target]的資料儲存在相同的點擊上，讓您依頁面和網站區段劃分活動。

此增加反映在所有[!DNL Analytics]服務和工具中，包括即時串流和即時報告，並適用於下列情況：

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 對於轉換量度、已完成資料和資料饋送的目前資料，所有點擊都會延遲5-7分鐘。

延遲增加會在您實作[!DNL Experience Cloud]訪客ID服務後開始，即使您尚未完全實作此整合亦然。

## 補充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4T活動用來傳送內容或記錄目標量度的所有[!DNL Target]呼叫都必須有對應的[!DNL Analytics]點擊，以共用A4T的補充ID才能正常運作。

包含[!DNL Analytics]和[!DNL Target]資料的點擊包含補充資料ID。 您可在[Adobe Experience Cloud除錯程式](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)中將此ID視為`sdid`參數。 例如: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`。只要符合下列條件即會產生此 ID:

* 已實作訪客 ID 服務
* 已實作支援此整合的 [!DNL mbox.js] 版本。

當[疑難排解](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)時，請確定[!DNL Analytics]點擊上有附加ID。

## 用戶端分析記錄 {#client-side}

如果at.js，則[!DNL Experience Cloud Visitor ID Service]和appMeasurement.js位於頁面上，而[!DNL Analytics]和[!DNL Target]只要頁面包含正確的附加ID，就能在後端正確地針對報告和分析目的連結事件。 您不需要管理並執行任何其他A4T作業，就能正常運作。

有時候，您可能想要對傳送與[!DNL Target]相關的分析資料至[!DNL Analytics]的時間和方式有更多控制，以利報告。 您可能有內部分析工具，可用於內部用途。 不過，您也想透過內部分析產品將分析資料傳送至[!DNL Analytics]，讓組織的其他成員可以繼續使用[!DNL Analytics]做為視覺化報表來源。 如需詳細資訊，請參閱 *Analytics for Target 實作*&#x200B;中的[步驟 7: 在所有網頁上參照 at.js 或 mbox.js](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)。

## 共用對象

在填寫[Marketing Cloud整合布建表單](https://www.adobe.com/go/audiences)時，請注意下列與「[!UICONTROL 您要求布建的功能]」下方所列的[!UICONTROL 共用觀眾]選項相關的重要資訊

![申請表](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

當您請求「共用對象」時，請啟用「[!UICONTROL Target]和[!UICONTROL Adobe Audience Manager](AAM)共用資訊」(在此例中為觀眾。][!UICONTROL 

>[!IMPORTANT]
>
>[!UICONTROL Target]之間的整合會帶AAM來額外成本。 每次[!UICONTROL Target]呼叫都需向您收費AAM。

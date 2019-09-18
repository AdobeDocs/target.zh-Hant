---
description: 啟用 Analytics 做為 Target (A4T) 的報表來源時，會在您的資料收集程序中發生數個變更。
keywords: Recommendations
seo-description: 啟用 Analytics 做為 Target (A4T) 的報表來源時，會在您的資料收集程序中發生數個變更。
seo-title: 實作之前Adobe Analytics 作為 Adobe Target (A4T) 的報表來源
solution: Target
title: 實作之前
topic: Premium
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# 實作之前{#before-you-implement}

啟用 Analytics 做為 Target (A4T) 的報表來源時，會在您的資料收集程序中發生數個變更。

決定用此整合之前，請檢閱下列各節，並考量對報表程序造成的影響:

## 實作需求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>開始使用 A4T 之前，您必須要求針對整合佈建您的帳戶。使用[此表單](https://www.adobe.com/go/audiences)來要求佈建帳戶。

視您是否要搭配 A4T 使用重新導向選件而定，此 A4T 整合需要您實作下列資料庫版本 (或更新版本):

### *不*&#x200B;搭配 A4T 使用重新導向選件之情況下的需求

如果您不打算搭配 A4T 使用重新導向選件，則此整合需要您實作下列程式庫版本 (或更新版本)。列出的順序是作業順序。

* Experience Cloud 訪客 ID 服務: visitorAPI.js 版本 1.8.0
* Adobe Target (根據您的實作): at.js 版本 0.9.1 或 mbox.js 版本 61
* Adobe Analytics: appMeasurement.js 版本 1.7.0

### 搭配 A4T 使用重新導向選件之情況下的需求

若要搭配 A4T 來使用重新導向選件，您必須實作下列程式庫版本 (或更新版本).列出的順序是作業順序。

* Experience Cloud 訪客 ID 服務: visitorAPI.js 版本 2.3.0
* Adobe Target: at.js 版本 1.6.2

   **注意:** mbox.js 資料庫不支援使用 A4T 重新導向選件。您的實作必須使用 at.js。

* Adobe Analytics: appMeasurement.js 版本 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## 實施前須知 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 選擇使用 Analytics 作為報表來源時，新的活動上會啟用此整合。當您如本文所述進行實作變更時，現有的活動不受影響。
* 將 Analytics 設定為 Target 的報表來源時，過程包括幾個實作步驟，隨後是一個佈建步驟。實作之前，最好閱讀一遍如下所述的程序。完成這些步驟後，只要 Analytics 一啟用，您立刻就可使用 Analytics 作為報表來源。佈建程序最多可能需要五個工作天。
* 訪客 ID 服務會為整個 Experience Cloud 建立一個共用訪客 ID。雖然不會取代 Target mboxPC id 或 Audience Manager UUID，訪客，但會取代 Analytics 識別新訪客的方式。如果設定正確，應該會透過舊的 Analytics ID 來識別再度訪問的 Analytics 訪客，以免訪客不知所措。同樣地，因為 Target mboxPCid 維持不變，當您升級至訪客 ID 服務時，不會遺失任何 Target 訪客設定檔資料。
* 訪客 ID 服務必須在 Analytics 和 Target 頁面程式碼之前執行。請確定 `VisitorAPI.js` 出現在其他所有 Experience Cloud 產品的標記上方。

## 延遲性 {#section_9489BE6FD21641A4844E591711E3F813}

此整合啟用之後，您在 Adobe Analytics 中會感受到額外 5-10 分鐘的延遲。增加此延遲可使 Analytics 和 Target 的資料透過相同的點擊儲存，讓您能夠依頁面和網站區段劃分測試。

此延遲增加的現象會反映在所有 Adobe Analytics 服務和工具中 (包括即時資料流與即時報表)，且適用於下列情況:

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 若是目前轉換量度的資料、已完成的資料及資料摘要，則所有點擊均會額外延遲 5 至 7 分鐘。

請注意，在您實作 Experience Cloud 訪客 ID 服務後，即使尚未完全實作此整合，也會開始增加延遲。

## 補充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4T 活動用來傳送內容或記錄目標量度的所有 Target 呼叫，必須有相應的 Analytics 點閱共用相同的補充 ID，A4T 才可正常運作。

如果點閱包含來自 Analytics 和 Target 的資料，即會包含補充資料 ID。You can see this ID in the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. 例如: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`。只要符合下列條件即會產生此 ID:

* 已實作訪客 ID 服務
* 已實作支援此整合的 [!DNL mbox.js] 版本。

進行疑難排解時，請確認 Analytics 點閱上有補充 ID。

## 用戶端分析記錄 {#client-side}

根據預設，當 at.js、[!DNL Experience Cloud Visitor ID Service] 和 appMeasurement.js 位於頁面上時，只要如上所述包含來自頁面的正確補充 ID，[!DNL Adobe Analytics] 和 [!DNL Target] 就會正確地拼接事件，以用於後端的報表和分析用途。您不需要管理及執行任何其他作業，A4T 即可正常運作。

不過，在某些情況下，您可能會想要進一步掌控將 [!DNL Target] 相關分析資料傳送至 [!DNL Analytics] 以用於報表用途的時間和方式。您可能有要運用於內部用途的內部分析工具，但也想要透過內部分析產品將分析資料傳送至 [!DNL Analytics]，讓組織的其他成員能夠繼續利用 [!DNL Analytics] 作為視覺報表來源。如需詳細資訊，請參閱 *Analytics for Target 實作*&#x200B;中的[步驟 7: 在所有網頁上參照 at.js 或 mbox.js](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)。

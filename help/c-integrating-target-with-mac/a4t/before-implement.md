---
keywords: Recommendations
description: 了解Analytics for [!DNL Target] (A4T)的實作需求，以及實作此整合前應考慮的事項。
title: 實作A4T之前應該知道什麼？
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 28%

---

# 使用at.js實作Analytics for Target(A4T)之前

啟用[!DNL Adobe Analytics]作為[!DNL Adobe Target](A4T)的報表來源時，您的資料收集程式會發生數項變更。

決定用此整合之前，請檢閱下列各節，並考量對報表程序造成的影響.

>[!NOTE]
>
>本文僅適用於at.js實作。

## 實作需求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>開始使用A4T之前，您必須要求已針對整合布建您的帳戶。 使用[Marketing Cloud整合布建表單](https://www.adobe.com/go/audiences_tw)請求布建。

視您是否要搭配 A4T 使用重新導向選件而定，此 A4T 整合需要您實作下列資料庫版本 (或更新版本):

### *不*&#x200B;搭配 A4T 使用重新導向選件之情況下的需求

如果您不打算搭配 A4T 使用重新導向選件，則此整合需要您實作下列程式庫版本 (或更新版本)。列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js版本1.8.0
* [!DNL Adobe Target]: at.js 0.9.1 版
* Adobe Analytics: appMeasurement.js 版本 1.7.0

### 搭配 A4T 使用重新導向選件之情況下的需求

若要搭配 A4T 來使用重新導向選件，您必須實作下列程式庫版本 (或更新版本).列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js版本2.3.0

   **注意：**  at.js 1.8.0或更新版本不再適用於2.5.0以前的訪客API版本，以傳 [!DNL Adobe Audience Manager] 遞(AAM)參數。

* [!DNL Adobe Target]: at.js 1.6.2 版

* Adobe Analytics: appMeasurement.js 版本 2.1

下載和部署指示列在[Analytics for Target實作](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)中。

## 實施前須知 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 當您選取使用[!DNL Analytics]作為報表來源時，此整合會在新活動上啟用。 當您如本文所述進行實作變更時，現有的活動不受影響。
* 將[!DNL Analytics]設定為[!DNL Target]的報表來源的程式包括數個實施步驟，隨後是布建步驟。 實作之前，最好閱讀一遍如下所述的程序。完成這些步驟後，您就可以在為您啟用[!DNL Analytics]時，使用作為報表來源。 佈建程序最多可能需要五個工作天。
* [!DNL Visitor ID service]會跨[!DNL Adobe Experience Cloud]建立共用[!DNL Visitor ID]。 雖然並未取代[!DNL Target] mboxPC id或[!DNL Audience Manager] UUID，但會取代[!DNL Analytics]識別新訪客的方式。 如果設定正確，還應透過其舊的[!DNL Analytics] ID來識別回訪的[!DNL Analytics]訪客。 同樣地，由於[!DNL Target] mboxPCid保持不變，因此升級至[!DNL Visitor ID service]時不會遺失[!DNL Target]訪客設定檔資料。
* [!DNL Visitor ID service]必須在[!DNL Analytics]和[!DNL Target]頁面代碼之前執行。 請確定`VisitorAPI.js`出現在所有其他[!DNL Experience Cloud]解決方案的標籤上方。

## 延遲性 {#section_9489BE6FD21641A4844E591711E3F813}

啟用此整合後，您會在[!DNL Analytics]中遇到5至10分鐘的額外延遲。 增加此延遲可讓[!DNL Analytics]和[!DNL Target]的資料儲存在相同的點擊上，讓您能夠依頁面和網站區段劃分活動。

此增加反映在所有[!DNL Analytics]服務和工具中，包括即時資料流和即時報告，並適用於下列情況：

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 針對轉換量度、已完成資料和資料摘要的目前資料，所有點擊都會延遲5至7分鐘。

即使您尚未完全實作此整合，延遲增加現象也會在您實作[!DNL Experience Cloud]訪客ID服務後開始。

## 補充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4T活動用來傳送內容或記錄目標量度的所有[!DNL Target]呼叫必須有相對應的[!DNL Analytics]點擊，且該點擊共用A4T的補充ID，才能正常運作。

包含[!DNL Analytics]和[!DNL Target]資料的點擊會包含補充資料ID。 您可以在[Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)中看到此ID為`sdid`參數。 例如: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`。只要符合下列條件即會產生此 ID:

* 已實作訪客 ID 服務

當[疑難排解](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)時，請務必確認[!DNL Analytics]點擊上有補充ID。

## 用戶端分析記錄 {#client-side}

如果at.js、[!DNL Experience Cloud Visitor ID Service]和appMeasurement.js位於頁面上，只要頁面中包含正確的補充ID,[!DNL Analytics]和[!DNL Target]即可正確拼接事件，以用於後端的報表和分析用途。 您不需要管理並執行任何其他操作，A4T才能正常運作。

在某些情況下，您可能會想要進一步掌控將[!DNL Target]相關分析資料傳送至[!DNL Analytics]以用於報表用途的時間和方式。 您可能有內部分析工具，可用於內部用途。 不過，您也想透過內部分析產品將分析資料傳送至[!DNL Analytics]，讓組織的其他成員能繼續使用[!DNL Analytics]作為視覺報表來源。 請參閱[步驟7:如需詳細資訊，請參考&#x200B;*Analytics for Target實作*&#x200B;中所有網頁上的at.js ](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)。

## 共用對象

填入[Marketing Cloud整合布建表單](https://www.adobe.com/go/audiences)時，請注意下列「[!UICONTROL 您要求布建的功能]？」下方所列的[!UICONTROL 共用對象]選項的重要資訊

![申請表](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

請求[!UICONTROL 共用對象]時，您會啟用[!UICONTROL Target]和[!UICONTROL Adobe Audience Manager](AAM)以共用資訊，在此例中是對象。

>[!IMPORTANT]
>
>[!UICONTROL Target]與AAM之間的整合會產生額外成本。 AAM中每次[!UICONTROL Target]呼叫都需為您付費。

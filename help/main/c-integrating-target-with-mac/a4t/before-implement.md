---
keywords: 推薦
description: 瞭解Analytics for [!DNL Target] (A4T)的實作需求，以及在實作此整合之前需要考量的事項。
title: 實作A4T之前，我應該瞭解什麼？
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 656f728ba890f1f5afc0404e22f6acb1a2565fe6
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 24%

---

# 使用at.js實作Analytics for Target (A4T)之前

啟用[!DNL Adobe Analytics]做為[!DNL Adobe Target] (A4T)的報告來源時，您的資料收集程式會發生一些變更。

在決定使用此整合之前，請檢閱下列各節並考慮對報表程式的影響。

>[!NOTE]
>
>本文僅適用於at.js實作。 如需有關使用[!UICONTROL Analytics for Target]實作[!DNL Adobe Experience Platform Web SDK] (A4T)的資訊，請參閱Experience Platform Web SDK[中的](https://experienceleague.adobe.com/docs/target-dev/developer/a4t/overview-a4t.html){target=_blank}Adobe Analytics for Target (A4T)登入。

## 實作需求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>開始使用A4T之前，您必須要求您的帳戶已針對整合進行布建。 使用[Marketing Cloud整合布建表單](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}來要求布建帳戶。

視您是否要搭配A4T使用重新導向選件而定，此A4T整合需要您實作下列程式庫版本（或更新版本）。

>[!NOTE]
>
>下列需求列出實作A4T所需的&#x200B;*最少*&#x200B;個at.js版本。 [!DNL Target]團隊只會維護兩個版本的[!DNL at.js]：最新版本和次新版本。 請視需要升級 [!DNL at.js]，以確保您執行的是支援的版本。如需每一個版本有何功能的詳細資訊，請參閱 [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}。

### *不*&#x200B;搭配 A4T 使用重新導向產品建議之情況下的需求

如果您不打算搭配 A4T 使用重新導向產品建議，則此整合需要您實作下列程式庫版本 (或更新版本)。列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]： visitorAPI.js版本1.8.0
* [!DNL Adobe Target]： at.js 0.9.1版
* Adobe Analytics: appMeasurement.js 版本 1.7.0

如需使用[!DNL Platform Web SDK]實作A4T的相關資訊，請參閱[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}。

### 搭配 A4T 使用重新導向產品建議之情況下的需求

若要搭配 A4T 來使用重新導向產品建議，您必須實作下列程式庫版本 (或更新版本).列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]： visitorAPI.js版本2.3.0

  >[!NOTE]
  >
  >at.js 1.8.0+ 和 at.js 2.x+ 不再搭配使用 2.5.0 之前的訪客 API 版本以傳遞 Adobe Audience Manager (AAM) 參數。

* [!DNL Adobe Target]： at.js版本1.6.2

* Adobe Analytics: appMeasurement.js 版本 2.1

[Analytics for Target實作](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)中列出下載和部署指示。

如需使用[!DNL Platform Web SDK]實作A4T的相關資訊，請參閱[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}。

## 實施前須知 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 當您選取使用[!DNL Analytics]作為報表來源時，會在新活動上啟用這項整合。 當您如本文所述進行實作變更時，現有的活動不受影響。
* 將[!DNL Analytics]設定為[!DNL Target]的報告來源的程式包含數個實作步驟，然後是布建步驟。 實作之前，最好閱讀一遍如下所述的程序。完成這些步驟後，您就可以使用[!DNL Analytics]作為您的報表來源（當您啟用它時）。 佈建程序最多可能需要五個工作天。
* [!DNL Visitor ID service]會建立跨[!DNL Visitor ID]的共用[!DNL Adobe Experience Cloud]。 雖然它不會取代[!DNL Target] mboxPC ID或[!DNL Audience Manager] UUID，但會取代[!DNL Analytics]識別新訪客的方式。 若設定正確，應該也透過舊[!DNL Analytics] ID識別回訪的[!DNL Analytics]訪客。 同樣地，由於[!DNL Target] mboxPCid會維持不變，當您升級至[!DNL Target]時，不會遺失[!DNL Visitor ID service]個訪客設定檔資料。
* [!DNL Visitor ID service]必須在您的[!DNL Analytics]和[!DNL Target]頁面代碼之前執行。 請確定`VisitorAPI.js`出現在所有其他[!DNL Experience Cloud]解決方案的標籤上方。

## 延遲性 {#section_9489BE6FD21641A4844E591711E3F813}

啟用這項整合後，[!DNL Analytics]中會出現5至10分鐘的額外延遲。 增加此延遲可讓來自[!DNL Analytics]和[!DNL Target]的資料儲存在相同的點選上，讓您能夠依頁面和網站區段劃分活動。

此增加會反映在所有[!DNL Analytics]服務和工具中（包括即時資料流和即時報表），並適用於下列情況：

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 對於轉換量度、最終完成的資料和資料摘要的目前資料，所有點選都會額外延遲5至7分鐘。

即使您尚未完全實作該整合，該延遲增加現象也會在您實作[!DNL Experience Cloud]訪客ID服務後開始。

## 補充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4T活動用來傳遞內容或記錄目標量度的所有[!DNL Target]呼叫都必須有對應的[!DNL Analytics]點選，這些點選共用A4T的補充ID才能正常運作。

包含來自[!DNL Analytics]與[!DNL Target]之資料的點選包含補充資料ID。 您可以在[Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)中看到此ID為`sdid`引數。 例如: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`。只要符合下列條件即會產生此 ID:

* 已實作訪客 ID 服務

[疑難排解](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)時，請確定在[!DNL Analytics]點選上有補充ID。

## 使用者端分析記錄 {#client-side}

如果at.js、[!DNL Experience Cloud Visitor ID Service]和appMeasurement.js位於頁面上，只要頁面中包含正確的補充ID，[!DNL Analytics]和[!DNL Target]就會正確地拼接事件，以用於後端的報表和分析用途。 您不需要管理和執行任何其他作業，A4T就能正常運作。

在某些情況下，您可能會想要進一步掌控將[!DNL Target]相關分析資料傳送至[!DNL Analytics]以用於報表用途的時間和方式。 您可能有用於內部用途的內部分析工具。 不過，您也想要透過內部分析產品將分析資料傳送至[!DNL Analytics]，讓組織的其他成員可以繼續使用[!DNL Analytics]作為視覺報表來源。 如需詳細資訊，請參閱[Analytics for Target實作](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)中的&#x200B;*步驟7：在所有網站頁面*&#x200B;上參考at.js 。

## 共用對象

填寫[Marketing Cloud整合布建表單](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}時，請注意下列有關「[!UICONTROL Shared Audiences]」底下所列[!UICONTROL For which capabilities are you requesting provisioning]選項的重要資訊？

![要求表單](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

當您請求[!UICONTROL Shared Audiences]時，您啟用[!UICONTROL Target]和[!UICONTROL Adobe Audience Manager] (AAM)以共用資訊，在此案例中是對象。

>[!IMPORTANT]
>
>[!UICONTROL Target]與AAM之間的這項整合需要額外付費。 在AAM中，您需為每個[!UICONTROL Target]呼叫付費。

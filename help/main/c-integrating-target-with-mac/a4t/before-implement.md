---
keywords: Recommendations
description: 了解Analytics的實作需求，適用於 [!DNL Target] (A4T)以及實作此整合前應考量的事項。
title: 實作A4T之前應該知道什麼？
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 231cf7972b7343e02245d12ea9380df8d4b125da
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 26%

---

# 使用 at.js 實作 Analytics for Target (A4T) 之前

啟用 [!DNL Adobe Analytics] 作為的報表來源 [!DNL Adobe Target] (A4T)。

決定用此整合之前，請檢閱下列各節，並考量對報表程序造成的影響.

>[!NOTE]
>
>本文僅適用於at.js實作。

## 實作需求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>開始使用A4T之前，您必須要求已針對整合布建您的帳戶。 使用 [Marketing Cloud整合布建表單](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}請求布建。

視您是否要搭配A4T使用重新導向選件而定，此A4T整合需要您實作下列程式庫版本（或更新版本）。

>[!NOTE]
>
>下列需求列出 *最小* 實作A4T所需的at.js版本。 此 [!DNL Target] team只維護兩個版本 [!DNL at.js] — 當前版本和次新版本。 請視需要升級 [!DNL at.js]，以確保您執行的是支援的版本。如需每個版本包含內容的詳細資訊，請參閱 [at.js版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}。

### *不*&#x200B;搭配 A4T 使用重新導向選件之情況下的需求

如果您不打算搭配 A4T 使用重新導向選件，則此整合需要您實作下列程式庫版本 (或更新版本)。列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js版本1.8.0
* [!DNL Adobe Target]: at.js 0.9.1 版
* Adobe Analytics: appMeasurement.js 版本 1.7.0

如需使用實作A4T的相關資訊， [!DNL Platform Web SDK]，請參閱 [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}。

### 搭配 A4T 使用重新導向選件之情況下的需求

若要搭配 A4T 來使用重新導向選件，您必須實作下列程式庫版本 (或更新版本).列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js版本2.3.0

   >[!NOTE]
   >
   >at.js 1.8.0+ 和 at.js 2.x+ 不再搭配使用 2.5.0 之前的訪客 API 版本以傳遞 Adobe Audience Manager (AAM) 參數。

* [!DNL Adobe Target]: at.js 1.6.2 版

* Adobe Analytics: appMeasurement.js 版本 2.1

下載和部署指示列於 [Analytics for Target實作](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

如需使用實作A4T的相關資訊， [!DNL Platform Web SDK]，請參閱 [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}。

## 實施前須知 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 當您選取使用 [!DNL Analytics] 作為報表來源時。 當您如本文所述進行實作變更時，現有的活動不受影響。
* 設定程式 [!DNL Analytics] 作為的報表來源 [!DNL Target] 包括數個實施步驟，隨後是布建步驟。 實作之前，最好閱讀一遍如下所述的程序。完成這些步驟後，即可使用 [!DNL Analytics] 作為您的報表來源。 佈建程序最多可能需要五個工作天。
* 此 [!DNL Visitor ID service] 建立共用 [!DNL Visitor ID] 跨 [!DNL Adobe Experience Cloud]. 雖然不會取代 [!DNL Target] mboxPC id或 [!DNL Audience Manager] UUID，會取代 [!DNL Analytics] 識別新訪客。 如果設定正確，請傳回 [!DNL Analytics] 訪客也應透過其舊 [!DNL Analytics] ID. 同樣地，因為 [!DNL Target] mboxPCid保持不變，沒有 [!DNL Target] 升級為時，訪客設定檔資料會遺失 [!DNL Visitor ID service].
* 此 [!DNL Visitor ID service] 必須在 [!DNL Analytics] 和 [!DNL Target] 頁面程式碼。 確保 `VisitorAPI.js` 出現在其他所有標籤的上方 [!DNL Experience Cloud] 解決方案。

## 延遲性 {#section_9489BE6FD21641A4844E591711E3F813}

啟用這項整合後，您會在 [!DNL Analytics]. 增加此延遲可讓 [!DNL Analytics] 和 [!DNL Target] 儲存在相同點擊上，可讓您依頁面和網站區段劃分活動。

這種增加反映在所有 [!DNL Analytics] 服務及工具（包括即時資料流和即時報表），並適用於下列情況：

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 針對轉換量度、已完成資料和資料摘要的目前資料，所有點擊都會延遲5至7分鐘。

延遲增加會在您實作 [!DNL Experience Cloud] 訪客ID服務，即使您尚未完全實作此整合亦然。

## 補充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

全部 [!DNL Target] A4T活動用來傳送內容或記錄目標量度的呼叫必須具有對應的 [!DNL Analytics] 點擊會共用A4T的補充ID以正常運作。

包含資料的點擊 [!DNL Analytics] 和 [!DNL Target] 包含補充資料ID。 您可以在 [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) 作為 `sdid` 參數。 例如: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`。只要符合下列條件即會產生此 ID:

* 已實作訪客 ID 服務

當 [疑難排解](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)，請務必確認上有補充ID [!DNL Analytics] 點擊。

## 用戶端分析記錄 {#client-side}

若at.js，則 [!DNL Experience Cloud Visitor ID Service]，和appMeasurement.js位於頁面上， [!DNL Analytics]，和 [!DNL Target] 只要頁面中包含正確的補充ID，就能正確拼接事件，以用於後端的報表和分析用途。 您不需要管理並執行任何其他操作，A4T才能正常運作。

在某些情況下，您可能會想要進一步掌控傳送相關分析資料的時間和方式 [!DNL Target] to [!DNL Analytics] 供報告之用。 您可能有內部分析工具，可用於內部用途。 不過，您也想要將分析資料傳送至 [!DNL Analytics] 透過內部分析產品，讓組織的其他成員可繼續使用 [!DNL Analytics] 作為視覺化報表來源。 請參閱 [步驟7:在所有網頁上參考at.js](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) in *Analytics for Target實作* 以取得更多資訊。

## 共用對象

填入 [Marketing Cloud整合布建表單](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}，請注意下列與 [!UICONTROL 共用對象] 「」中列出的選項[!UICONTROL 您要求布建的功能]?&quot;

![申請表](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

請求時 [!UICONTROL 共用對象]，請啟用 [!UICONTROL 目標] 和 [!UICONTROL Adobe Audience Manager] (AAM)來共用資訊，在此例中為對象。

>[!IMPORTANT]
>
>此整合 [!UICONTROL 目標] AAM會額外付費。 每個 [!UICONTROL 目標] 在AAM中呼叫。

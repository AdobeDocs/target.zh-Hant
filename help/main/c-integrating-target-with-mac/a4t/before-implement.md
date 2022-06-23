---
keywords: Recommendations
description: 瞭解Analytics的實施要求 [!DNL Target] (A4T)以及實施此整合之前要考慮的內容。
title: 在實施A4T之前，我應瞭解什麼？
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 27%

---

# 使用 at.js 實作 Analytics for Target (A4T) 之前

啟用時，資料收集過程中會發生一些更改 [!DNL Adobe Analytics] 作為 [!DNL Adobe Target] (A4T)。

決定用此整合之前，請檢閱下列各節，並考量對報表程序造成的影響.

>[!NOTE]
>
>本文僅適用於at.js實現。

## 實作需求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>在開始使用A4T之前，必須請求為整合設定您的帳戶。 使用 [Marketing Cloud整合預配表](https://www.adobe.com/go/audiences_tw) 請求設定。

此A4T整合要求您實施以下庫版本（或更新版本），具體取決於您是否要對A4T使用重定向服務。

>[!NOTE]
>
>以下要求列出 *最小* 實現A4T所需的at.js版本。 的 [!DNL Target] 團隊只維護兩個版本 [!DNL at.js] — 當前版本和第二個最新版本。 請視需要升級 [!DNL at.js]，以確保您執行的是支援的版本。如需每一個版本有何功能的詳細資訊，請參閱 [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)。

### *不*&#x200B;搭配 A4T 使用重新導向選件之情況下的需求

如果您不打算搭配 A4T 使用重新導向選件，則此整合需要您實作下列程式庫版本 (或更新版本)。列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js 1.8.0版
* [!DNL Adobe Target]: at.js 0.9.1 版
* Adobe Analytics: appMeasurement.js 版本 1.7.0

有關使用 [!DNL Platform Web SDK]，請參閱 [Adobe Experience PlatformWeb SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/)。

### 搭配 A4T 使用重新導向選件之情況下的需求

若要搭配 A4T 來使用重新導向選件，您必須實作下列程式庫版本 (或更新版本).列出的順序是作業順序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js 2.3.0版

   >[!NOTE]
   >
   >at.js 1.8.0+ 和 at.js 2.x+ 不再搭配使用 2.5.0 之前的訪客 API 版本以傳遞 Adobe Audience Manager (AAM) 參數。

* [!DNL Adobe Target]: at.js 1.6.2 版

* Adobe Analytics: appMeasurement.js 版本 2.1

下載和部署說明列於 [目標實施分析](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)。

有關使用 [!DNL Platform Web SDK]，請參閱 [Adobe Experience PlatformWeb SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/)。

## 實施前須知 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 當您選擇使用時，新活動將啟用此整合 [!DNL Analytics] 作為報告源。 當您如本文所述進行實作變更時，現有的活動不受影響。
* 設定過程 [!DNL Analytics] 作為 [!DNL Target] 包括幾個實施步驟，然後是設定步驟。 實作之前，最好閱讀一遍如下所述的程序。完成這些步驟後，即可使用 [!DNL Analytics] 作為報告源。 佈建程序最多可能需要五個工作天。
* 的 [!DNL Visitor ID service] 建立共用 [!DNL Visitor ID] 對面 [!DNL Adobe Experience Cloud]。 雖然它不會替代 [!DNL Target] mboxPC id或 [!DNL Audience Manager] UUID，它確實替代了 [!DNL Analytics] 標識新訪問者。 如果設定正確，則返回 [!DNL Analytics] 遊客也應通過他們的老家來辨認 [!DNL Analytics] ID。 同樣，因為 [!DNL Target] mboxPCid保持不變，無 [!DNL Target] 升級到訪問者配置檔案時，訪問者配置檔案資料丟失 [!DNL Visitor ID service]。
* 的 [!DNL Visitor ID service] 必須在 [!DNL Analytics] 和 [!DNL Target] 頁碼。 確保 `VisitorAPI.js` 顯示在所有其他標籤的上方 [!DNL Experience Cloud] 解決方案。

## 延遲性 {#section_9489BE6FD21641A4844E591711E3F813}

啟用此整合後，您將在以下時間內體驗5-10分鐘的延遲 [!DNL Analytics]。 延遲增加允許資料 [!DNL Analytics] 和 [!DNL Target] 儲存到同一擊中，允許您按頁面和站點區分活動。

這一增長反映在 [!DNL Analytics] 服務和工具，包括即時流和即時報告，並適用於以下情形：

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 對於有關轉換度量、最終資料和資料饋送的當前資料，所有命中都會延遲5-7分鐘。

在實施 [!DNL Experience Cloud] 訪問者身份證服務，即使您尚未完全實現此整合。

## 補充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

全部 [!DNL Target] A4T活動用於傳遞內容或記錄目標度量的調用必須具有相應的 [!DNL Analytics] 點擊該按鈕，共用A4T的補充ID。

包含資料的命中 [!DNL Analytics] 和 [!DNL Target] 包含補充資料ID。 您可以在 [Adobe Experience Cloud調試器](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) 的 `sdid` 的下界。 例如: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`。只要符合下列條件即會產生此 ID:

* 已實作訪客 ID 服務

當 [故障排除](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)，確保確認上存在補充ID [!DNL Analytics] 擊中。

## 用戶端分析記錄 {#client-side}

如果at.js, [!DNL Experience Cloud Visitor ID Service]，和appMeasurement.js在頁面上， [!DNL Analytics], [!DNL Target] 只要頁面中包含正確的補充ID，就可以在後端正確地為報告和分析目的縫合事件。 您不需要管理並執行任何附加操作，A4T才能正常運行。

在某些情況下，您可能希望對何時以及如何發送與相關的分析資料擁有更多控制權 [!DNL Target] 至 [!DNL Analytics] 報告用途。 您可能擁有內部分析工具，用於內部目的。 但是，您還希望將分析資料發送到 [!DNL Analytics] 通過內部分析產品，以便組織中的其他成員可以繼續使用 [!DNL Analytics] 作為可視報告源。 請參閱 [第7步：所有網站頁上的at.js引用](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) 在 *目標實施分析* 的子菜單。

## 共用對象

填充 [Marketing Cloud整合預配表](https://www.adobe.com/go/audiences)，請注意以下與 [!UICONTROL 共用受眾] 選項列在「[!UICONTROL 您要為其請求置備的功能]?&quot;

![請求表](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

請求時 [!UICONTROL 共用受眾]，則啟用 [!UICONTROL 目標] 和 [!UICONTROL Adobe Audience Manager] (AAMa)分享資訊，在這種情況下是受眾。

>[!IMPORTANT]
>
>此整合 [!UICONTROL 目標] 還AAM有額外費用。 您將按每個 [!UICONTROL 目標] 打來AAM。

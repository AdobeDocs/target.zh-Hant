---
keywords: 版本注意事項;發行;更新;未來發行;增強;新功能;修正;更新;版本注意事項
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8cdf362d9e45153b26bca5a45ed59ef557adc016
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Target 版本注意事項 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期；2023 年 3 月 14 日**

若要檢視目前版本的相關資訊，請參閱 [Target 版本注意事項](release-notes.md)。這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 22.15.1 (2023 年 3 月 8 日和 9 日)

我們將根據以下排程分批發行此版本：

* **3 月 8 日**：美洲區域
* **3 月 9 日**：歐洲、中東和非洲 (EMEA) 區域
* **3 月 9 日**：亞太 (APAC) 區域

此版本包含以下新功能、增強功能和修正：

| 功能 | 詳細資料 |
| --- | --- |
| 為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]最佳化的 A4T 量度 | [!DNL Target]可讓您在為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動使用 [!UICONTROL A4T] 時，選擇以二項式事件為基礎的量度，或是以持續事件為基礎的量度。<P>請注意受支援量度的以下變更：<ul><li>[!DNL Target] 已保留現有活動的先前行為，直到 (日期待定)。在此日期之後，將停止使用非支援之量度的活動，以強制現有活動遷移至新行為。</li></ul>如需詳細資訊，請參閱&#x200B;*自動分配和自動鎖定目標活動之 A4T 支援*&#x200B;的[受支援目標量度](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported)。 |
| 使用 [!UICONTROL Analytics for Target] (A4T) 的[!UICONTROL 自動分配] | 新教學課程：<ul><li>[在  [!DNL Analysis Workspace]  中設定[!UICONTROL 自動分配]活動的 A4T 報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| 使用 [!UICONTROL Analytics for Target] (A4T) 的[!UICONTROL 自動鎖定目標] | 新教學課程：<ul><li>[在  [!DNL Analysis Workspace]  中設定[!UICONTROL 自動鎖定目標]活動的 A4T 報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

此版本包含下列修正：

* 更新自訂Web元件的編寫，使用 [!UICONTROL 可視化體驗撰寫器] (VEC):

   * 透過改善編寫程式，修正VEC中陰影DOM元素的選取，因此不會依賴 [!DNL Target] 製作陰影根時的實作類型。 現在，在VEC中選取「影子DOM」元素，即可供任何網站使用。
   * 修正無法在VEC中使用#Shadow DOM載入HTML元素的問題。 (TGT-35801)
   * 修正SPA網站使用ShadowDOM的VEC問題。 (TGT-43169)
   * 修正最佳化目標的問題：「已點按元素」未正確識別ShadowDOM中的CSS選取器。

>[!NOTE]
>
>若要確保傳送在VEC中撰寫的變更，請確定您使用 [!DNL Target] SDK([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js))，其版本大於2.8。

**已知問題**:使用 [!DNL Adobe Experience Platform Web SDK] 無法正常運作。 (TNT-47012)

## at.js 版本 2.10.2 (2023 年 3 月 7 日)

* 修正造成 `trackEvent` 函數總是傳回錯誤的問題。

有關所有 at.js 版本的資訊，請參閱 [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}。

## 額外的版本注意事項和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [版本注意事項：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |


## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 207095a1db483abcc59f7806a67e559ee8694397
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 69%

---

# [!DNL Target] 發行說明 (最新)

這些版本注意事項提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的版本注意事項以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target] Standard/Premium 22.15.1 (2023 年 3 月 8 日和 9 日)

我們將根據以下排程分批發行此版本：

* **3 月 8 日**：美洲區域
* **3 月 9 日**：歐洲、中東和非洲 (EMEA) 區域
* **3 月 9 日**：亞太 (APAC) 區域

>[!NOTE]
>
>由於此後已修正的問題，「針對 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標]「 3月8日和9日發行的功能已暫時移除。 進一步的內部測試後，此功能將在未來幾週內再次發行。

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

## 文件變更、過去的版本注意事項和 Experience Cloud 版本注意事項

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些版本注意事項中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 舊版版本注意事項 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本注意事項](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 版本注意事項 | 檢視 Adobe Experience Cloud 解決方案的最新版本注意事項。<br>如需詳細資訊，請參閱 [Experience Cloud 版本注意事項](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html) |
| 即將發佈的版本注意事項 | 如需本月的 Target 版本的詳細資訊，包括搶鮮版版本資訊，請參閱 [Target 版本注意事項 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md)頁面。 |

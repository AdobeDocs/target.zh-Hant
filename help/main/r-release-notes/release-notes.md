---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 68%

---

# [!DNL Target] 發行說明 (最新)

這些版本注意事項提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的版本注意事項以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target] Standard/Premium 22.15.1（2023年3月8日和9日）

我們將根據以下排程分批發行此版本：

* **3月8日**:美洲地區
* **3月9日**:歐洲、中東和非洲(EMEA)地區
* **3月9日**:亞太地區

此版本包含下列新功能和增強功能：

| 功能 | 詳細資料 |
| --- | --- |
| 針對 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] | [!DNL Target] 可讓您在使用 [!UICONTROL A4T] for [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動。<P>請注意支援的量度中有下列時效性變更：<ul><li>[!DNL Target] 將現有活動的先前行為保留至2023年9月9日。 在此日期後，將停止使用不支援量度的活動，以強制現有活動移轉至新行為。</li></ul>如需詳細資訊，請參閱 [支援的目標量度](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) in *自動分配和自動鎖定目標活動的A4T支援*. |
| [!UICONTROL 自動分配] 使用 [!UICONTROL Analytics for Target] (A4T) | 新教學課程：<ul><li>[在中設定A4T報表 [!DNL Analysis Workspace] for [!UICONTROL 自動分配] 活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| [!UICONTROL 自動鎖定目標] 使用 [!UICONTROL Analytics for Target] (A4T) | 新教學課程：<ul><li>[在中設定A4T報表 [!DNL Analysis Workspace] for [!UICONTROL 自動鎖定目標] 活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

## at.js 版本 2.10.2 (2023 年 3 月 7 日)

* 修正 `trackEvent` 函式，一律傳回錯誤。

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

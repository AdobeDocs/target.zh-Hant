---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2e6efe777925eb14e280ea38110dc1cb12264d17
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 82%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target] Standard/Premium 23.5.2 (2023 年 5 月 31 日)

此版本包含下列增強功能和修正：

* 已修復在生成設定檔 API 授權權杖時造成顯示空白頁面的問題。(TGT-45387 和 TGT-45423)
* 已修復在影像名稱包含 GB 18030 字元時，[!UICONTROL 建立設計]面板無法顯示影像的問題。(TGT-44614)
* 修正體驗中的文字/HTML中，部分GB 18030符號字元錯誤逸出的問題。 (TGT-44600)
* 已修復在分析過程中導致報告在 [!UICONTROL Auto Personalization] 活動中凍結的問題。(TGT-44820)
* 修正無法搜尋活動的問題 [!UICONTROL 活動] 頁面(如果活動名稱包含方括弧( [ 或 ] )。 (TGT-44777)
* 修正當活動的目標包含特殊字元時，無法同步活動的問題。 (TGT-44982)
* 已修正導致無活動顯示於 [!DNL Target] 特定客戶預設工作區的UI。 (TGT-45286)
* 已更新「不允許重複」標幟的行為。 已更新排除的重複優惠方案標幟，以允許預設內容優惠方案的重複優惠方案 (適用於 API v3、v4)，並且如果選項參考預設內容優惠方案且未定義範本，則允許重複選項。 (TNT-46617)
* 修正在URL中新增查詢引數，導致頁面無法在中載入的問題。 [!UICONTROL 視覺化體驗撰寫器] (VEC)。 (TGT-44873)
* 對整個 [!DNL Target] UI 進行了各種本地化修正。

## [!DNL Target] Standard/Premium 23.5.1 (2023 年 5 月 23-25 日)

我們將根據以下排程分批發行此版本：

5 月 23 日：歐洲、中東和非洲 (EMEA) 地區
5 月 24 日：亞太 (APAC) 地區
5 月 25 日：美洲地區

此版本包含下列新增強功能和修正：

* 已修復讓特定客戶無法使用「大於」或「小於」運算符號，建立具有訪客資料的對象問題。(TGT-45271)
* 對整個 [!DNL Target] UI 進行了各種本地化修正。
* 為即將到來的 UI 重新整理更新了不同位置的 Target UI (在發行更新之前，變更隱藏在功能標幟之後)。

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |

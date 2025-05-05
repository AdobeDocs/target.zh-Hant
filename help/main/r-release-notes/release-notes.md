---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新、目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 0f96fb2a74a0716542308037d183847c91b1dc04
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 52%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 25.5.1 （2025年5月5日）

此版本包含下列修正和更新：

* 已修正無法在更新的UI中顯示特定活動的對象細分的問題。 (TGT-52057)
* 修正無法在活動中使用合併受眾的問題。 (TGT-52346)
* 修正了無法使用相同工作區中僅限活動的對象，在非預設工作區中建立新活動的問題。 (TGE-52349)
* 修正造成在建立及選取新對象後，僅限於此活動的對象從更新的UI中消失的問題。 (TGT=52091)
* 修正無法在活動中使用重複受眾的問題。 (TGT-51200 和 TGT-52057)
* 已修正導致在更新的UI中回覆對象細分和活動對象的問題。 (TGT-52158)
* 修正由於使用者輸入錯誤「此使用者不允許非預設工作區」而無法建立新活動的問題。 (TGT-52267)
* 已修正導致無法在預設和非預設工作區的更新UI中顯示選件的問題。 [!DNL Target]現在會顯示來自兩個工作區的選件。 (TGT-52339)
* 修正[!DNL Target]在編輯活動和變更已修改的網站元素時未警告客戶的問題。 (TGT-52100)
* 修正編輯具有臨時優惠方案的優惠方案時，會建立新優惠方案而非更新現有優惠方案的問題。 (TGT-52135)
* 修正將優惠方案移至資料夾時，造成無效裝載錯誤的問題。 (TGT-52325)
* 修正將優惠方案移至資料夾時造成使用者輸入錯誤的問題。 (TGT-52296)
* 為每個活動新增`audienceMetadata`欄位，並確保在編輯活動時已讀取和更新它。 (TGT-51004)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |

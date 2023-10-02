---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 159cf7595878e0412f249a52dc979e0824c717eb
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 81%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target] Standard/Premium 23.9.4 （日期待定）

此版本包含下列增強功能和修正：

| 功能 | 詳細資料 |
| --- | --- |
| [!UICONTROL 活動] UI重新整理<P>和<P>[!UICONTROL 動態消息] UI重新整理 | 作為 [!DNL Adobe Target] 團隊持續努力改善的使用者體驗， [!DNL Target] 使用者，此版本會重新整理 [!UICONTROL 活動] 和 [!DNL Recommendations] [!UICONTROL 動態消息] 中的頁面 [!DNL Target] UI。 此更新統一並標準化先前不一致的設計模式，同時加入新的增強功能。<P>如需詳細資訊，請參閱 [活動](/help/main/c-activities/activities.md) 和 [動態消息](/help/main/c-recommendations/c-products/feeds.md). |
| [!DNL Recommendations] 實作模式 | 此 *使用at.js的Recommendations實作模式* 文章可協助您瞭解並建立您的 [!DNL Adobe Target Recommendations] 使用at.js JavaScript資料庫時的實作。<P>如需詳細資訊，請參閱 [使用at.js的Recommendations實作模式概覽](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank} 在 *Adobe Target開發人員指南*. |

* 已新增 [!UICONTROL 視覺化體驗撰寫器] (VEC)動態架構的增強功能。 (TGT-44064)
* 已修正導致在 `getViewInAnalyticsId` 請求不要正確更新。 此修正可協助重新計算 [!DNL Analytics] 日期範圍和量度報表設定變更時報表中的連結。 (TGT-46246)

## [!DNL Target] Standard/Premium 23.9.3 (2023 年 9 月 18 日)

此版本包含下列增強功能和修正：

* 強化 [!UICONTROL 可視化體驗撰寫器] (VEC) 以支援 Lightning Web (Light DOM)。(TGT-45422)
* 已修復使 VEC 操作以錯誤順序應用的問題。在某些情況下，VEC 會不同步應用部份修改並將額外修改加入引起錯誤的元素 (如果該元素在[!UICONTROL 插入]行動之後顯示)。也修復了 VEC URL，現在按一下錨點連結時就會更新。(TGT-45983)
* 已修復 VEC [!UICONTROL 覆蓋]功能的問題，該功能現在支援 Shadow DOM 中的元素。(TGT-45202 和 TGT-45262)
* 已修復在 VEC 中開啟單次頁面應用程式 (SPA) 頁面後進入[!UICONTROL 瀏覽]模式時，後退和前進箭頭無法正常運作的問題。(TGT-45956)
* 已修復導致某些網頁無法在 VEC 中載入的問題。(TGT-45983)

## [!DNL Target] Standard/Premium 23.9.2 (2023 年 9 月 12-14 日)

我們將根據以下排程分批發行此版本：

* **9 月 12 日**：美洲區域
* **9 月 13 日**：亞太 (APAC) 區域
* **9 月 14 日**：歐洲、中東和非洲 (EMEA) 區域

此版本包含下列增強功能和修正：

* 已將 [!DNL Analytics]API 改成新的[!DNL Analytics] API 2.0 版。(TGT-45345)
* 已修正影響某些客戶的 [!UICONTROL Automated Personalization] (AP) 活動的問題，包括及時同步 [!DNL Target] 後端上的活動以及在預覽連結中提供預期的體驗。(TGT-46202)

## [!DNL Target] Standard/Premium 23.9.1 (2023 年 9 月 6-11 日)

我們將根據以下排程分批發行此版本：

* **9 月 6 日**：美洲區域
* **9 月 7 日**：歐洲、中東和非洲 (EMEA) 區域
* **9 月 11 日**：亞太 (APAC) 區域

此版本包含下列增強功能和修正：

* 已修復造成 [!DNL Target]UI 和 [!DNL Adobe Analytics] UI (針對[!UICONTROL 自動分配]活動等使用 [!UICONTROL Analytics for Target] (A4T) 作為報告來源) 中報告資料不一致的問題。(TGT-46112)
* 將 PUT 呼叫 Target 傳遞 API 的逾時時間增加到 15 秒，以避免發生逾時錯誤。(TGT-46091)
* 已修復瀏覽單次頁面應用程式 (SPA) 網站時 URL 無法持續&#x200B;&#x200B;更新的問題。(TGT-45417)

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

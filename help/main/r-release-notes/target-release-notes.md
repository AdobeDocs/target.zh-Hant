---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: dbf9a51044f317d02a705f2331d6dc58b6549606
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 100%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2023 年 10 月 3 日**

>[!NOTE]
>
>發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 23.9.4 (2023 年 10 月 4-6 日)

我們將根據以下排程分批發行此版本：

* **10 月 4 日**：亞太 (APAC) 區域
* **10 月 5 日**：歐洲、中東和非洲 (EMEA) 區域
* **10 月 6 日**：美洲區域

此版本包含下列增強功能和修正：

| 功能 | 詳細資料 |
| --- | --- |
| [!UICONTROL 活動] UI 重新整理<P>和<P>[!UICONTROL 摘要] UI 重新整理 | 作為 [!DNL Adobe Target] 的一份子，團隊持續努力改進 [!DNL Target] 使用者的使用者體驗，本次的版本重新整理了 [!DNL Target] UI 中的[!UICONTROL 活動]和[!DNL Recommendations] [!UICONTROL 摘要]頁面。本次更新統一並標準化先前不一致的設計模式，同時加入了新的增強功能。<P>如需詳細資訊，請參閱[活動](/help/main/c-activities/activities.md)和[摘要](/help/main/c-recommendations/c-products/feeds.md)。 |
| [!DNL Recommendations] 實作模式 | 「*使用 at.js 的 Recommendations 實作模式*」文章可協助您在使用 at.js JavaScript 程式庫時理解並建立您的 [!DNL Adobe Target Recommendations] 實作。<P>如需更多資訊，請參閱 *Adobe Target 開發人員指南*&#x200B;中的[使用 at.js 的 Recommendations 實作模式概觀](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank}。 |

* 已新增 [!UICONTROL Visual Experience Composer] (VEC) 動態框架增強功能。(TGT-44064)
* 已修正造成 `getViewInAnalyticsId` 要求中的所選日期無法正確更新的問題。此修正有助於當日期範圍和量度報告設定變更時重新計算報告中的 [!DNL Analytics] 連結。(TGT-46246)

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

## [!DNL Target] Standard/Premium 23.5.2 (日期待定)

此版本包含下列增強功能和修正：

* 為 [!DNL Adobe Analytics] 量度啟用最佳化準則選擇。
* 啟用透過 Sling 工作同步外部對象。
* 已修正不支援 SC 報告套裝名稱中包含點字元的問題。
* 啟用允許客戶刪除和編輯內建對象的功能。

## [!DNL Target] Standard/Premium 23.5.3 (日期待定)

此版本包含下列增強功能：

| 功能 | 詳細資料 |
|--- |--- |
| [!UICONTROL QA 模式]適用於 [!UICONTROL Automated Personalization] 活動 | [!DNL Adobe Target][!UICONTROL QA 模式]現在可用於 [!UICONTROL Automated Personalization] 活動，取代[!UICONTROL 預覽連結]功能。<P>如需詳細資訊，請參閱[活動 QA](/help/main/c-activities/c-activity-qa/activity-qa.md)。 |

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: c351044163a6fb32ca72fa015724d3b0388c059a
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 100%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## Target 平台發行版本 (2022 年 5 月 25 日)

此版本包含下列增強功能和修正：

* 新增的「[使用者代理用戶端提示](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/user-agent-and-client-hints.md)」支援。
* 修正在「[!UICONTROL 體驗鎖定]」 (XT) 活動中提供「[!UICONTROL 優惠方案決策]」時會斷斷續續引起逾時的問題。 (TNT-44611)

## at.js 2.9.0 版 (2022 年 5 月 27 日)

* 新增的「[使用者代理用戶端提示](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/user-agent-and-client-hints.md)」支援。
* 修正了同一個頁面上多個 mbox 請求有不同印象 ID 的問題。

## [!DNL Target Standard/Premium] 22.5.1 (分批發行；2022 年 5 月 11 至 13 日)

我們將根據以下排程分批發行此版本：

* **5 月 11 日**：亞太 (APAC) 區域
* **5 月 12 日**：美洲區域
* **5 月 13 日**：歐洲、中東和非洲 (EMEA) 區域

此版本包含下列增強功能和修正：

* 已修正造成 JavaScript 錯誤以及部分客戶無法存取特定 [!UICONTROL Automated Personalization] (AP) 活動的活動詳細資訊的錯誤。(TGT-43526)
* 已修正導致部分客戶無法新增 (或編輯) 特定優惠方案至 AP 活動的問題。(TGT-43503)
* 已修正 [!DNL Target] UI 中顯示下列錯誤訊息的問題：「您的全域 mbox 可能不同步。請嘗試重新儲存。」這個問題是 UI 問題，並不會影響客戶的實作。(TGT-43475)
* 已修正導致一位客戶無法編輯活動的經驗層級微調和受眾的問題 (若該微調和受眾是在部署新的[!UICONTROL 受眾] UI 之前建立的)。(TGT-43433)
* 已修正允許客戶在編輯活動的通報受眾時可選取重複 [!DNL Adobe Audience Manager] (AAM) 受眾的問題。(TGT-43430)
* 已修正導致客戶除了在不同的工作區外無法建立重複受眾的問題。 (TGT-43423)
* 已修正導致客戶對於在[!UICONTROL 表單式體驗撰寫器]中建立的活動中擁有臨時優惠方案的位置無法進行刪除的問題。(TGT-43315)
* 已修正導致客戶在按下影像優惠方案然後重新整理 UI 之後無法存取代碼優惠方案的問題。(TGT-43566)
* 已修正導致對個人資料指令碼的編輯在編輯、啟動然後停用該指令碼後恢復為原始、未編輯的指令碼的問題。該個人資料指令碼現在保持在其已編輯狀態。(TGT-43249)
* 已修正在嘗試將受眾移動到另一個工作區時導致以下錯誤的問題：「我們無法完成您的請求。如果問題仍然存在，請聯絡 Adobe 客戶服務」。(TGT-43212)
* 已修正在複製單次頁面應用程式 (SPA) 頁面的自訂代碼修正時導致錯誤的錯誤。(TGT-43137)
* 已修正導致在複製體驗接著編輯促銷後原始促銷受到影響的問題。(TGT-41775)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些發行說明中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 舊版發行說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 發行說明 | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。如需詳細資訊，請參閱「<br>Creative Cloud 發行說明[」。](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html) |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html) |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括搶鮮版版本資訊，請參閱 [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md)頁面。 |

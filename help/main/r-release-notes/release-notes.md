---
keywords: 版本注意事項;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6bef27637c06f39ffc0e755f19e8a0870ec749e5
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 87%

---

# Target 版本注意事項 (最新)

這些版本注意事項提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的版本注意事項以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target] Standard/Premium 22.9.1 (分批發行：2022 年 9 月 13 至 15 日)

我們將根據以下排程分批發行此版本：

* **9 月 13 日**：歐洲、中東和非洲 (EMEA) 區域
* **9 月 14 日**：美洲區域
* **9 月 15 日**：亞太 (APAC) 區域

此版本包含下列增強功能和修正：

* 新增 [!UICONTROL 跨網域] 選項，在下載at.js 2.10.0（和更新版本）時允許或停用設定第三方Cookie。 (TGT-43674)
* 更新 [!DNL Target] UI會通知客戶 [!DNL Recommendations] 摘要失敗。 (TGT-35811)
* 修正導致 [!UICONTROL Decision Offers] 無法在 [!UICONTROL Visual Experience Composer] (VEC) 內正常作用的問題。(TGT-43866)
* 修正在建立 [!UICONTROL Multivariate Testing] (MVT) 活動時，當選取 [!UICONTROL Clicked an Element] 轉換目標時導致錯誤訊息顯示的問題。(TGT-43842)
* 修正讓「[!UICONTROL 曝光次數]」欄不會在 [!UICONTROL Automated Personalization] (AP) 活動的已下載 CSV 報告檔案中顯示的問題。 (TGT-43780)
* 修正在使用 [!UICONTROL Form-Based Experience Composer] 時客戶無法在複製體驗後編輯 HTML/JSON 優惠的問題。(TGT-43633)
* 修正客戶無法從非預設工作區複製 [!UICONTROL A/B 測試] 活動至另一個非預設工作區的問題。(TGT-41910)
* 修正問題，確保客戶可正確顯示 [!DNL Recommendations] 對象（設計、條件、集合等） [!UICONTROL A/B測試] 和 [!UICONTROL 體驗鎖定] (XT)包含建議的活動，也會刪除不再使用的條件物件 [!DNL Target] UI和 [!DNL Recommendations] 後端。 (TGT-42331)
* 修正在擷取參數時造成網路逾時警報在 [!DNL Target] UI 中出現的問題。(TGT-43737)
* 已進行 UI 更新，以確保可以使用鍵盤存取某些拖放動作。(TGT-42969)
* 已進行 UI 更新，以確保文字字串正確本地化。

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
| Adobe Experience Cloud 版本注意事項 | 檢視 Adobe Experience Cloud 解決方案的最新版本注意事項。<br>如需詳細資訊，請參閱「[Experience Cloud 版本注意事項](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)」。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html) |
| 即將發佈的版本注意事項 | 如需本月的 Target 版本的詳細資訊，包括搶鮮版版本資訊，請參閱 [Target 版本注意事項 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md)頁面。 |

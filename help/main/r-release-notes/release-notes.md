---
keywords: 版本注意事項;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 8c348f40be8df5018d63c6b6fe75e1f8e804eafc
workflow-type: ht
source-wordcount: '1001'
ht-degree: 100%

---

# Target 版本注意事項 (最新)

這些版本注意事項提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的版本注意事項以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target] Standard/Premium 22.10.3 (分批發行：2022 年 10 月 25 至 27 日)

我們將根據以下排程分批發行此版本：

* **10 月 25 日**：歐洲、中東和非洲 (EMEA) 區域
* **10 月 26 日**：亞太 (APAC) 區域
* **10 月 27 日**：美洲區域

此版本包含以下新功能、增強功能和修正：

| 功能 | 詳細資料 |
| --- | --- |
| 為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]<br>最佳化 A4T 量度 (可供特定客戶進行測試。將在未來版本中提供給所有客戶。) | 請注意下列變更：<ul><li>針對 [!UICONTROL Analytics for Target] A4T 報告中的[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動，新增對非二進位和最大化量度的支援</li><li>保留現有活動的行為，直到 2023 年 2 月。在此日期之後，將停止活動以強制現有活動遷移至新行為</li><li>從 2023 年 2 月 20 日開始，將不再支援 [!DNL Target] 活動中的 `averagetimespentonsite`、 `bouncerate` 和 `entries` 量度。</li></ul> |

* 在 [!DNL Target] UI 中新增工具提示，以幫助客戶更有效地瀏覽對象產生器，並了解如何使用不熟悉的功能。(TGT-44139)
* 新增功能，此功能可防止客戶編輯因使用不受支援的量度而被 [!DNL Target] 停用的活動。UI 中的訊息，可指引客戶複製活動，然後更新轉換量度。

   在此版本中，[!DNL Target] 活動中的 `averagetimespentonsite`、`bouncerate` 和 `entries` 量度，新活動將停止使用。現有活動可以繼續使用這些量度直到 2023 年 5 月。

* 在 [!DNL Target] UI 中新增工具提示，以幫助客戶在建立或編輯使用 A4T 的[!UICONTROL 自動鎖定目標]活動時選取最佳化準則。

## [!DNL Target] Standard/Premium 22.10.1 (分批發行：2022 年 10 月 10 至 13 日)

我們將根據以下排程分批發行此版本：

* **10 月 10 日**：亞太 (APAC) 區域
* **10 月 12 日**：美洲區域
* **10 月 13 日**：歐洲、中東和非洲 (EMEA) 區域

此版本包含以下新功能、增強功能和修正：

| 功能 | 詳細資料 |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) 體驗片段 | AEM 體驗片段功能的更新包括以下內容：<ul><li>已新增在[!UICONTROL 選件]清單中按類型 (HTML 或 JSON) 篩選 AEM 體驗片段的功能。 (TGT-43121)</li><li>已修正允許客戶在使用 VEC 時插入 JSON [!UICONTROL 體驗片段]選件的問題，此狀況不受支援。只有在使用[!UICONTROL 表單式體驗]編排器時，才能插入 JSON 選件。(TGT-43846)</li></ul>如需詳細資訊，請參閱 AEM [體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。 |
| 新的適用於 Google Chrome 的 [!UICONTROL Visual Experience Composer] 擴充功能 | 新的適用於 Chrome 的 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) 擴充功能，Chrome 網站商店提供<br>2023 年 1 月起，目前 [!DNL Target] VEC Helper 擴充功能將停止在 Google Chrome 中運作，因為 Google 不允許使用 Manifest V2 的擴充功能。下載新的擴充功能，從新的一年開始，繼續在 [!DNL Target] 中以視覺方式創作您的網站。<br>以下連結顯示 Chrome 網站商店中的兩個擴充功能：<ul><li>[新擴充功能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[舊擴充功能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>如需詳細資訊，請參閱「[Visual Editing Helper 擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)」。 |
| 文件更新 | 主要文件更新包含以下項目：<ul><li>新的和更新的 [Adobe Target 管理和報告 API 文件 ](https://developer.adobe.com/target/administer/admin-api/) {target=_blank} 包含完整的管理和報告 API 端點，包括性質、選件、主機、環境、用戶端、對象、活動等。<br>在 [[!DNL Adobe Target] [!UICONTROL 開發人員指南]](https://developer.adobe.com/target/){target=_blank}中查看此內容和其他開發人員內容。</li><li>[A/Bn 測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>本文記錄了 [!DNL Adobe Target] 中手動 A/Bn 測試使用的詳細統計計算。<br>本文資訊取代了 *Adobe Target 中 A/B 測試使用的計算* pdf 檔案 (先前可在此網站下載)。</li></ul> |

* 已修正導致對象規則資訊無法在[!UICONTROL 對象細分]資訊視窗中正確顯示的問題。(TGT-43917)
* 已改進當載入對象人數接近[鎖定目標規則建議上限](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules)時的 [!DNL Target] UI 性能。(TGT-43675)
* 已修正從[!UICONTROL 編排]切換到[!UICONTROL 瀏覽]模式後，在 VEC 中建立或編輯活動時，導致某些元件在 [!UICONTROL 體驗] 頁面的[!UICONTROL 修改]面板中無法正確顯示的問題。(TGT-43300)
* 已修正導致部分客戶無法封存使用[!UICONTROL 自動鎖定目標]的 [!UICONTROL A/B 測試] 的問題。(TGT-40978)
* 已新增在單一報表群組內的多個位置自動使用單一選件的功能。(TGT-40689)

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

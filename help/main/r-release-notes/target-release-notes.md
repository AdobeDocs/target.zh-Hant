---
keywords: 版本注意事項;發行;更新;未來發行;增強;新功能;修正;更新;版本注意事項
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c5445903e7bbab210d0e72200c54ab07975c21c5
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 91%

---

# Target 版本注意事項 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2022 年 10 月 4 日**

若要檢視目前版本的相關資訊，請參閱「[Target 版本注意事項](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 22.10.1 (分批發行：2022 年 10 月 5 至 7 日)

我們將根據以下排程分批發行此版本：

* **10 月 5 日**：亞太 (APAC) 區域
* **10 月 6 日**：美洲區域
* **10 月 7 日**：歐洲、中東和非洲 (EMEA) 區域

此版本包含以下新功能、增強功能和修正：

| 功能 | 詳細資料 |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM)體驗片段 | AEM體驗片段功能的更新包括：<ul><li>新增可依下列類型(HTML或JSON)篩選AEM體驗片段的功能： [!UICONTROL 選件] 清單。 (TGT-43121)</li><li>已修正允許客戶在使用 VEC 時插入 JSON [!UICONTROL 體驗片段]選件的問題，此狀況不受支援。只有在使用[!UICONTROL 表單式體驗]編排器時，才能插入 JSON 選件。(TGT-43846)</li></ul>如需詳細資訊，請參閱AEM [體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| 新的適用於 Google Chrome 的 [!UICONTROL Visual Experience Composer] 擴充功能 | 新的適用於 Chrome 的 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) 擴充功能，Chrome 網站商店提供<br>2023 年 1 月起，目前 [!DNL Target] VEC Helper 擴充功能將停止在 Google Chrome 中運作，因為 Google 不允許使用 Manifest V2 的擴充功能。下載新的擴充功能，從新的一年開始，繼續在 [!DNL Target] 中以視覺方式創作您的網站。<br>以下連結顯示 Chrome 網站商店中的兩個擴充功能：<ul><li>[新擴充功能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[舊擴充功能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>如需詳細資訊，請參閱 [Visual Editing Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| 優化的 A4T [!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]<br> 量度 (確切發行日期尚未確定。) | 請注意下列變更：<ul><li>針對 [!UICONTROL Analytics for Target] A4T 報告中的[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動，新增對二進位和最大化量度的支援</li><li>保留現有活動的行為，直到 2023 年 2 月 20 日。在此日期之後，將停止活動以強制現有活動遷移至新行為</li><li>從 2023 年 2 月 20 日開始，將不再支援 [!DNL Target] 活動中的 `averagetimespentonsite`、 `bouncerate` 和 `entries` 量度。</li></ul> |

* 已修正導致對象規則資訊無法在[!UICONTROL 對象細分]資訊視窗中正確顯示的問題。(TGT-43917)
* 已改進當載入對象人數接近[鎖定目標規則建議上限](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules)時的 [!DNL Target] UI 性能。(TGT-43675)
* 已修正從[!UICONTROL 編排]切換到[!UICONTROL 瀏覽]模式後，在 VEC 中建立或編輯活動時，導致某些元件在 [!UICONTROL 體驗] 頁面的[!UICONTROL 修改]面板中無法正確顯示的問題。(TGT-43300)
* 已修正導致部分客戶無法封存使用[!UICONTROL 自動鎖定目標]的 [!UICONTROL A/B 測試] 的問題。(TGT-40978)
* 已新增在單一報表群組內的多個位置自動使用單一選件的功能。(TGT-40689)

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

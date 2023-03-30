---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: db093dd3812e211a0e1437b522adcd5f87bc2e41
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 96%

---

# [!DNL Target] 發行說明 (最新)

這些版本注意事項提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的版本注意事項以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target] Standard/Premium 23.3.1 (2023 年 3 月 28 至 30 日)

我們將根據以下排程分批發行此版本：

* **3 月 28 日**：歐洲、中東和非洲 (EMEA) 區域
* **3 月 29 日**：亞太 (APAC) 區域
* **3 月 30 日**：美洲區域

此版本包含以下新功能、增強功能和修正：

| 功能 | 詳細資料 |
|--- |--- |
| 為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]最佳化的 A4T 量度<p> (發行日期：2023 年 3 月 30 日) | [!DNL Target]可讓您在為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動使用 [!UICONTROL A4T] 時，選擇以二項式事件為基礎的量度，或是以持續事件為基礎的量度。<P>請注意受支援量度的以下變更：<ul><li>[!DNL Target] 已保留現有活動的先前行為，直到 2023 年 9 月 9 日。在此日期之後，將停止使用非支援之量度的活動，以強制現有活動遷移至新行為。</li></ul>如需詳細資訊，請參閱 [適用於 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported).<br>已結合此功能更新下列教學課程：<ul><li>[在  [!DNL Analysis Workspace]  中設定[!UICONTROL 自動分配]活動的 A4T 報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li><li>[在  [!DNL Analysis Workspace]  中設定[!UICONTROL 自動鎖定目標]活動的 A4T 報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

* 增強對象和活動同步，以便在 [!DNL Adobe Experience Platform] 和 [!DNL Adobe Audience Manager] 中建立的項目可更快地在 [!DNL Target] UI 中使用。(TGT-44568)
* 進行變更以允許使用者在[!UICONTROL 管理] > [!UICONTROL Visual Experience Composer] > [!UICONTROL 預設 URL] 下刪除[!UICONTROL 預設 URL]。此變更可讓客戶將預設 URL 變更回空字串，這在以前於初始設定後是不可能的。(TGT-44577)
* 刪除禁止客戶編輯或刪除現成可用對象 (具有保留名稱的對象) 的限制。(TGT-44655)
* 停用建立[合併的對象](/help/main/c-target/combining-multiple-audiences.md)期間在載入進度環時會出現在 [!DNL Target] UI 的「[!UICONTROL 完成]」選項。(TGT-44079)
* 修正 [!UICONTROL Audiences] 頁面底部的[!UICONTROL 語言]連結，以便正確連結到「[!UICONTROL 帳戶通訊偏好設定]」頁面。(TGT-43562)
* 有時客戶在[!UICONTROL 管理] > [!UICONTROL 報告] > [!UICONTROL 報告 Experience Cloud 解決方案]下選取 [!UICONTROL Adobe Analytics] 後，無法建立 [!UICONTROL A/B 測試]活動，這個問題已經修正。(TGT-44844)
* 客戶無法檢視[!UICONTROL 多變數測試]活動中的最後一個體驗，有許多來自 [!UICONTROL Visual Experience Composer] (VEC) 內的體驗，這個問題已經修正。VEC 底部的 [DOM 路徑](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)有時會造成客戶無法看到最後一個體驗。(TGT-44578)
* 如果頁面要求授權或叫用重新導向，VEC 中的瀏覽 URL 無法反映目前頁面，而此頁面在正常瀏覽器工作階段是可見的，這個問題已經修正。(TGT-44350)
* 客戶無法在 [!UICONTROL Recommendations] > [!UICONTROL 設定]中變更[!UICONTROL 篩選不相容的條件]設定，這個問題已經修正。(TGT-44398)
* 使用 [!UICONTROL Analytics 分類]和名稱有點符號的報表套裝時，建立新 [!DNL Recommendations] 摘要的 POST 要求會失敗，這個問題已經修正。(TGT-44598)
* 更新 [!DNL Target] UI 中的連結以指向新的 [Visual Editing Helper 擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。(TGT-44459)
* 增強安全性以防止在 [!DNL Recommendations] 摘要中嘗試伺服器端請求偽造 (SSRF)。(TGT-43769)
* 如果影像名稱包含 [GB18030 字元](https://en.wikipedia.org/wiki/GB_18030)，客戶無法檢視 [!DNL Recommendations] 設計中的預覽影像{target=_blank}，這個問題已經修正。(TGT-44614)
* 在編輯活動[!UICONTROL 體驗]頁面中的[!UICONTROL 文字/HTML] 時[!UICONTROL 修改]面板中的部分 [GB18030 字元](https://en.wikipedia.org/wiki/GB_18030){target=_blank}會逸出，這個問題已經修正。(TGT-44600)
* 對整個 [!DNL Target] UI 進行了各種本地化修正。

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

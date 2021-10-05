---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 資料庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些新功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: ht
source-wordcount: '727'
ht-degree: 100%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也會隨附 Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明，以及其他平台變更 (如適用)。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本，以避免您的網站出現任何潛在問題。如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 21.9.1 (2021 年 9 月 14 日)

此維護發行包含下列增強功能、修正和變更。

* 修正由於某些網頁瀏覽器中針對第三方 Cookie 的新安全性原則而導致客戶無法登入[!UICONTROL 可視化體驗撰寫器] (VEC) 的問題。 此問題已在[疑難排解可視化體驗撰寫器和增強體驗撰寫器的相關問題](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)的「使用 Google Chrome 80+ 版時，未在可視化體驗撰寫器 (VEC) 或增強體驗撰寫器 (EEC) 中載入的頁面」中進行了討論。
* 修正了導致 VEC 中的產品名稱顯示的是產品路徑而不是產品易記名稱的問題。 (TGT-41300)
* 體驗名稱現在反映在 [!DNL Analysis Workspace] A4T 活動中 (TGT-38674)
* 修正了 [!DNL Recommendations] 中，將重複活動的促銷中的實體 ID 變更錯誤地套用至原始活動的問題。 (TGT-41482)
* 修正了阻止 [編輯標準] 按鈕在[!UICONTROL 體驗]頁面 (針對 VEC 的 [!DNL Recommendations] 活動) 上正確顯示的問題。 (TGT-39512)
* 修正了在重複和複製到測試工作區時阻止活動同步的問題。 (TGT-40686)
* 修正了 VEC 中阻止修改具有[體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)的選擇器 (使用 [[!UICONTROL 之後插入]]) 的問題。 (TGT-41802)
* 修正了阻止將產品中的空 JSON 內容傳送到後端的問題。 [!DNL Target] 現在會傳送 JSON 物件，即使它是空的。 (TGT-41555)
* 修正了導致舊 [!DNL Analytics] 報告開啟而非 [!DNL Analysis Workspace] (當客戶在檢視報告時點擊「[!UICONTROL 在 Analytics 中檢視]」) 的問題。 (TGT-41867)
* 當客戶嘗試選取 [!DNL Analytics] 作為[!UICONTROL 自動個人化]活動的報告來源 (A4T) 時，向顯示的 UI 訊息新增了額外說明。 訊息會指出「[!DNL Target] 是[!UICONTROL 自動個人化]活動唯一支援的來源。」 (TGT-41954)
* 當客戶嘗試使用「新行」而不是逗號分隔主機時，對錯誤訊息新增了額外的說明。 (TGT-40671)
* 修正了導致某些活動的「[!UICONTROL 上次更新]」日期在西班牙文和日文客戶的英文 UI 中不同的問題 (以西班牙文和日文檢視 UI 時)。 (TGT-38980)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh_Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 資料庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些發行說明中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 舊版發行說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版發行說明](/help/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 發行說明 | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。如需詳細資訊，請參閱「<br>Creative Cloud 發行說明[」。](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html??lang=zh-Hant) |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html) |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 發行說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |

---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 資料庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些新功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 57%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也會隨附 Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明，以及其他平台變更 (如適用)。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本，以避免您的網站出現任何潛在問題。如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 21.9.1（2021年9月14日）

此維護發行包含下列增強功能、修正和變更。

* 修正由於某些網頁瀏覽器中第三方Cookie的新安全性原則，客戶無法登入[!UICONTROL 可視化體驗撰寫器](VEC)的問題。 在[疑難排解可視化體驗撰寫器和增強體驗撰寫器的相關問題](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)中，「使用Google Chrome 80+版時，可視化體驗撰寫器(VEC)或增強體驗撰寫器(EEC)中未載入頁面」中討論了此問題。
* 修正VEC中的選件名稱顯示選件路徑，而非選件易記名稱的問題。 (TGT-41300)
* A4T活動的[!DNL Analysis Workspace]現在會反映體驗名稱(TGT-38674)
* 修正[!DNL Recommendations]中，重複活動中促銷活動中套用的實體ID誤變至原始活動的問題。 (TGT-41482)
* 修正VEC中[!DNL Recommendations]活動的[!UICONTROL 體驗]頁面上，無法正確顯示「編輯條件」按鈕的問題。 (TGT-39512)
* 修正複製和複製到測試工作區時，無法同步活動的問題。 (TGT-40686)
* 修正在VEC中使用「[!UICONTROL Insert After]」時，無法修改具有[體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)的選取器的問題。 (TGT-41802)
* 修正無法將選件中的空JSON內容傳送至後端的問題。 [!DNL Target] 現在會傳送JSON物件，即使它為空。(TGT-41555)
* 修正當客戶檢視報表時按一下「[!UICONTROL 在Analytics中檢視」時，導致開啟舊版[!DNL Analytics]報表而非[!DNL Analysis Workspace]的問題。 ](TGT-41867)
* 新增當客戶嘗試為[!UICONTROL Automated Personalization]活動選取[!DNL Analytics]作為報表來源(A4T)時，已顯示之UI訊息的其他說明。 訊息指出，「[!DNL Target]是[!UICONTROL Automated Personalization]活動唯一支援的來源。」 (TGT-41954)
* 新增當客戶嘗試以「新行」（而非逗號）分隔主機時，錯誤訊息的其他說明。 (TGT-40671)
* 修正部分活動「[!UICONTROL Last Updated]」日期與西班牙和日本客戶的英文UI不同（以西班牙文和日文檢視UI時）的問題。 (TGT-38980)

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

---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本包含哪些新功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 6957eb88e2ee7d54fdad5afeaedf75b091b601e7
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 36%

---

# Target 發行說明 (發行前)

本文包含發行前資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新: 2021 年 9 月 14 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>為避免您的網站出現任何潛在問題，請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

## [!DNL Target Standard/Premium] 21.9.1（2021年9月14日）

此維護發行包含下列增強功能、修正和變更。

* 修正由於某些網頁瀏覽器中第三方Cookie的新安全性原則，客戶無法登入[!UICONTROL 可視化體驗撰寫器](VEC)的問題。 在[疑難排解可視化體驗撰寫器和增強體驗撰寫器的相關問題](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)中，「使用Google Chrome 80+版時，可視化體驗撰寫器(VEC)或增強體驗撰寫器(EEC)中未載入頁面」中討論了此問題。
* 修正VEC中的選件名稱顯示選件路徑，而非選件易記名稱的問題。 (TGT-41300)
* 修正[!DNL Recommendations]中，重複活動中促銷活動中套用的實體ID誤變至原始活動的問題。 (TGT-41482)
* 修正VEC中[!DNL Recommendations]活動的[!UICONTROL 體驗]頁面上，無法正確顯示「編輯條件」按鈕的問題。 (TGT-39512)
* 修正複製和複製到測試工作區時，無法同步活動的問題。 (TGT-40686)
* 修正在VEC中使用「[!UICONTROL Insert After]」時，無法修改具有[體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)的選取器的問題。 (TGT-41802)
* 修正無法將選件中的空JSON內容傳送至後端的問題。 [!DNL Target] 現在會傳送JSON物件，即使它為空。(TGT-41555)
* 修正當客戶檢視報表時按一下「[!UICONTROL 在Analytics中檢視」時，導致開啟舊版[!DNL Analytics]報表而非[!DNL Analysis Workspace]的問題。 ](TGT-41867)
* 新增當客戶嘗試為[!UICONTROL Automated Personalization]活動選取[!DNL Analytics]作為報表來源(A4T)時，已顯示之UI訊息的其他說明。 訊息指出，「[!DNL Target]是[!UICONTROL Automated Personalization]活動唯一支援的來源。」 (TGT-41954)
* 新增當客戶嘗試以「新行」（而非逗號）分隔主機時，錯誤訊息的其他說明。 (TGT-40671)
* 更新區段的[!UICONTROL 類型]欄位，以準確包含[!DNL Platform]和[!DNL AAM]([!DNL Adobe Audience Manager])。 (TGT-41328)
* 修正在按一下[!UICONTROL Save]後，流量來源運算元變更的問題。 (TGT-41408)
* 儲存僅限於此活動的對象（以規則為基礎或結合）後，UI現在會載入[!UICONTROL 對象]選擇器，並套用僅限於此活動的篩選器。 (TGT-41747).
* 修正從來源([!DNL Adobe Experience Platform]、[!UICONTROL AAM]等)刪除的對象繼續顯示在[!DNL Target] UI中的問題。
* 在[!UICONTROL 對象]頁面新增篩選選項，以僅顯示從[!DNL Adobe Experience Platform]匯入的對象。 (TGT-41298)
* 在[!UICONTROL Audiences] UI中新增增強的鍵盤協助工具選項。 (TGT-39927)
* 修正部分活動「[!UICONTROL Last Updated]」日期與西班牙和日本客戶的英文UI不同（以西班牙文和日文檢視UI時）的問題。 (TGT-38980)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

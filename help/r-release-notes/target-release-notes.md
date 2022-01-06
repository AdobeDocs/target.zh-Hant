---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本包含哪些新功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: df00a36ea3440ebd959351fcfc6a24f6bd9fe8b8
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 86%

---

# Target 發行說明 (發行前)

本文包含發行前資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**最近更新日期: 2022 年 1 月 6 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>為避免您的網站出現任何潛在問題，請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

## [!DNL Target Standard/Premium] 22.1.1（2022年1月6日）

此版本包含下列新功能：

| 功能 | 詳細資料 |
| --- | --- |
| 在Target活動中使用選件決策 | 您現在可以使用 [!DNL Adobe Journey Optimizer] 在 [!DNL Adobe Target] A/B測試和體驗鎖定目標(XT)活動，以決定下一個最佳選件，並在網頁和行動裝置上提供給您的訪客。<br>如需詳細資訊，請參閱使用優惠方案決策。<br>**附註**:此功能適用於 [!DNL Target] 也可存取Offer decisioning的客戶，且 [!DNL Target] 以AdobeExperience Platform Web SDK為基礎的實作。 |

## at.js 2.7.0 版 (2021 年 10 月 28 日)

此版本包含下列增強功能：

* 新增 [Web 元件](https://developer.mozilla.org/en-US/docs/Web/Web_Components)的支援。在自訂元素及其內部元素上建立和測試個人化體驗和選件，必須有此版本的 at.js。此功能包含在 [!DNL Target Standard/Premium] 21.10.5 版。

## [!DNL Target Standard/Premium] 21.10.5 (2021 年 10 月 28 日)

此維護版本包含下列增強功能：

| 功能 | 詳細資料 |
| --- | --- |
| [!UICONTROL Visual Experience Composer] (VEC) | 新增 [Web 元件](https://developer.mozilla.org/en-US/docs/Web/Web_Components)的支援。在自訂元素及其內部元素上，可建立和測試個人化體驗和選件。<br>如需詳細資訊，請參閱[可視化體驗撰寫器選項](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom)。 |

## [!DNL Target Standard/Premium] 21.10.4 (2021 年 10 月 21 日)

此維護版本包含下列增強功能：

| 功能 | 詳細資料 |
| --- | --- |
| 購物車型推薦 | 新增一系列演算法，以根據訪客購物車的內容提供推薦。<br>如需詳細資訊，請參閱[建立條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md)中的「購物車型」，以及[計劃和實作 Recommendations](/help/c-recommendations/plan-implement.md) 中的「購物車新增/購物車檢視/結帳頁面」和「排除訪客購物車中已有的項目」。 |

## [!DNL Target Standard/Premium] 21.10.3 (2021 年 10 月 19 日)

此維護發行包含下列增強功能、修正和變更。

* 修正在按一下 [!DNL Target] 活動報告中的「[!UICONTROL 在 Analytics 中檢視]」按鈕後，無法開啟 [!DNL Analysis Workspace] [!UICONTROL A4T] 面板的問題。(TGT-42099 和 TGT-42100)
* 修正在使用[!UICONTROL 表單式體驗撰寫器]編輯 [!UICONTROL A/B 測試]和[!UICONTROL 體驗鎖定] (XT) 活動時，造成「[!UICONTROL 編輯設計]」按鈕不顯示的問題。(TGT-41980)
* 修正在建立新的 [!UICONTROL Recommendations] 活動時，「[!UICONTROL 相容]」核取方塊無法顯示在條件選取中的問題。(TGT-42053)
* 修正因為缺少 [!DNL Analytics] 權限而無法選取 [!DNL Analytics] 做為報告來源 (A4T) 時所顯示的不正確錯誤訊息。(TGT-41954)
* 實作多項協助工具修正，以改善 [!DNL Target] UI 鍵盤導覽。

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

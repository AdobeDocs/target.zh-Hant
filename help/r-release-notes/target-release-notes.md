---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本包含哪些新功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3fb58864e265653b48e851c8dff404589bb867a6
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 51%

---

# Target 發行說明 (發行前)

本文包含發行前資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2021 年 10 月 25 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>為避免您的網站出現任何潛在問題，請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

## [!DNL Target Standard/Premium] 21.10.5（2021年10月28日）

此維護髮行包含下列增強功能：

| 功能 | 詳細資料 |
| --- | --- |
| Visual Experience Composer (VEC) | 新增 [Web元件](https://developer.mozilla.org/en-US/docs/Web/Web_Components). 您可以在自訂元素和自訂元素內的元素上建立和測試個人化體驗和選件。<br>此版本與at.js 2.7.0版發行時同時發生。 |

## [!DNL Target Standard/Premium] 21.10.4（2021年10月21日）

此維護髮行包含下列增強功能：

| 功能 | 詳細資料 |
| --- | --- |
| 購物車型Recommendations | 新增一系列演算法，以根據訪客購物車的內容提供建議。<br>如需詳細資訊，請參閱 [建立條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md) 和「購物車新增/購物車檢視/結帳頁面」和「排除已在訪客購物車中的項目」，於 [計畫和實作Recommendations](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] 21.10.3（2021年10月19日）

此維護發行包含下列增強功能、修正和變更。

* 修正客戶無法開啟 [!UICONTROL A4T] 面板 [!DNL Analysis Workspace] 按一下 [!UICONTROL 在Analytics中檢視] 按鈕 [!DNL Target] 活動報表。 (TGT-42099 和 TGT-42100)
* 修正 [!UICONTROL 編輯設計] 編輯時不顯示的按鈕 [!UICONTROL A/B測試] 和 [!UICONTROL 體驗鎖定] (XT)使用 [!UICONTROL 表單式體驗撰寫器]. (TGT-41980)
* 修正無法 [!UICONTROL 相容] 建立新條件時在條件選取中顯示的核取方塊 [!UICONTROL Recommendations] 活動。 (TGT-42053)
* 修正無法選取時顯示的錯誤訊息 [!DNL Analytics] 作為報表來源(A4T)，因為 [!DNL Analytics] 權限。 (TGT-41954)
* 實作多項協助工具修正，以改善 [!DNL Target] UI。

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

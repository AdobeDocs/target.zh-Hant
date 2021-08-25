---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本包含哪些新功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: afa370a38921ab76babf5e49edc1e4b23ee807b0
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 99%

---

# Target 發行說明 (發行前)

本文包含發行前資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新：2021 年 8 月 24 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>為避免您的網站出現任何潛在問題，請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

## [!DNL Target Standard/Premium] 21.8.1（2021年8月10日）

此維護發行包含許多後端增強功能，包括下列客戶面向的變更：

* 修正在[!UICONTROL 表單式體驗撰寫器]中建立之 [!UICONTROL Auto Personalization] 活動的報表，會參照報表中已刪除之優惠的問題。此問題會導致顯示以下錯誤訊息：「擷取此報表的資料時遇到問題。如果問題仍然存在，請聯絡 Adobe 客戶服務。」(TGT-41028)

## Target Delivery API (2021 年 8 月 3 日)

此版本包含下列增強功能：

* mbox 參數限制已提高為 100 個參數。先前的限制為 50 個參數。(TNT-41717)
* `categoryId` 的限制已增加為 256 個字元。先前的限制為 128 個字元。
* 下列 [!DNL Adobe Audience Manager] (AAM) 詳細資料已新增至 Delivery API：

   * AAM UUID：用來唯一識別用戶的內部 AAM ID。
   * dataPartnerId：資料合作夥伴的 ID。
   * dataPartnerUserId：資料合作夥伴所提供的用戶 ID。

   先前的 Delivery API 只包含 `dcsLocationHint` 和 `blob`。(TNT-41644)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

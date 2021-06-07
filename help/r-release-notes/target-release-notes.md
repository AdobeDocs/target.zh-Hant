---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本包含哪些新功能？
feature: 發行說明
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 146395f5453093ca34b259a143ff4e4c63be949b
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 69%

---

# Target 發行說明 (發行前)

本文包含發行前資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新: 2021 年 6 月 7 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>為避免您的網站出現任何潛在問題，請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

## [!DNL Target Standard/Premium] 21.5.2（待定日期）

此版本包含下列新功能和增強功能。 括號內的問題編號供 [!DNL Adobe] 內部使用。

| 功能 | 詳細資料 |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | 下列增強功能適用於[!DNL Recommendations]人氣演算法：<ul><li>當[!DNL Target]為行為資料來源時，所有人氣（檢視次數最多/最暢銷商品）演算法都將提供新的六小時「回顧期間」（資料範圍）選項。 （當[!DNL Adobe Analytics]為行為資料來源時，此回顧期間為&#x200B;*not*&#x200B;可用。）</li><li>選取後，下列演算法大約每三小時執行一次（而非每12小時）。<ul><li>檢視次數最多</li><li>購買次數最多</li><li>按類別檢視次數最多</li><li>按類別購買次數最多</li><li>按自訂屬性檢視次數最多（使用groupBy功能）</li><li>按自訂屬性購買最多（使用groupBy功能）</li></ul></ul>(TOP-1086) |

此版本包含下列修正。

* 內容會隨著發行日期的臨近而新增。

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

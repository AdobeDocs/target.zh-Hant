---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本包含哪些新功能？
feature: 發行說明
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3be6ad187b99472ccd3019e6998eba4953e2f5b5
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 51%

---

# Target 發行說明 (發行前)

本文包含發行前資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**最近更新: 2021 年 5 月 24 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>為避免您的網站出現任何潛在問題，請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

## ![Adobe Experience Platform Web SDK](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] 版本2.5.0（2021年6月1日）

此版本的[!DNL Platform Web SDK]包含對以下內容的支援：

| 功能 | 詳細資料 |
| --- | --- |
| 透過[!UICONTROL Analytics for Target](A4T)重新導向支援 | 使用A4T時，Platform Web SDK現在支援[!DNL Target]重新導向。 [!DNL Adobe Target]中的重新導向選件會造成瀏覽器重新導向至新頁面。 |
| 回應 Token | Platform Web SDK現在支援[!DNL Target]回應Token。 回應Token可讓您自動將[!DNL Adobe Target]的特定資訊輸出至您品牌的網頁。 此資訊可包含活動、選件、體驗、使用者設定檔、地理資訊等的詳細資訊。 這些詳細資料提供額外的回應資料，可與內部或第三方系統共用，或用於除錯。 |

## [!DNL Target Standard/Premium] 21.5.1（2021年6月8日）

內容會隨著發行日期的臨近而新增。

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

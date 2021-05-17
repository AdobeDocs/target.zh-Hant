---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本包含哪些新功能？
feature: 發行說明
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b14c9bb4bc0363c77de084c7ae7110e73c5f2f13
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 36%

---

# Target 發行說明 (發行前)

本文包含發行前資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**最近更新: 2021 年 5 月 17 日**

若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>為避免網站出現任何潛在問題，請移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本。 如需詳細資訊，請參閱 [總覽：實施用戶端 Web 的 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## at.js 2.5.0版（2021年5月13日）

此版本的at.js包含下列增強功能和變更：

* [at.js的](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) 裝置上決策支援。
* [預](/help/c-activities/c-activity-qa/activity-qa.md) 覽Automated Personalization  (AP)活動的連結支援

此版本也移除對Microsoft Internet Explorer 10、Internet Explorer 11和所有舊版的支援。 at.js 2.5.0及更新版本仍支援Microsoft Edge。 如需更多資訊，請參閱[支援的瀏覽器](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)。

## [!DNL Adobe Experience Platform Web SDK] 2.5.0版（2021年5月24日）

此版本的[!DNL Platform Web SDK]包含[!UICONTROL  Analytics for Target](A4T)對[!DNL Target]重導的支援。

## [!DNL Target Standard/Premium] 21.5.1（2021年6月8日）

內容會隨著發行日期的臨近而新增。

## [!DNL Target Standard/Premium] 21.5.2（待定日期）

此版本包含下列新功能和增強功能。 括號內的問題編號供 [!DNL Adobe] 內部使用。

| 功能 | 詳細資料 |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | 下列增強功能適用於[!DNL Recommendations]人氣演算法：<ul><li>當[!DNL Target]為行為資料來源時，所有人氣（最常檢視／最暢銷商品）演算法都可使用新的六小時「回顧視窗」（資料範圍）選項。 （當[!DNL Adobe Analytics]是行為資料來源時，此回顧視窗為&#x200B;*not*。）</li><li>選取後，下列演算法大約每三小時（而非每12小時）執行一次。<ul><li>檢視次數最多</li><li>購買次數最多</li><li>依類別檢視次數最多</li><li>依類別購買的最多</li><li>自訂屬性檢視次數最多（使用groupBy功能）</li><li>自訂屬性購買最多（使用groupBy功能）</li></ul></ul>(TOP-1086) |

此版本包含下列修正。

* 內容會隨著發行日期的臨近而新增。

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

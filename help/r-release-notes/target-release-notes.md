---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本包含哪些新功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8f5e2c5025dc4b9caf31f51c03fb073ddd9ba756
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 41%

---

# Target 發行說明 (發行前)

本文包含發行前資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新: 2021 年 10 月 6 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>為避免您的網站出現任何潛在問題，請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

## [!DNL Target Standard/Premium] 21.10.1（2021年10月6日）

此版本包含下列新功能：

| 功能 | 詳細資料 |
| --- | --- |
|  AudiencesUI重新整理 | 作為[!DNL Adobe Target]團隊持續致力改善[!DNL Target]使用者的使用者體驗的一部分，此版本會重新整理[!DNL Target] UI中的[!UICONTROL  Audiences]和[!UICONTROL 設定檔指令碼]頁面。 此更新會統一及標準化先前不一致的設計模式，同時新增增強功能，例如：<ul><li>可同時選取和刪除多個對象</li><li>重新整理的[audience builder設計](/help/c-target/c-audiences/create-audience.md)</li><li>[!UICONTROL Audience]資料庫規則產生器中的排除規則支援</li><li>新的「受眾來源」篩選器，可加快受眾探索</li><li>工作階段持續搜尋和篩選選項</li></ul>如需詳細資訊，請參閱[對象](/help/c-target/target.md)。<br>**注意**:此UI重新整理只會影響EMEA地區的客戶。包括北美在內，世界其他地區的客戶下週將看到最新的UI。 |
| [!UICONTROL 設定檔] 指令碼UI重新整理 | [!UICONTROL 設定檔指令碼]程式庫也已更新，其中包含重新整理的介面以及數項生產力更新：<ul><li>可同時選取和刪除多個設定檔指令碼</li><li>描述檔指令碼的新程式碼編輯器</li><li>程式碼編輯器內的語法醒目提示和錯誤檢查</li><li>透過鍵盤快速鍵自動完成Token（mbox或設定檔）參數</li></ul>如需詳細資訊，請參閱[訪客設定檔](/help/c-target/c-visitor-profile/visitor-profile.md)。<br>**注意**:此UI重新整理只會影響EMEA地區的客戶。包括北美在內，世界其他地區的客戶下週將看到最新的UI。 |
| ![Premium徽](/help/assets/premium.png) 章Recommendations條件建立和編輯 | 已簡化[!UICONTROL Recommendations條件]建立和編輯工作流程，以簡化選擇正確建議演算法和設定以達成您的目標。<br>如需詳細資訊，請參閱 [建立條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md)。 |
| ![Premium徽](/help/assets/premium.png) 章Recommendations回顧期間和演算法重新整理率改善 | 您現在可以執行「檢視次數最多」和「最暢銷商品」演算法，並有六小時回顧期間，以擷取最近趨勢的內容。 選取六小時回顧期間後，您的建議結果會一天中每3到6小時更新一次。<br>如需詳細資訊，請參 [閱建](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) 立條 *件中的資料來源*。 |

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

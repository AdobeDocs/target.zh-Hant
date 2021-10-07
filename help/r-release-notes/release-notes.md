---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 資料庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些新功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 874c27fe7d0144b0485545cf687d50215309d416
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 58%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也會隨附 Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明，以及其他平台變更 (如適用)。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本，以避免您的網站出現任何潛在問題。如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 21.10.1（2021年10月6日）

此版本包含下列新功能：

| 功能 | 詳細資料 |
| --- | --- |
|  AudiencesUI重新整理 | 作為[!DNL Adobe Target]團隊持續致力改善[!DNL Target]使用者的使用者體驗的一部分，此版本會重新整理[!DNL Target] UI中的[!UICONTROL  Audiences]和[!UICONTROL 設定檔指令碼]頁面。 此更新會統一及標準化先前不一致的設計模式，同時新增增強功能，例如：<ul><li>可同時選取和刪除多個對象</li><li>重新整理的[audience builder設計](/help/c-target/c-audiences/create-audience.md)</li><li>[!UICONTROL Audience]資料庫規則產生器中的排除規則支援</li><li>新的「受眾來源」篩選器，可加快受眾探索</li><li>工作階段持續搜尋和篩選選項</li></ul>如需詳細資訊，請參閱[對象](/help/c-target/target.md)。<br>**注意**:此UI重新整理只會影響EMEA地區的客戶。包括北美在內，世界其他地區的客戶下週將看到最新的UI。 |
| [!UICONTROL 設定檔] 指令碼UI重新整理 | [!UICONTROL 設定檔指令碼]程式庫也已更新，其中包含重新整理的介面以及數項生產力更新：<ul><li>可同時選取和刪除多個設定檔指令碼</li><li>描述檔指令碼的新程式碼編輯器</li><li>程式碼編輯器內的語法醒目提示和錯誤檢查</li><li>透過鍵盤快速鍵自動完成Token（mbox或設定檔）參數</li></ul>如需詳細資訊，請參閱[訪客設定檔](/help/c-target/c-visitor-profile/visitor-profile.md)。<br>**注意**:此UI重新整理只會影響EMEA地區的客戶。包括北美在內，世界其他地區的客戶下週將看到最新的UI。 |
| ![Premium徽](/help/assets/premium.png) 章Recommendations條件建立和編輯 | 已簡化[!UICONTROL Recommendations條件]建立和編輯工作流程，以簡化選擇正確建議演算法和設定以達成您的目標。<br>如需詳細資訊，請參閱 [建立條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md)。 |
| ![Premium徽](/help/assets/premium.png) 章Recommendations回顧期間和演算法重新整理率改善 | 您現在可以執行「檢視次數最多」和「最暢銷商品」演算法，並有六小時回顧期間，以擷取最近趨勢的內容。 選取六小時回顧期間後，您的建議結果會一天中每3到6小時更新一次。<br>如需詳細資訊，請參 [閱建](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) 立條 *件中的資料來源*。 |

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

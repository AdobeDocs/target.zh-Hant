---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 資料庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 當前版本中包括哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: fd1d276cd01221be1fbde7931b4350edefe1965c
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 73%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也會隨附 Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明，以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 22.1.2（2022年1月26日）

| 功能 | 詳細資料 |
| --- | --- |
| [!DNL Adobe Experience Platform] 觀眾 [!DNL Target] | 您現在可以使用 [!DNL Adobe Experience Platform] 觀眾 [!DNL Target]。 的 [!DNL Target] 團隊， [!DNL Experience Platform] [!DNL Destinations] 團隊和 [!DNL Unified Profile Service] 團隊高興地宣佈&quot;同一頁/下一頁個性化&quot;使用案例的正式上市。<br>使用在 [!DNL Adobe Experience Platform] 提供更豐富的客戶資料，從而實現更有影響的個性化。 的 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank}(RTCP)，內置於 [!DNL Adobe Experience Platform] 幫助公司將來自多個企業來源的已知和匿名資料匯集到一起，以建立客戶配置檔案，這些配置檔案可用於即時提供跨所有渠道和設備的個性化客戶體驗。<br>有關詳細資訊，請參見 [使用來自Adobe Experience Platform的觀眾](/help/c-target/c-audiences/audiences.md#aep) 在 *建立受眾*。<br>請務必閱讀Adobe部落格並觀看視頻： [[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}。 |
| [!UICONTROL Audiences] UI 重新整理 | 作為 [!DNL Adobe Target] 的一份子，團隊持續努力改進 [!DNL Target] 使用者的使用者體驗，本次的版本重新整理了 [!DNL Target] UI 中的 [!UICONTROL Audiences] 和 [!UICONTROL Profile Scripts] 頁面。本次更新統一並標準化先前不一致的設計模式，同時加入了新的增強功能，例如：<ul><li>能夠同時選擇和刪除多個對象</li><li>重新整理的[對象建立器設計](/help/c-target/c-audiences/create-audience.md)</li><li>[!UICONTROL 對象]資料庫規則建立器中的排除規則支援</li><li>一個全新的「對象來源」篩選器，能讓您更快地發現對象</li><li>工作階段持續搜尋和篩選器選項</li><li>在工作區之間移動受眾的能力 [!DNL Target Premium] 客戶。</li></ul>如需詳細資訊，請參閱[對象](/help/c-target/target.md)。<br>**注釋**:此功能將在接下來的六週內向不同地區的客戶推出。 |
| [!UICONTROL 設定檔指令碼] UI 重新整理 | [!UICONTROL 設定檔指令碼]資料庫也進行了更新，包括一個重新整理的界面和多種生產力更新：<ul><li>能夠同時選擇和刪除多個設定檔指令碼</li><li>設定檔指令碼的新代碼編輯器</li><li>代碼編輯器中的語法醒目提示和錯誤檢查</li><li>透過鍵盤快捷鍵自動完成權杖 (mbox 或設定檔) 參數</li></ul>如需詳細資訊，請參閱[訪客設定檔](/help/c-target/c-visitor-profile/visitor-profile.md)。<br>**注釋**:此功能將在接下來的六週內向不同地區的客戶推出。 |

## [!DNL Target Standard/Premium] 22.1.1（2022年1月12日）

此版本包括錯誤修復和未來整合的必備功能。

## at.js 2.8.0 版 (2022 年 1 月 7 日)

[!DNL Target] at.js JavaScript 程式庫現在會收集功能使用情況和效能遙測資料。不會收集個人資料。可透過將 `targetGlobalSettings` 中的 `telemetryEnabled` 設定為 False，選擇退出此功能。如需詳細資訊，請參閱 [targetGlobalSettings 中的 telemetryEnabled](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#telemetry)。

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

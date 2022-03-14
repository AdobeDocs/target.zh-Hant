---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 資料庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 100%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也會隨附 Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明，以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## Target Standard/Premium 22.2.1 (2022 年 2 月 1 日)

此維護版本包含以下針對 Target Standard/Premium 22.1.2 版本中宣布的新[!UICONTROL 對象] UI 的修復和增強功能，該版本將在未來六週內向所有地區的客戶推出。此修正調整了在 [!DNL Adobe Target Standard/Premium] 中建立的對象功能。

* 修復了無法將從 [!DNL Adobe Experience Platform]、[!DNL Adobe Experience Cloud] 和 [!DNL Adobe Target Classic] 匯入的對象指派為報告對象的問題。(TGT-43140)
* 在「[!UICONTROL 對象]」清單中為從 [!DNL Adobe Experience Platform]、[!DNL Adobe Experience Cloud] 和 [!DNL Adobe Target Classic] 匯入的對象新增了[!UICONTROL 刪除]選項。還新增了大量刪除功能。(TGT-42914)

## at.js 2.8.1 版 (2022 年 1 月 28 日)

* 已修正以下問題：`pageLoad` 在[!UICONTROL 裝置上決策] (ODD) 混合執行模式中未對應到 target-global-mbox。
* 已修正 mbox 要求的分析詳細資料問題。
* 已升級 dev 相依項目，修正安全漏洞。

## [!DNL Target Standard/Premium] 22.1.2 (2022 年 1 月 26 日)

| 功能 | 詳細資料 |
| --- | --- |
| [!DNL Target] 中的 [!DNL Adobe Experience Platform] 對象 | 您現在可以在 [!DNL Target] 中消費和使用 [!DNL Adobe Experience Platform] 對象。[!DNL Target] 團隊、[!DNL Experience Platform] [!DNL Destinations] 團隊和 [!DNL Unified Profile Service] 團隊很高興地宣布推出「相同頁面/下一頁個人化」使用案例的正式版本。<br>使用在 [!DNL Adobe Experience Platform] 中建立的對象可提供更豐富的客戶資料，從而帶來更具影響力的個人化。[Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant){target=_blank} (RTCDP) 是以 [!DNL Adobe Experience Platform] 為基礎打造，可讓公司整合來自多個企業來源的已知和匿名資料，以建立客戶設定檔，其可用於跨所有管道和裝置即時提供個人化客戶體驗。<br>如需詳細資訊，請參閱&#x200B;*建立對象*&#x200B;中的[使用來自 Adobe Experience Platform 的對象](/help/main/c-target/c-audiences/audiences.md#aep)以及&#x200B;*目的地概觀*&#x200B;指南中的[相同頁面/下一頁個人化使用案例](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank}。 |
| [!UICONTROL Audiences] UI 重新整理 | 作為 [!DNL Adobe Target] 的一份子，團隊持續努力改進 [!DNL Target] 使用者的使用者體驗，本次的版本重新整理了 [!DNL Target] UI 中的 [!UICONTROL Audiences] 和 [!UICONTROL Profile Scripts] 頁面。本次更新統一並標準化先前不一致的設計模式，同時加入了新的增強功能，例如：<ul><li>能夠同時選擇和刪除多個對象</li><li>重新整理的[對象建立器設計](/help/main/c-target/c-audiences/create-audience.md)</li><li>[!UICONTROL 對象]資料庫規則建立器中的排除規則支援</li><li>一個全新的「對象來源」篩選器，能讓您更快地發現對象</li><li>工作階段持續搜尋和篩選器選項</li><li>為 [!DNL Target Premium] 客戶在工作區之間移動對象的功能。</li></ul>如需詳細資訊，請參閱[對象](/help/main/c-target/target.md)。<br>**請注意**：此功能將在未來八週內向不同區域的客戶推出。 |
| [!UICONTROL 設定檔指令碼] UI 重新整理 | [!UICONTROL 設定檔指令碼]資料庫也進行了更新，包括一個重新整理的界面和多種生產力更新：<ul><li>能夠同時選擇和刪除多個設定檔指令碼</li><li>設定檔指令碼的新代碼編輯器</li><li>代碼編輯器中的語法醒目提示和錯誤檢查</li><li>透過鍵盤快捷鍵自動完成權杖 (mbox 或設定檔) 參數</li></ul>如需詳細資訊，請參閱[訪客設定檔](/help/main/c-target/c-visitor-profile/visitor-profile.md)。<br>**請注意**：此功能將在未來八週內向不同區域的客戶推出。 |

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 資料庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些發行說明中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 舊版發行說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 發行說明 | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。如需詳細資訊，請參閱「<br>Creative Cloud 發行說明[」。](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant) |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html) |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 發行說明 - 發行前](/help/main/r-release-notes/target-release-notes.md)頁面。 |

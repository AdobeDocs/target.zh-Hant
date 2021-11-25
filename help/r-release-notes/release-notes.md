---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 資料庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些新功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: cc260620cf87feebcd4c43f45f05406ac845cf5b
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 100%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也會隨附 Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明，以及其他平台變更 (如適用)。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本，以避免您的網站出現任何潛在問題。如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

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
| 購物車型推薦 | 新增一系列演算法，以根據訪客購物車的內容提供推薦。<br>如需詳細資訊，請參閱[建立條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md)中的「購物車型」、[計劃和實作 Recommendations](/help/c-recommendations/plan-implement.md) 中的「購物車新增/購物車檢視/結帳頁面」和「排除訪客購物車中已有的項目」，以及[使推薦以推薦索引鍵為依據](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)中的「購物車型」。 |

## [!DNL Target Standard/Premium] 21.10.3 (2021 年 10 月 19 日)

此維護發行包含下列增強功能、修正和變更。

* 修正在按一下 [!DNL Target] 活動報告中的「[!UICONTROL 在 Analytics 中檢視]」按鈕後，無法開啟 [!DNL Analysis Workspace] [!UICONTROL A4T] 面板的問題。(TGT-42099 和 TGT-42100)
* 修正在使用[!UICONTROL 表單式體驗撰寫器]編輯 [!UICONTROL A/B 測試]和[!UICONTROL 體驗鎖定] (XT) 活動時，造成「[!UICONTROL 編輯設計]」按鈕不顯示的問題。(TGT-41980)
* 修正在建立新的 [!UICONTROL Recommendations] 活動時，「[!UICONTROL 相容]」核取方塊無法顯示在條件選取中的問題。(TGT-42053)
* 修正因為缺少 [!DNL Analytics] 權限而無法選取 [!DNL Analytics] 做為報告來源 (A4T) 時所顯示的不正確錯誤訊息。(TGT-41954)
* 實作多項協助工具修正，以改善 [!DNL Target] UI 鍵盤導覽。

## [!DNL Target Standard/Premium] 21.10.2 (2021 年 10 月 13 日)

透過[!DNL Adobe Experience Platform Web SDK]使用 [!DNL Target] [!UICONTROL Audiences] 時，新增了以下加強功能：

* 在 [!DNL Target]UI 的不同位置中，加入了警告圖示、彈出視窗和訊息，指示該對象已在來源刪除，並且不再可用於[!DNL Target]活動。

   下方插圖顯示了圖示、彈出視窗和訊息顯示的一些位置：

   * [!UICONTROL 活動]清單頁面

      ![在活動清單頁面上的來源訊息中刪除了對象](assets/deleted-at-source-audiences-list.png)

   * 活動[!UICONTROL 總覽]頁面：

      ![在總覽頁面上的來源訊息中刪除了對象](assets/deleted-at-source-overview.png)

   * 活動建立工作流程的[!UICONTROL 體驗]步驟：

      ![在[!UICONTROL 體驗]頁面](assets/deleted-at-source-experiences.png)上的來源訊息中刪除了對象

   * 活動建立工作流程的[!UICONTROL 定位]步驟：

      ![在[!UICONTROL 定位]頁面](assets/deleted-at-source-targeting.png)上的來源訊息中刪除了對象

   * 活動建立工作流程的[!UICONTROL 目標與設定]步驟：

      ![在[!UICONTROL 目標與設定]頁面](assets/deleted-at-source-goals-settings.png)上的來源訊息中刪除了對象

   * 對象細分 (活動建立工作流程[!UICONTROL 定位]步驟上的[!UICONTROL 取代對象])：

* 如果您嘗試使用「合併 Audiences」功能，並且在來源中刪除了其中一個對象，則會啟用[!UICONTROL 儲存]。

## [!DNL Target Standard/Premium]21.10.1 (2021 年 10 月 6 日)

此版本包含下列新功能：

| 功能 | 詳細資料 |
| --- | --- |
| [!UICONTROL Audiences] UI 重新整理 | 作為 [!DNL Adobe Target] 的一份子，團隊持續努力改進 [!DNL Target] 使用者的使用者體驗，本次的版本重新整理了 [!DNL Target] UI 中的 [!UICONTROL Audiences] 和 [!UICONTROL Profile Scripts] 頁面。本次更新統一並標準化先前不一致的設計模式，同時加入了新的增強功能，例如：<ul><li>能夠同時選擇和刪除多個對象</li><li>重新整理的[對象建立器設計](/help/c-target/c-audiences/create-audience.md)</li><li>[!UICONTROL 對象]資料庫規則建立器中的排除規則支援</li><li>一個全新的「對象來源」篩選器，能讓您更快地發現對象</li><li>工作階段持續搜尋和篩選器選項</li></ul>如需詳細資訊，請參閱[對象](/help/c-target/target.md)。<br>**注意**：新的 [!UICONTROL Audiences] UI 僅供特定客戶使用。自 2022 年 1 月起，此更新將逐步向所有客戶推出。 |
| [!UICONTROL 設定檔指令碼] UI 重新整理 | [!UICONTROL 設定檔指令碼]資料庫也進行了更新，包括一個重新整理的界面和多種生產力更新：<ul><li>能夠同時選擇和刪除多個設定檔指令碼</li><li>設定檔指令碼的新代碼編輯器</li><li>代碼編輯器中的語法醒目提示和錯誤檢查</li><li>透過鍵盤快捷鍵自動完成權杖 (mbox 或設定檔) 參數</li></ul>如需詳細資訊，請參閱[訪客設定檔](/help/c-target/c-visitor-profile/visitor-profile.md)。<br>**注意**：新的[!UICONTROL 設定檔指令碼] UI 僅供特定客戶使用。自 2022 年 1 月起，此更新將逐步向所有客戶推出。 |
| ![Premium badge](/help/assets/premium.png)建立與編輯 Recommendations 標準 | [!UICONTROL Recommendations 標準]的建立與編輯工作流程已經過簡化，以精簡選擇正確的推薦演算法和設定以達成目標的過程。<br>如需詳細資訊，請參閱[建立準則](/help/c-recommendations/c-algorithms/create-new-algorithm.md)。 |
| ![進階徽章](/help/assets/premium.png)建議回顧視窗和演算法更新率改進 | 您現在可以執行具有 6 小時回顧視窗的「最多觀看次數」和「最暢銷」演算法，擷取近期最受歡迎的內容。選擇 6 小時回顧視窗後，您的推薦結果在一天之中每 3-6 小時會更新一次。<br>如需詳細資訊，請參閱&#x200B;*建立準則*&#x200B;中的[資料來源](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source)。 |

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

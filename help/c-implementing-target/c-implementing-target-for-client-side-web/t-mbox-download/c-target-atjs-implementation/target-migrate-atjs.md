---
keywords: Target;at.js;移轉至 at.js;整備;稽核 at.js;整合 at.js
description: 瞭解如何移轉至at.js，這是專為一般Web實作和單頁應用程式(SPA)所設計的全新Adobe實作庫 [!DNL Target] 。
title: 如何從 mbox.js 移轉至 at.js
feature: at.js
role: Developer
exl-id: d612ca74-521b-437e-aa9a-b1065e460d45
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 92%

---

# 如何從 mbox.js 移轉至 at.js

在 [!DNL Adobe Target] 中從 mbox.js 移轉至 at.js 是簡單直接的程序。

使用下列步驟來從 [!DNL mbox.js] 移轉至 [!DNL at.js]，並檢查您的移轉:

1. 判斷您組織的[瀏覽器支援](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)需求。
1. 檢查您網站目前的 [!DNL mbox.js] 實施，以瞭解是否有 [!DNL at.js] 不支援的功能。

   稽核您的實施時，請查看下列:

   **您目前使用什麼類型的 mbox?**

   | 類型 | 詳細資料 |
   |--- |--- |
   | 自動建立的全域 mbox | 自動建立的全域 mbox 是在您的網站上的唯一一行 Target 代碼為 mbox.js 檔案時建立。該檔案會自動產生 mbox 呼叫。 |
   | 全域的空白 mboxCreate | 建議您切換為自動建立的全域 mbox。 |
   | 包裝 mboxCreate | 只要您的 `mboxCreate()` 前端有加上 `<div class="mboxDefault"></div>`，移轉程序應該會相當簡單。 |
   | mboxUpdate | 移轉應該簡單的，當您`mboxUpdate()` 需搭配 `mboxDefine()` 或 `mboxCreate()` 使用。`mboxUpdate()` 不會更新自動建立的全域 mbox 或原來由 `getOffer()` 建立的 mbox。在這類情況下，移轉至 at.js 時，應使用 `getOffer()` 和 `applyOffer()` 的組合來取代 `mboxUpdate()`。 |
   | 自訂點擊追蹤 mbox，包括 mboxTrack | 建議您更新您的代碼以使用`trackEvent()`。 |

   >[!NOTE]
   >
   >如需前文表格中所提及各種函數的詳細資訊，請參閱 [at.js 函數](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。

   **您對您的 [!DNL mbox.js] 檔案有任何自訂項目嗎?**

   * mboxParameters()
   * mboxSupported()
   * mboxCookieDomain()
   * 額外 Javascript
   * 其他位置

   不支援大部分的 [mbox.js 物件和方法](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) (例如 `mbox`、`mboxCurrent`、`mboxFactoryDefault`、`mboxFactories`)。可能有替代方法能完成您嘗試的動作。

   **您在您的任何網頁上是否有 [!DNL mbox.js]?**

   您無法在相同網頁上同時使用 [!DNL at.js] 和[!DNL mbox.js]。不過，您可以在相同網站的兩個不同頁面上使用 JavaScript 資料庫。

   mbox Cookie 是 Adobe 拼接頁面與頁面間訪客的主要方式。隨著您的 QA 程序，您應該確認會保留 Cookie，並且在訪客使用 [!DNL at.js] 和使用 [!DNL mbox.js] 的這些頁面間往返時可正確讀取。確定相同的 `mboxPC` 和 `mboxSession` 值會傳入 mbox 呼叫，而無論訪客先登陸所在網站的區段 ([!DNL at.js] 或 [!DNL mbox.js])，以及原始設定 Cookie 的區段為何。如果您在您的實施中使用第三方 Cookie，請確保那些值在您瀏覽網站時保持相同。

   **您將 [!DNL Target] 與任何其他 Adobe 解決方案整合嗎?**

   * 目標分析 (A4T)
   * Analytics (舊版整合)
   * AAM (後端)
   * AAM (舊版前端)
   * AEM
   * Data Workbench

   [!DNL at.js] 不支援部分舊版整合。如需詳細資訊，請參閱[整合](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)頁面。

   **您將 [!DNL Target] 與任何第三方工具整合嗎?**

   * 其他 Analytics 工具
   * 其他 DMP
   * Demandbase
   * Clicktale
   * 其他

   這些整合可能需要經過調整，才能與 [!DNL at.js] 搭配使用。如需詳細資訊，請參閱[整合](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)頁面。

   **您有使用標記管理程式嗎?**

   * Adobe Experience Platform Launch
   * Ensighten
   * Tealium
   * Signal/BrightTag

   如需詳細資訊，請參閱 [at.js 整合](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)。

   >[!NOTE]
   >
   >如果您目前未使用標籤管理程式來部署 [!DNL Target]，現在不妨考慮使用。
   >
   >[!DNL Platform Launch] 是來自的新一代標籤管理平台， [!DNL Adobe] 且是實作的首選方法 [!DNL Adobe Target]。[!DNL Platform Launch] 為客戶提供簡單的方式，來部署及管理提供相關客戶體驗所需的分析、行銷和廣告標籤。
   >
   >如需詳細資訊，請參閱[Implement [!DNL Target] using [!DNL Adobe Platform Launch]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。

1. 確認所有目前的活動和整合皆如預期般運作。

   這裡是測試時您可以進行的項目，以確認 [!DNL at.js] 可如預期般運作:

   * 確定您目前的所有活動可與新的 JavaScript 資料庫搭配使用。
   * 確認所有[整合項目](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)和[外掛程式](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF)均如預期般運作。
   * 確定您瞭解可透過 [!DNL at.js] 進行[除錯](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F)的方法。

**移轉至 at.js 可能發生的問題** 某些客戶在移轉至 at.js 後報告了下列問題:

* 有些 VEC 活動建置在具有 [!DNL mbox.js] 的頁面上，這些活動可能需要更新才能與 [!DNL at.js] 搭配使用。

   此問題最常發生在未在 HTML 元素中使用許多 id 或 class 屬性的網站上。您可以載入頁面並判斷體驗是否正如預期般傳送，藉此確認您是否遇到此問題，方法是使用 `?mboxDebug=true` 載入頁面並檢閱主控台陳述式。

   ![](assets/mboxdebug.png)
在這些情況下，元素選取器可能的開始可能會是

   ```
   HTML > BODY > DIV:nth-of-type(2)
   ```

   並且建置時會預期 [!DNL mbox.js] 已在頁面上方新增額外的 `<div>` 元素。因為 [!DNL at.js] 未在頁面上方新增 `<div>` 元素，此選取器將不再能與 [!DNL at.js] 搭配使用。

   在 VEC 中的 URL 上使用 [!DNL at.js] 重新建立活動，或在 VEC 中使用&#x200B;**[!UICONTROL 「&lt;/> 代碼」]**>**[!UICONTROL 「修改」]**&#x200B;選項手動更新選取器，即可解決此問題。

   若要補救此問題，您應該在 BODY 之後的第一個 DIV 元素中，從第 n 個輸入數字減 1。在以上範例中，經過編輯的代碼會是:

   ```
   HTML > BODY > DIV:nth-of-type(1)
   ```

   如需如何使用代碼編輯器來執行此動作的相關資訊，請參閱[代碼編輯器](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5)。

* 因為所有 mbox 現在非同步，它們將不會封鎖頁面呈現或在其觸發的訂單中傳回。如需詳細資訊，請參閱以下主題中的「資料收集」: [at.js 限制](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#concept_FA99E4D6EC274552BF45E01AFB76CCAE)。

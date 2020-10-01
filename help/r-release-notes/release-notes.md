---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 這些版本說明提供關於每個 Adobe Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
title: 'Adobe Target 版本說明 (最新) '
feature: release notes
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 1397891d4451d9e66a25e018e6bd7078e70cfd3f
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 23%

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

>[!IMPORTANT]
>
>* **Adobe再次在Gartner個人化引擎魔力像限中獲評為領導者**:在2020年第三年度的Gartner個人化引擎魔力像限報告中，Adobe再次獲評為領導者。 Gartner個人化引擎魔力像限評估了15個標準的供應商，這些標準分為兩類：願景的完整性與執行能力。 [在Adobe部落格上閱讀相關資訊](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.js移除**:自2021年1月18日起，Adobe Target將不再支援mbox.js程式庫。 在2021年1月18日後，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 如需詳細資訊，請 [參閱At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[和Adobe Target技能產生器：開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。
   >
   >
* **目標公告**:請參閱Target公告頁面，以取得近期活動的相關資訊，包括Target Skill Builder研討會、開發人員聊天、網路研討會和Target Coffee Break研討會。 如需詳細資訊，請參閱 [Target公告](/help/r-release-notes/target-announcements.md)。


括號內的問題編號供 [!DNL Adobe] 內部使用。

## Target Standard/Premium 20.9.1 (2020 年 9 月 30 日)

此維護髮行包含下列增強功能、修正和變更：

* 已改善僅限鍵盤使用者的導覽和功能。 (TGT-34487、TGT-34516、TGT-34517、TGT-34514)
* 在UI中新增標籤，以協助使用者使用輔助技術。 (TGT-34500、TGT-34501、TGT-34502、TGT-24504)
* 改善UI中影像和文字的文字和色彩對比。 (TGT-34513)

## Target Standard/Premium 20.8.3 (2020 年 9 月 15 日)

| 功能 | 詳細資料 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) Analytics for Target(A4T)支援自動定位活動 | [!UICONTROL Auto-Target活動] ，現在支援 [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)。<br>此整合可讓您使用 [!UICONTROL Auto-Target] ensemble機器學習演算法，根據每位訪客的描述檔、行為和上下文來選擇最佳體驗。<br>如果您已實作 [A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) ，以便與A/B測試和體驗定位活動搭配使用，一切就緒！<br>如需詳細資訊，請參 [閱「活動建立」中「自動分配」和「自動定位」活動的Analytics for Target(A4T)](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)*支援*。 |

## Target Standard/Premium 20.8.2 (2020 年 9 月 10 日)

| 功能 | 詳細資料 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) Control recommendations slots within criteria sequences | 「准則序列」現在可讓您控制每個建議准則佔用的槽數，讓您混合和比對不同類型的項目或不同演算法邏輯。<br>如需詳 [細資訊，請參閱](/help/c-recommendations/c-algorithms/create-criteria-sequence.md#sequence) 「建立准則序列」。 |

## Target Standard/Premium 20.8.1 (2020 年 9 月 2 日)

此發行包含下列增強功能、修正和變更：

* 修正在切換組織後載入新的「管理」頁面時， [!UICONTROL 顯示錯誤] 的問題。 (TGT-37730)
* 修正導致「管理>實作」頁面上顯示錯誤用戶端 [!UICONTROL 代碼的顯示問題] 。 (TGT-37849)
* 修正在成功載入VEC後，使用者有時無法在 [!UICONTROL Visual Experience Composer] (VEC)中使用編輯功能的問題。 (TGT-37162)
* 修正即使已安裝VEC Helper擴充功能，仍無法在VEC和Enhanced Experience Composer(EEC)中載入頁面的問題。 這是由於Google Chrome 80+的變更。 下載更 [新的VEC Helper擴充功能](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)。 (TGT-37893)
* 修正使用者在切換組織後，有時無法從「管理>實作」頁 [!UICONTROL 面下載at.js的問題] 。 (TGT-37668)
* 現在載入時會停用at.js下載按鈕，以防止使用者 [!DNL Target] 多次按一下下載按鈕時傳送多個請求。 (TGT-37633)
* 修正「體驗 [!UICONTROL 定位] (XT)」活動中，導致體驗在較長時間內顯示「擷取結果」的問題。 (TGT-37684)
* 已改善僅限鍵盤使用者的導覽和功能。 (TGT-34479 和 TGT-34473)
* 在UI中新增標籤，以協助使用者使用輔助技術。 (TGT-34480)
* 改進刪除活動中目前使用的行動檢視區時的錯誤訊息。 錯誤訊息現在會顯示：「此視區目前與一或多個活動相關聯。 您必須先從這些活動中移除視區，才能刪除它。」 (TGT-37030)
* 在VEC中新增支援，可允許在符合頁面中多個元素的css選擇器上追蹤點按。 (TGT-37323)
* 修正某些使用者無法顯示「活動」清單 [!UICONTROL 的問] 題。 顯示以下錯誤消息：&quot;無法擷取URL建議。&quot; 在Adobe後端系統中，使用其FirstName(FirstName/r/n)中傳回歸位的使用者發生錯誤。 (TGT-37330)
* 修正當工作區名稱(在適用於企業的 [!UICONTROL Adobe Admin Console中指定])包含縮寫符號時，使用者無法顯示「活動」頁面的問題。 (TGT-37709)
* 修正「自動  分配」活動中，選取最佳化和轉換量度時，即使已指定報表套裝，錯誤訊息仍會錯誤告知使用者選取報表套裝的問題。 (TGT-37689)
* 修正導覽至「定位」頁面後，有時造 [!UICONTROL 成「目標與設定」頁面上的量度空白的] 問題  。 (TGT-37691)
* 修正導致准則上次修改的值不正確的 [!DNL Recommendations] 問題。 (TGT-37666)
* 修正mbox ID顯示在「mbox」下拉式清單中，而非mbox名稱的問題。 (TGT-37739)

## 其他發行說明和版本詳細資訊

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明——目標伺服器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 與Adobe Target伺服器端API相關的發行說明。 |
| [發行說明- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 與Adobe Target的Node.js SDK相關的發行說明。 |
| [發行說明——目標Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 與Adobe Target Java SDK相關的發行說明。 |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobe Target at.js JavaScript程式庫各版本變更的詳細資訊。 |
| [mbox.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 本頁面顯示每個 mbox.js 版本的變更。<br>請注意，mbox.js程式庫已不再開發。 所有客戶應該從 mbox.js 移轉至 at.js。 |

## 文件變更、過去的版本說明和 Experience Cloud 版本說明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視在版本說明中可能未涵蓋的手冊更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版版本說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本說明](../r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 版本說明 | 檢視 Adobe Experience Cloud 解決方案的最新版本說明。<br>如需詳細資訊，請參 [閱Experience Cloud發行說明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先順序產品更新清單 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |

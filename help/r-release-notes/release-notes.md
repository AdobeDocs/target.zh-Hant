---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 這些版本說明提供關於每個 Adobe Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
title: 'Adobe Target 版本說明 (最新) '
feature: release notes
translation-type: tm+mt
source-git-commit: f4091506538cd4719302227b88fa11e9d4ae93a6
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 28%

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

>[!IMPORTANT]
>
>* **mbox.js生命週期結束**:自2021年1月18日起，Adobe Target將不再支援mbox.js程式庫。在2021年1月18日後，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 如需詳細資訊，請參閱[At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[Adobe Target技能產生器：開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。
   >
   >
* **目標公告**:請參閱Target公告頁面，以取得近期活動的相關資訊，包括Target Skill Builder研討會、開發人員聊天、網路研討會和Target Coffee Break研討會。如需詳細資訊，請參閱[Target公告](/help/r-release-notes/target-announcements.md)。


括號內的問題編號供 [!DNL Adobe] 內部使用。

## at.js 2.3.3（2020年11月13日）

此版本的at.js是維護髮行，包含下列修正：

* 修正與mbox點按追蹤和A4T相關的問題。

## Target Standard/Premium 20.10.1 (2020 年 10 月 27 日)

此版本包含下列新功能：

| 功能 | 詳細資料 |
| --- | --- |
| [裝置上決策](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) | 裝置上決策可讓行銷人員和產品開發人員在使用者的裝置內、跨通道、幾乎零延遲的情況下，提供實驗和機器學習驅動的個人化。<br>速度與效能攸關——在客戶見解與使用者滿意度方面。<br>裝置上決策可讓您將A/B測試與體驗定位(XT)活動類型中的關鍵個人化和實驗指示編譯為「最佳化工件：」 JSON物件，這些物件會透過CDN載入到客戶裝置上。而且，由於裝置上的決策功能會以原生方式與[!DNL Adobe Experience Cloud]產品連接，[!DNL Target]使用者可獲得快速分析和更快速的體驗互動。<br>如需詳細資訊，請參閱*[裝置上決策](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md)。 |

此發行包含下列增強功能、修正和變更：

* 修正[!UICONTROL 平均提升度信賴區間]和[!UICONTROL 信賴區間]無法顯示在[!UICONTROL 總計]列之[!DNL Auto-Target]報表中的問題。 所有個別體驗的度量都會正確顯示。 (TGT-37301)
* 修正從9月15日下午2:30開始影響[!DNL Adobe Target Premium]使用者[!UICONTROL  Auto-Target]報表的問題。(PDT)至10月6日，上午九點二刻(PDT)。 檢視受影響轉換度量的報表時（使用「[!UICONTROL 已檢視頁面]」或「[!UICONTROL 已點按mbox]」選項設定），轉換率報告不正確。 目前沒有已知的傳送問題。 有關如何重新同步和更正報告的資訊，請參閱&#x200B;**&lt;a4/>&lt;已解決問題&#x200B;**&#x200B;中的[自動目標報告](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics)。
* 在[!UICONTROL 目錄搜尋]表格中新增可選[!UICONTROL 上次更新日期]欄，以及[!UICONTROL 上次更新日期]篩選。 此增強功能可節省時間和精力，因為您不需要開啟每個個別項目來查看上次更新的時間，而且您可以依上次更新項目的日期進行篩選。

   ![「上次更新於」欄和篩選器圖示](/help/r-release-notes/assets/column-and-filter.png)

* 已進行更新，以協助Target UI符合[Web內容協助工具准則](https://www.w3.org/WAI/standards-guidelines/wcag/) 2.0 Level A和AA Success Criteria(WCAG 2.0 AA)。 (TGT-34384 和 TGT-24679)
* 對內容安全性政策(CSP)做了改進。 (TGT-37035)
* 引入一種方式，指定用戶端程式碼為使用CNAME的客戶的參數。 (TNT-38571)
* [!DNL Adobe Experience Cloud] 文檔正在移至 [!DNL Experience League]。在10月期間，所有發行說明、文章、影片和教學課程都將從目前位於`docs.adobe.com`的位置移至[!DNL Experience League]。 此舉可確保從單一位置提供所有學習、自助、啟用和社群內容。 發生此變更時，您不需要執行任何動作，因為所有連結都會重新導向至[!DNL Experience League]。 當切換開始時，我們會更新版本注意事項。

## 其他發行說明和版本詳細資訊

| 資源 | 詳細資料 |
|--- |--- |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 資料庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的版本說明和 Experience Cloud 版本說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視在版本說明中可能未涵蓋的手冊更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版版本說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本說明](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 版本說明 | 檢視 Adobe Experience Cloud 解決方案的最新版本說明。<br>如需詳細資訊，請參 [閱Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)。 |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先順序產品更新清單 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |

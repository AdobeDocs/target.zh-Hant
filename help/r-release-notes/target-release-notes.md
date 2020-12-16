---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 提供最新或即將發行的DNL Adobe Target版本功能、增強功能和修正資訊的發行說明。
title: Adobe Target搶鮮版注意事項
feature: null
translation-type: tm+mt
source-git-commit: f4091506538cd4719302227b88fa11e9d4ae93a6
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 10%

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新: 2020 年 10 月 27 日**

若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>* **Adobe再次在Gartner個人化引擎魔力像限中獲評為領導者**:在2020年第三年度的Gartner個人化引擎魔力像限報告中，Adobe再次獲評為領導者。Gartner個人化引擎魔力像限評估了15個標準的供應商，這些標準分為兩類：願景的完整性與執行能力。 [在Adobe部落格上閱讀相關資訊](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.js生命週期結束**:自2021年1月18日起，Adobe Target將不再支援mbox.js程式庫。在2021年1月18日後，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 如需詳細資訊，請參閱[At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)和[Adobe Target技能產生器：開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。
   >
   >
* **目標公告**:請參閱Target公告頁面，以取得近期活動的相關資訊，包括Target Skill Builder研討會、開發人員聊天、網路研討會和Target Coffee Break研討會。如需詳細資訊，請參閱[Target公告](/help/r-release-notes/target-announcements.md)。


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

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 提供最新或即將發行的DNL Adobe Target版本功能、增強功能和修正資訊的發行說明。
title: Adobe Target搶鮮版注意事項
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: f531dd591455b90a8e4e937bdbc0a10f70ff089a
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 10%

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新: 2020 年 10 月 15 日**

若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>* **Adobe再次在Gartner個人化引擎魔力像限中獲評為領導者**:在2020年第三年度的Gartner個人化引擎魔力像限報告中，Adobe再次獲評為領導者。 Gartner個人化引擎魔力像限評估了15個標準的供應商，這些標準分為兩類：願景的完整性與執行能力。 [在Adobe部落格上閱讀相關資訊](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.js生命週期結束**:自2021年1月18日起，Adobe Target將不再支援mbox.js程式庫。 在2021年1月18日後，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 如需詳細資訊，請 [參閱At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[和Adobe Target技能產生器：開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。
   >
   >
* **目標公告**:請參閱Target公告頁面，以取得近期活動的相關資訊，包括Target Skill Builder研討會、開發人員聊天、網路研討會和Target Coffee Break研討會。 如需詳細資訊，請參閱 [Target公告](/help/r-release-notes/target-announcements.md)。


## Target Standard/Premium 20.10.1 (2020 年 10 月 27 日)

此版本包含下列新功能：

| 功能 | 詳細資料 |
| --- | --- |
| 裝置上決策 | 「裝置上決策」可讓行銷人員和產品開發人員在使用者的裝置內、跨通道，以接近零的延遲，提供實驗和機器學習驅動的個人化。<br>速度與效能攸關——在客戶見解與使用者滿意度方面。 裝置上決策功能可讓行銷人員（現在也是產品開發人員）直接在使用者裝置內測試和最佳化體驗，將即時、情境式體驗的決策和載入時間縮短至幾乎為零。<br>裝置上決策可讓您將所有個人化和實驗指示編譯到「最佳化工件」上，這些工件會載入到客戶裝置上。 這些零延遲的工件可讓行銷人員一對一個人化、行為重新鎖定，以及即時產品和內容建議，同時讓開發人員和產品擁有者直接存取程式碼，以測試使用者體驗，並鎖定和階段產品發佈，即時進行調整。 而且，由於裝置上決策會以原生方式與產品連 [!DNL Adobe Experience Cloud] 接， [!DNL Target] 所以使用者可以快速分析並加速體驗反覆。<br>**立即註冊參加即時網路研討會。** 與Adobe Target產品專家一起討論如何在裝置上將關鍵體驗最佳化決策移至本機執行，而無延遲，為客戶開啟令人振奮的新使用案例，同時提升網站效能。<ul><li>2020年11月10日</li><li>上午10點PT /下午12點CT /下午1點ET</li><li>[在此處註冊](https://www.adobeeventsonline.com/Target/2020/OnDeviceDecisions/invite.html)</li></ul> |

此發行包含下列增強功能、修正和變更：

* 修正「平均提升度信賴 [!UICONTROL 區間」和「信賴度] 」無法顯示在「總計 [!UICONTROL 」列報] 表中的問 [!DNL Auto-Target] 題  。 所有個別體驗的度量都會正確顯示。 (TGT-37301)
* 修正從9月15 [!DNL Adobe Target Premium] 日下午2  :30開始影響使用者「自動定位」報表的問題。(PDT)至10月6日，上午九點二刻(PDT)。 檢視受影響轉換度量的報表時(使用「已檢視頁面[!UICONTROL 」或「已點按mbox]」選項設定)，轉換率報告不正確。 目前沒有已知的傳送問題。 如需如何重新同步和更正報表的詳細資訊，請參閱「已知問題中已解決的問題」 [(Resolved issues](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) in *Known issues)和「已解決的問題」(Resolved issues)下的「自動定位」(* Auto-Target)報表 **。
* 在「目錄搜尋」 [!UICONTROL 表格中新增可選的「上次更新的At] 」欄和「上次更新的At  」篩選。 此增強功能可節省時間和精力，因為您不需要開啟每個個別項目來查看上次更新的時間，而且您可以依上次更新項目的日期進行篩選。

   ![「上次更新於」欄和篩選器圖示](/help/r-release-notes/assets/column-and-filter.png)

* 已進行更新，以協助Target UI符合 [Web內容協助工具方針](https://www.w3.org/WAI/standards-guidelines/wcag/) 2.0 A級和AA成功准則(WCAG 2.0 AA)。 (TGT-34384 和 TGT-24679)
* 對內容安全性政策(CSP)做了改進。 (TGT-37035)
* 引入一種方式，指定用戶端程式碼為使用CNAME的客戶的參數。 (TNT-38571)


## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

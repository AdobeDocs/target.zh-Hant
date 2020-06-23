---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 提供最新或即將發行的DNL Adobe Target版本功能、增強功能和修正資訊的發行說明。
title: Adobe Target搶鮮版注意事項
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 058828bbf3f13704d9e941563b7dab5259be6809
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 19%

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新: 2020 年 6 月 23 日**

若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!NOTE]
>
>* **mbox.js淘汰**: 自2020年8月30日起，Adobe Target將不再支援mbox.js程式庫。 在2020年8月30日發佈後，從mbox.js進行的所有呼叫都將失敗，並影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 如需詳細資訊，請 [參閱At.js的運作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)[和Adobe Target技能產生器： 開發人員聊天，將Adobe Target的mbox.js移轉至at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點外，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。
   >
   >
* **目標公告**: 請參閱Target公告頁面，以取得近期活動的相關資訊，包括Target Skill Builder研討會、開發人員聊天、網路研討會和Target Coffee Break研討會。 如需詳細資訊，請參閱 [Target公告](/help/r-release-notes/target-announcements.md)。


## Target Standard/Premium 20.6.1（2020年7月，確切日期待定）

此版本包含下列增強功能:

### Analytics for Target(A4T)支援 [!UICONTROL Auto-Target活動]

[!UICONTROL Auto-Target活動] ，現在支援 [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)。

此整合使用進階的機器學習功能，從多個高效能行銷人員定義的體驗中選擇，以個人化內容並推動轉化。 自動鎖定目標會根據訪客的個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供每位訪客量身打造的最佳體驗。

如果您已實作 [A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) ，以便與A/B測試活動搭配使用，一切就緒！

### [!UICONTROL 管理區] UI重新整理

我們已更新「管 [!UICONTROL 理] 」區段(先前稱為 [!UICONTROL 「管理員]」)及其頁面，讓您的工作流程更輕鬆、更有效率。

重點包括：

* **[!UICONTROL 「視覺體驗撰寫器]」頁面&#x200B;**: 這個新頁面(「管**[!UICONTROL 理&#x200B;]**>視覺**[!UICONTROL 體驗撰寫器&#x200B;]**」)可讓您：

   * 設定VEC的一般設定(指定預設URL、啟用 [!UICONTROL Enhanced Experience Composer]、載入混合內容，以及在活動流程圖中產生體驗快照)
   * 設定行動檢視區
   * 設定CSS選擇器

* **[!UICONTROL 報告頁]**: 這個新頁面(「管**[!UICONTROL 理&#x200B;]**>報表**[!UICONTROL 」)可讓您設定一般設定，以用於套用&#x200B;]**至整個帳戶的報表[!DNL Target][!DNL Target]中。

   可用的設定包括：

   * 用於 [!DNL Adobe Experience Cloud] 報告的解決方案
   * 用於報告的時區
   * 用於報告的貨幣
   * 要排除在報告之外的IP位址
   * 是否在報告中顯示預估的收入提升
   * 是否啟用細粒度的優先順序

* 上一頁 [!UICONTROL 的「主機] 」已分割為兩個新頁面：

   * [!UICONTROL 主機]
   * [!UICONTROL 環境]

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

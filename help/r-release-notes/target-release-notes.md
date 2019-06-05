---
description: 以下版本說明提供最新或即將發行之 Target 版本的功能、增強功能、修正和已知問題等資訊。
keywords: 版本說明
seo-description: 以下版本說明提供最新或即將發行之 Adobe Target 版本的功能、增強功能、修正和已知問題等資訊。
seo-title: Target 版本說明 (發行前)
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: bac43f0907b083f416aaf72fca0eb4c6d4b83a7e

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**最近更新: 2019 年 5 月 28 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會有所變更。若要檢視關於最新版本的資訊，請參閱 [Target 發行說明](release-notes.md)。視發行的時間點而定，這些頁面上的資訊可能相同或有所不同。

## Target Standard/Premium 19.6.1 (2019 年 6 月 25 日) {#tgt-19-6-1}

| 功能/增強功能 | 說明 |
| --- | --- |
| 可視化體驗撰寫器 (VEC) | <ul><li>您現在可以使用CMS中的 [!DNL Styles > Background] 功能表，變更選取元素的背景影象和顏色。(TGT-15001)</li><li>當您按一下CMS中的頁面元素時，功能表會顯示該元素類型可用的選項。當您按一下影像後，會顯示 [!DNL Replace With]兩個新選項： [!DNL HTML] 和 [體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)。<br> 使用HTML取代影像可讓您完全控制元素，而不需選取父元素來存取HTML選項。體驗片段可讓您快速插入在Target定位中建立的Adobe Experience Manager(AEM)元素。(TGT-34097)</li></ul> |
| 單頁應用程式(SPA) Visual Experience Composer(CMS) | <ul><li>新的引導工作流程可協助您瞭解頁面遞送規則設定如何設定，以便在單一頁面應用程式中成功執行和執行活動。(TGT-33718)</li><li>您現在可以使用SPA CMS定義修改，然後將修改複製到您的單一頁面應用程式中的其他檢視中。(TGT-33882)</li><li>我們改善了在SPA CMS內設定點按追蹤的程序。<br>選取要用於點擊追蹤的元素時，所有可用元素的名稱會顯示在右側的「修改」面板中，讓您快速且輕鬆地選取所要的元素。<br>三部分引導活動工作流程 [!DNL Goals & Settings] 的頁面顯示代表點選追蹤元素數目的數字。您可以將滑鼠指標暫留在此數目上，以查看所有選取元素的名稱。(TGT-33878) </li></ul> |
| Mobile Visual Experience Composer(CMS) | <ul><li>您現在可以針對多種版本的行動應用程式編寫活動，如此當版本非常類似，而且您不需要大幅變更應用程式的UI時，就能為您節省時間和精力。(TGT-34231)</li></ul> |
| ![Premium BadgeAutomated](/help/assets/premium.png)<br>Personalization(AP)和Auto-Target活動：體驗 | <ul><li>建立 AP 或自動鎖定目標活動時，您可以選取要用來作為控制的體驗。此功能可讓您根據活動中設定的流量配置百分比，將整個控制流量傳送至特定體驗。接著，您可以根據控制體驗評估個人化傳送的效能。(TGT-32801 和 TGT-26572)</li></ul> |

### 增強功能、修正和變更

* 該 <BODY> 標記現在會顯示在DOM路徑中，當您按一下頁面上的元素時，會顯示在CMS底部，讓您在 <BODY> 標記之前是否有宣告。(TGT-33736)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到有關 Target 和其他 Adobe Experience Cloud 解決方案的未來產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

---
description: 以下版本說明提供最新或即將發行之 Target 版本的功能、增強功能、修正和已知問題等資訊。
keywords: 版本說明
seo-description: 以下版本說明提供最新或即將發行之 Adobe Target 版本的功能、增強功能、修正和已知問題等資訊。
seo-title: Adobe Target發行說明(搶鮮版)
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: e50ae8c95774716ea484f02b276b2d66cb228364

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新: 2019 年 6 月 6 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會變更，恕不另行通知。若要檢視關於最新版本的資訊，請參閱 [Target 發行說明](release-notes.md)。視發行的時間點而定，這些頁面上的資訊可能相同或有所不同。
>
>括號中的問題編號是供內部 [!DNL Adobe] 使用。

## Target Standard/Premium 19.6.1 (2019 年 6 月 25 日) {#tgt-19-6-1}

此版本包含下列新功能和增強功能:

### 可視化體驗撰寫器 (VEC)

* **新的CMS功能表選項**：當您按一下CMS中的頁面元素時，功能表會顯示該元素類型可用的選項。

   * **樣式&gt;背景**：您現在可以使用 [!UICONTROL 「樣式&gt;背景] 」選項來變更選取元素的背景影象和顏色。(TGT-15001)

   * **[!UICONTROL 取代為&gt; HTML]並[!UICONTROL 取代為&gt;體驗片段]**：當您按一下影像然後按一下 [!UICONTROL 「取代為」]時，會顯示兩個新選項：

      * **HTML**：您可以使用HTML取代影像，讓您完全控制元素，而不需選取父元素來存取HTML選項。
      * **體驗片段**：您可以使用Adobe Experience Manager(AEM) [體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md) 取代影像，以便快速插入Target活動中AEM中建立的元素。(TGT-34097)

* **點擊追蹤改進**：我們改善了在CMS和單一頁面應用程式(SPA) CMS中設定點按追蹤的程序。

   * 選取要用於點擊追蹤的元素時，所有可用元素的名稱會顯示在右側的「修改」面板中，讓您快速且輕鬆地選取所要的元素。
   * 三部分引導活動工作流程的 [!UICONTROL 「目標與設定] 」頁面顯示代表點選追蹤元素數目的數字。您可以將滑鼠指標暫留在此數目上，以查看所有選取元素的名稱。(TGT-33878)

### SPA CMS

* **引導式工作流程**：新的引導工作流程可協助您瞭解頁面遞送規則設定如何設定，以便在單一頁面應用程式中成功執行和執行活動。(TGT-33718)

* **複製修改**：您現在可以使用SPA CMS定義修改，然後將修改複製到您的單一頁面應用程式中的其他檢視中。(TGT-33882)

### 行動CMS

* **多個應用程式版本**：您現在可以為行動應用程式的多個版本編寫活動。如此可為您節省時間和精力，當版本類似時，您就不需要大幅變更應用程式的UI。(TGT-34231)

### ![Premium徽章](/help/assets/premium.png) 自動個人化(AP)與自動目標

* **特定體驗作為控制**：您可以選取在建立AP或自動Target活動時做為控制項的體驗。此功能可讓您根據活動中設定的流量分配百分比，將整個控制流量路由至特定體驗。然後，您可以評估個人化流量的績效報告，以控制該一個體驗的流量。目前的控制選項(隨機提供體驗)將繼續可用。(TGT-32801 和 TGT-26572)

### 其他增強功能、修正和變更

* `<BODY>` 標籤現在會顯示在DOM路徑中，當您按一下頁面上的元素時，會顯示在CMS底部，讓您對 `<BODY>` 標籤執行動作。(TGT-33736)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到有關 Target 和其他 Adobe Experience Cloud 解決方案的未來產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

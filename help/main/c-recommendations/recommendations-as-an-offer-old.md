---
keywords: 推薦;產品建議
description: 了解如何使用 Adobe 推薦作為 A/B 測試 (包括自動分配和自動鎖定目標) 以及體驗鎖定 (XT) 活動的產品建議。
title: 如何使用推薦作為其他活動類型的產品建議？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: f6034e83564a9a386e21e4e57279c66cc3c94537
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 42%

---

# 推薦作為產品建議

您現在可以在[!UICONTROL A/B測試] （包括[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]）和[!UICONTROL 體驗鎖定目標] (XT)活動中包含建議。

這項功能開啟了全新功能，例如:

* 在同一個活動內測試及鎖定建議與非建議內容。
* 輕鬆試驗建議在頁面上的放置方式，包括多個建議的順序。
* 使用[!UICONTROL 自動分配]自動將流量推送到績效最佳的建議體驗。
* 使用[!UICONTROL 自動鎖定目標]，根據訪客的設定檔，以動態方式為訪客指派自訂建議體驗。

若要開始使用，請使用[!UICONTROL 視覺化體驗撰寫器]建立[!UICONTROL A/B測試]或[!UICONTROL 體驗鎖定目標]活動，並使用[!UICONTROL 建議]動作將建議新增至體驗。

## 新增建議作為 A/B 測試或 XT 活動中的產品建議

1. 使用可視化體驗撰寫器 (VEC) 開始三步驟引導式工作流程，建立 [A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)或[體驗鎖定目標](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT) 活動。

   >[!NOTE]
   >
   >若為 A/B 測試，您可以選擇[「自動分配」](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)選項以自動將流量推送至成效最佳的建議，或是選擇[「自動鎖定目標」](/help/main/c-activities/auto-target/auto-target-to-optimize.md)選項，以便根據訪客的輪廓，以動態方式為訪客指派自訂建議體驗。

1. 建立[體驗](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)時，按一下您想新增建議作為選件的元素，按一下&#x200B;**[!UICONTROL 取代內容]** （ ![取代內容圖示](/help/main/assets/icons/Switch.svg) ），然後選取&#x200B;**[!UICONTROL 建議]**。

   ![插入推薦作為產品建議](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. 從右側的[!UICONTROL 建議]邊欄中，按一下&#x200B;**[!UICONTROL 選取建議]**&#x200B;以顯示[!UICONTROL 選取條件]對話方塊。

1. 按一下「**[!UICONTROL 建立條件]**」或選取現有的條件。

1. （選擇性）按一下&#x200B;**[!UICONTROL 篩選]**&#x200B;圖示（ ![篩選圖示](/help/main/assets/icons/Filter.svg) ）從下列選項中選取，以依據頁面型別檢視熱門建議條件：

   * 購物車頁面
   * 類別頁面
   * 首頁
   * 登陸頁面
   * 產品頁面
   * 搜尋結果頁面
   * 感謝頁面
   * 其他

1. 按一下&#x200B;**[!UICONTROL 建立條件]**&#x200B;或選取現有的[條件](/help/main/c-recommendations/c-algorithms/algorithms.md)，然後按一下&#x200B;**[!UICONTROL 下一步]**&#x200B;以顯示[!UICONTROL 選取設計]對話方塊。

1. 按一下[建立設計]****&#x200B;或選取現有的[設計](/help/main/c-recommendations/c-design-overview/design-overview.md)，然後按一下[下一步]****。

1. 在[!UICONTROL 選項]對話方塊中，指定下列專案：

   * 選擇一個[集合](/help/main/c-recommendations/c-products/collections.md)。
   * 視需要設定[「前端促銷活動」和「後端促銷活動」](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)選項。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 使用三步驟引導式工作流程完成 A/B 測試或 XT 活動的設定。

## 編輯推薦產品建議的設定

1. 從[!UICONTROL 建議]邊欄中，按一下[!UICONTROL 條件名稱]、[!UICONTROL 設計名稱]或[!UICONTROL 集合名稱]旁的&#x200B;**[!UICONTROL 編輯]**&#x200B;圖示（![編輯圖示](/help/main/assets/icons/Edit.svg)）以變更元素。

## 刪除建議產品建議

1. 按一下[!UICONTROL 建議]面板頂端的&#x200B;**[!UICONTROL 刪除]**&#x200B;圖示（![刪除圖示](/help/main/assets/icons/Delete.svg)）。

### 檢視Recommendations選件的狀態 {#status}

Recommendations選件（演演算法）狀態會顯示在包含Recommendations選件之A/B測試和XT活動的活動[!UICONTROL 總覽]頁面底部：

* 可用結果
* 不可用結果
* 摘要失敗

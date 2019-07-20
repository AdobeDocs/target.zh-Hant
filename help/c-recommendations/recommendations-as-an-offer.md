---
description: Adobe Recommendations 作為 A/B 測試和體驗鎖定目標活動中的選件。
keywords: Recommendations;選件
seo-description: Adobe Recommendations 作為 A/B 測試 (包括自動分配和自動鎖定目標) 及體驗鎖定目標 (XT) 活動中的選件
seo-title: Adobe Recommendations 作為 A/B 測試 (包括自動分配和自動鎖定目標) 及體驗鎖定目標 (XT) 活動中的選件
solution: Target
title: 建議作為選件
title-outputclass: premium
topic: Premium
translation-type: tm+mt
source-git-commit: e8e6dcadf307209abcc712798b714af0a5be2e7e

---


# ![PREMIUM](/help/assets/premium.png) 建議作為選件

您現在可以在 [!UICONTROL A/B 測試] (包括[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]) 與[!UICONTROL 體驗鎖定目標] (XT) 活動中包含建議。

這項功能開啟了全新功能，例如:

* 在同一個活動內測試及鎖定建議與非建議內容。
* 輕鬆試驗建議在頁面中的放置方法，包括多個建議的排列順序。
* 使用[!UICONTROL 自動分配]將流量推送到績效最好的建議體驗。
* 使用[!UICONTROL 自動鎖定目標]，根據訪客的設定檔，以動態方式為訪客指派自訂建議體驗。

若要開始使用此功能，請使用[!UICONTROL 可視化體驗撰寫器]建立 [!UICONTROL A/B 測試]或[!UICONTROL 體驗鎖定目標]活動，並使用[!UICONTROL 「插入在前」]、[!UICONTROL 「插入在後」]或[!UICONTROL 「取代為」]動作來將建議新增至體驗。

## 新增建議作為 A/B 測試或 XT 活動中的選件

1. 使用可視化體驗撰寫器 (VEC) 開始三步驟引導式工作流程，建立 [A/B 測試](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)或[體驗鎖定目標](/help/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT) 活動。

   >[!NOTE]
   >
   >若為 A/B 測試，您可以選擇[「自動分配」](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)選項以自動將流量推送至成效最佳的建議，或是選擇[「自動鎖定目標」](/help/c-activities/auto-target-to-optimize.md)選項，以便根據訪客的設定檔，以動態方式為訪客指派自訂建議體驗。

1. While creating an [experience](/help/c-experiences/c-visual-experience-composer/viztarget-options.md), click the element you want to add a recommendation to as an offer, select the **[!UICONTROL Insert Before]**, **[!UICONTROL Insert After]**, or **[!UICONTROL Replace With]** action, then select [!UICONTROL Recommendation].

   下圖顯示[!UICONTROL 「插入在後 &gt; 建議」]選項。

   ![插入建議作為選件](/help/c-recommendations/assets/replace-after-recommendations.png)

1. 從下列選項中選擇，按照頁面類型檢視熱門建議條件:

   * 購物車頁面
   * 類別頁面
   * 首頁
   * 登陸頁面
   * 產品頁面
   * 搜尋結果頁面
   * 感謝頁面
   * 其他

1. 選擇所需[條件](/help/c-recommendations/c-algorithms/algorithms.md)，然後按[!UICONTROL 「下一步」]。
1. 選擇所需[設計](/help/c-recommendations/c-design-overview/design-overview.md)，然後按[!UICONTROL 「下一步」]。
1. 在[!UICONTROL 「選項」]對話方塊中，指定下列項目:

   * 選擇一個[集合](/help/c-recommendations/c-products/collections.md)。
   * 視需要設定[「前端促銷活動」和「後端促銷活動」](/help/c-recommendations/t-create-recs-activity/adding-promotions.md)選項。

1. 按一下[!UICONTROL 「儲存」]。
1. 使用三步驟引導式工作流程完成 A/B 測試或 XT 活動的設定。

## 編輯 Recommendations 選件的設定

編輯選件組態的方式有兩種:

* 使用[!UICONTROL 「編輯」]選單
* 使用[!UICONTROL 「修改」]面板

### 使用「編輯」選單編輯建議選件

1. 按一下您要編輯的選件，然後按一下「編輯」。

   ![「編輯」選單](/help/c-recommendations/assets/recs-offer-edit.png)

1. 從下列選項中選擇:

   * [變更條件](/help/c-recommendations/c-algorithms/algorithms.md)
   * [變更設計](/help/c-recommendations/c-design-overview/design-overview.md)
   * [變更集合](/help/c-recommendations/c-products/collections.md)
   * [變更促銷活動](/help/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. 進行編輯。

### 使用「修改」面板編輯建議選件

1. 按一下[!UICONTROL 「修改」]圖示&#x200B;*「&lt;/&gt;」*&#x200B;以顯示[「修改」](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)窗格。
1. 將游標停留在所需的動作上，然後按一下[!UICONTROL 「編輯」]圖示。

   ![「修改」面板](/help/c-recommendations/assets/recs-offer-modifications.png)

1. 進行編輯。

## 刪除建議選件

刪除建議選件的方式有兩種:

* 使用[!UICONTROL 「編輯」]選單
* 使用[!UICONTROL 「修改」]面板

### 使用「編輯」選單刪除建議選件

1. 按一下您要移除的選件，然後按一下[!UICONTROL 「配置 &gt; 移除」]。

   ![移除](/help/c-recommendations/assets/recs-offer-remove.png)

### 使用「修改」面板刪除建議選件

1. 按一下[!UICONTROL 「修改」]圖示&#x200B;*「&lt;/&gt;」*&#x200B;以顯示[「修改」](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)窗格。
1. 將游標停留在所需的動作上，然後按一下[!UICONTROL 「刪除」]圖示。

   ![「刪除」圖示](/help/c-recommendations/assets/recs-offer-delete.png)
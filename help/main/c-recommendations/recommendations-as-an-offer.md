---
keywords: 推薦;產品建議
description: 了解如何使用 Adobe 推薦作為 A/B 測試 (包括自動分配和自動鎖定目標) 以及體驗鎖定 (XT) 活動的產品建議。
title: 如何使用推薦作為其他活動類型的產品建議？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
source-git-commit: f848c79cb95009b5810a1707d04e548a57220e12
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 60%

---

# 推薦作為產品建議

您現在可以在[!UICONTROL A/B Test] （包括[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]）與[!UICONTROL Experience Targeting] (XT)活動中包含建議。

這項功能開啟了全新功能，例如:

* 在同一個活動內測試及鎖定建議與非建議內容。
* 輕鬆試驗建議在頁面中的放置方法，包括多個建議的排列順序。
* 使用[!UICONTROL Auto-Allocate]自動將流量推送到績效最好的建議體驗。
* 使用[!UICONTROL Auto-Target]，根據訪客的設定檔，以動態方式為訪客指派自訂建議體驗。

若要開始，請使用[!UICONTROL Visual Experience Composer]建立[!UICONTROL A/B Test]或[!UICONTROL Experience Targeting]活動，並使用[!UICONTROL Insert Before]、[!UICONTROL Insert After]或[!UICONTROL Replace With]動作將建議新增至體驗。

## 新增建議作為 A/B 測試或 XT 活動中的產品建議

1. 使用可視化體驗撰寫器 (VEC) 開始三步驟引導式工作流程，建立 [A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)或[體驗鎖定目標](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT) 活動。

   >[!NOTE]
   >
   >若為 A/B 測試，您可以選擇[「自動分配」](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)選項以自動將流量推送至成效最佳的建議，或是選擇[「自動鎖定目標」](/help/main/c-activities/auto-target/auto-target-to-optimize.md)選項，以便根據訪客的輪廓，以動態方式為訪客指派自訂建議體驗。

1. 建立[體驗](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)時，按一下您要新增建議作為選件的元素，按一下「**[!UICONTROL Replace Content]**」，然後選取「**[!UICONTROL Recommendation]**」。

   ![插入推薦作為產品建議](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. 從下列選項中選擇，按照頁面類型檢視熱門建議條件:

   * 購物車頁面
   * 類別頁面
   * 首頁
   * 登陸頁面
   * 產品頁面
   * 搜尋結果頁面
   * 感謝頁面
   * 其他

1. 選取所需的[條件](/help/main/c-recommendations/c-algorithms/algorithms.md)，然後按一下[!UICONTROL Next]。
1. 選取所需的[設計](/help/main/c-recommendations/c-design-overview/design-overview.md)，然後按一下[!UICONTROL Next]。
1. 在[!UICONTROL Options]對話方塊中，指定下列專案：

   * 選擇一個[集合](/help/main/c-recommendations/c-products/collections.md)。
   * 視需要設定[「前端促銷活動」和「後端促銷活動」](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)選項。

1. 按一下 [!UICONTROL Save]。
1. 使用三步驟引導式工作流程完成 A/B 測試或 XT 活動的設定。

## 編輯推薦產品建議的設定

編輯產品建議組態的方式有兩種:

* 使用[!UICONTROL Edit]功能表
* 使用[!UICONTROL Modifications]面板

### 使用「編輯」選單編輯建議產品建議

1. 按一下您要編輯的選件，然後按一下&#x200B;**[!UICONTROL Edit]**。

   ![編輯推薦產品建議](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. 從下列選項中選擇:

   * [變更條件](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [變更設計](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [變更集合](/help/main/c-recommendations/c-products/collections.md)
   * [變更促銷活動](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. 進行編輯。

### 使用「修改」面板編輯建議產品建議

1. 按一下[!UICONTROL Modifications]圖示&#x200B;**( `</>` )**&#x200B;以顯示[修改](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)窗格。
1. 將游標停留在所需的動作上，然後按一下&#x200B;**[!UICONTROL Edit]**&#x200B;圖示。

   ![「修改」面板](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. 進行編輯。

## 刪除建議產品建議

刪除建議產品建議的方式有兩種:

* 使用[!UICONTROL Edit]功能表
* 使用[!UICONTROL Modifications]面板

### 使用「編輯」選單刪除建議產品建議

1. 按一下您要移除的選件，然後按一下&#x200B;**[!UICONTROL Layout > Remove]**。

   ![移除](/help/main/c-recommendations/assets/recs-offer-remove.png)

### 使用「修改」面板刪除建議產品建議

1. 按一下[!UICONTROL Modifications]圖示&#x200B;**( &lt;/> )**&#x200B;以顯示[修改](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)窗格。
1. 將游標停留在所需的動作上，然後按一下[!UICONTROL Delete]圖示。

   ![「刪除」圖示](/help/main/c-recommendations/assets/recs-offer-delete.png)

### 檢視Recommendations選件的狀態 {#status}

Recommendations選件的（演演算法）狀態會顯示在包含Recommendations選件之A/B測試和XT活動的[!UICONTROL Overview]頁面底部：

* 可用結果
* 不可用結果
* 摘要失敗

![推薦產品建議狀態](/help/main/c-recommendations/assets/recs-offer-status.png)

## 訓練影片：推薦作為![Overview badge](/help/main/assets/overview.png) 的產品建議

>[!VIDEO](https://video.tv.adobe.com/v/28878)

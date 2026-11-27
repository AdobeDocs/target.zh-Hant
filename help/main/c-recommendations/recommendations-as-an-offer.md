---
keywords: 推薦;產品建議
description: 了解如何使用 Adobe 推薦作為 A/B 測試 (包括自動分配和自動鎖定目標) 以及體驗鎖定 (XT) 活動的產品建議。
title: 如何使用推薦作為其他活動類型的產品建議？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
TQID: 'https://experienceleague.adobe.com/ZMOb5RdY6bES331INSM7VF-w4be-5Xmjqon0YvfuNG4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 12%
---
# 推薦作為產品建議 {#recommendations-as-an-offer}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在[!UICONTROL A/B測試]和[!UICONTROL 體驗鎖定目標] (XT)活動中新增、編輯和刪除建議作為選件。

>[!ENDSHADEBOX]

除了[!UICONTROL Recommendations]活動之外，建議也可包含在[!UICONTROL A/B測試] （包括[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]）和[!UICONTROL 體驗鎖定目標] (XT)活動中。 這可提供下列功能：

* 在同一個活動內測試及鎖定建議與非建議內容。
* 嘗試在頁面上放置建議，包括多個建議的順序。
* 透過&#x200B;**[!UICONTROL 自動分配]**，自動將流量推送到績效最佳的建議體驗。
* 使用&#x200B;**[!UICONTROL 自動鎖定目標]**，根據訪客的設定檔，以動態方式為訪客指派自訂建議體驗。

## 新增建議作為選件 {#add-recs-offer}

使用[!UICONTROL 視覺化體驗撰寫器] (VEC)在[!UICONTROL A/B測試]或XT活動中建立體驗時，建議會新增為選件。

1. 開始VEC的三步驟引導式工作流程，以建立[A/B測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)或[體驗鎖定目標](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT)活動。

   >[!NOTE]
   >
   >若為A/B測試，[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)選項會自動將流量推送至成效最佳的建議，而[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)選項會根據訪客的設定檔，以量身打造的建議體驗來指派訪客。

1. 建立[體驗](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)時，請以下列其中一種方式將建議新增為選件：

   * 按一下新增建議的元素，按一下&#x200B;**[!UICONTROL 取代內容]**，然後選取&#x200B;**[!UICONTROL 建議]**。

     ![已選取標題並在功能表中反白顯示「建議」選項的視覺化體驗撰寫器（在HTML選件和體驗片段選項旁）](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

   * 在&#x200B;**[!UICONTROL 元件]**&#x200B;邊欄中，選取&#x200B;**[!UICONTROL 動態]**&#x200B;底下的&#x200B;**[!UICONTROL 建議]**，將滑鼠游標停留在頁面上的現有元素上，然後按一下&#x200B;**[!UICONTROL 插入到]**&#x200B;之前，或按一下&#x200B;**[!UICONTROL 插入到]**&#x200B;之後，將建議置於該元素之前或之後。

1. 存取&#x200B;**[!UICONTROL 顯示屬性]**&#x200B;功能表，然後按一下&#x200B;**[!UICONTROL Select建議]**。

1. Select所需的[條件](/help/main/c-recommendations/c-algorithms/algorithms.md)，然後按一下&#x200B;**[!UICONTROL 下一步]**。

1. Select所需的[設計](/help/main/c-recommendations/c-design-overview/design-overview.md)，然後按一下&#x200B;**[!UICONTROL 下一步]**。

1. 在&#x200B;**[!UICONTROL 選項]**&#x200B;對話方塊中，指定下列專案：

   * 選擇一個[集合](/help/main/c-recommendations/c-products/collections.md)。
   * 如有必要，請設定[前端促銷活動和後端促銷活動](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)選項。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

1. 使用三步驟引導式工作流程完成[!UICONTROL A/B測試]或XT活動的設定。

## 編輯Recommendations選件 {#edit-recs-offer}

建議選件的條件、設計、集合和促銷活動可在新增選件後從&#x200B;**[!UICONTROL 建議]**&#x200B;窗格變更。

1. 按一下選件，編輯並瀏覽右窗格功能表中的選項。

   ![包含條件、設計和集合名稱的建議窗格，以及所選優惠的「新增促銷活動」按鈕](assets/create_reco_7.png)

1. Select提供下列其中一個選項：

   * [變更條件](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [變更設計](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [變更集合](/help/main/c-recommendations/c-products/collections.md)
   * [變更促銷活動](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. 進行編輯。

## 刪除建議產品建議 {#delete-recs-offer}

可以從&#x200B;**[!UICONTROL 建議]**&#x200B;窗格中刪除不再需要的建議選件。

按一下要移除的選件，然後按一下&#x200B;**[!UICONTROL 建議]**&#x200B;窗格中的bin圖示（![Bin圖示](assets/Smock_Delete_18_N.svg)）。

![建議窗格，反白顯示bin圖示](assets/create_reco_8.png)

## 檢視建議選件的狀態 {#status}

建議選件（演演算法）的狀態會顯示在[!UICONTROL A/B測試]和包含建議選件之XT活動的&#x200B;**[!UICONTROL 總覽]**&#x200B;頁面底部。 狀態為下列其中一項：

* **[!UICONTROL 個結果已就緒]**
* **[!UICONTROL 個結果未就緒]**
* **[!UICONTROL 摘要失敗]**

## 訓練影片：推薦作為![Overview badge](/help/main/assets/overview.png) 的產品建議

>[!VIDEO](https://video.tv.adobe.com/v/28878)

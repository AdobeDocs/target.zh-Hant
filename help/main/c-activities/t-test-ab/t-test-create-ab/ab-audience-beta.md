---
keywords: 客群; 選取客群; 選擇客群; 選取器
description: 根據對象條件定義哪些網站訪客加入您的Adobe [!DNL Target] 活動。
title: 如何在 [!DNL Target] A/B活動中選取對象？
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: cc823f84fb93cbe2e55d394d0f6f4fe48bbd5293
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 12%

---

# 選取客群

對象會決定哪些符合資格的訪客進入了您的[!DNL Adobe Target]活動。

在[建立活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab-beta.md)時，三步驟引導式工作流程的[!UICONTROL Targeting]步驟會顯示流程圖表，引導您完成指派對象及其流量百分比、選取流量分配方法，以及指定活動中每個體驗的流量分配的步驟。

![A/B 測試鎖定目標步驟](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

如需流程圖中所有選項的詳細資訊，請參閱[建立A/B測試活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab-beta.md)。

## 選取活動的對象

1. 按一下&#x200B;**[!UICONTROL All Visitors]**&#x200B;控制項以選取活動的其他對象。

   [!UICONTROL All Visitors]對象已設定為預設值。 如果您選取其他對象，其名稱會顯示在最左側的控制項中。

   針對沒有特定對象鎖定目標的A/B測試，請選擇預設值[!UICONTROL All Visitors]。

   右側框架隨即顯示，可讓您新增或刪除對象，以及指派活動的訪客百分比。

1. 若要變更對象，請按一下右側框架中的&#x200B;**[!UICONTROL Replace]圖示** （ ![取代圖示](/help/main/assets/icons/Retweet.svg) ）。

1. 在[!UICONTROL Add Audience]對話方塊中，[選取所需的對象](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，然後按一下&#x200B;**[!UICONTROL Assign Audience]**。

   依預設，所有訪客皆為對象。但您可以變更對象。對象是從[!UICONTROL Audience Library]中選取，或者您可以建立僅限於此活動的對象。 [!UICONTROL Audience Library]包含先前已定義的對象，包括一些隨著[!DNL Target]預先建置的常見對象。

1. （視條件而定）按一下&#x200B;**結合對象**&#x200B;至[建立結合多個對象的對象](/help/main/c-target/combining-multiple-audiences.md)。

1. （視條件而定）若要建立不在[!UICONTROL Audience Library]中的新對象，請按一下&#x200B;**建立對象**。 在[建立對象工作流程](/help/main/c-target/c-audiences/audiences.md)期間，您可以選擇下列選項：

   * 建立儲存至[!UICONTROL Audience Library]且可在其他活動中重複使用的隨選對象
   * 建立未儲存至[!UICONTROL Audience Library]且只能用於目前活動的[活動特定對象](/help/main/c-target/creating-activity-only-audience.md)

1. 按一下右窗格中的&#x200B;**[!UICONTROL Visitor Percentage]**，然後指定要包含在活動中的合格訪客百分比。

1. 當您對對象感到滿意時，請按一下&#x200B;**[!UICONTROL Next]**&#x200B;以移至三步驟引導式工作流程的第三個步驟。

>[!NOTE]
>
>當您開啟客群清單時，系統會自動在背景匯入客群，且匯入的是登入超過 10 分鐘的客群。

## 檢視對象資訊

1. 在[!UICONTROL Add Audiences]對話方塊中，按一下對象旁的&#x200B;**[!UICONTROL Information]**&#x200B;圖示（ ![資訊圖示](/help/main/assets/icons/InfoOutline.svg) ）以檢視該對象的詳細資訊，包括其來源和屬性。

1. 按一下&#x200B;**[!UICONTROL View Full Details]**&#x200B;以檢視對象的其他詳細資料。 詳細資訊包括對象的屬性；對象的說明、工作區、型別和來源，以及參考此對象的活動清單。 您可以檢視有關每個對象的資訊，包括活動名稱、狀態、工作區、上次修改對象的時間以及修改者。

## 編輯或複製對象

您可以編輯或複製對象，方法是按一下[!UICONTROL Add Audience]對話方塊中所需對象旁的[!UICONTROL More Actions]圖示（![更多動作圖示](/help/main/assets/icons/More.svg) ），然後按一下[!UICONTROL Edit]或[!UICONTROL Copy]。

如果想要建立一個類似現有對象的對象，則複製對象就很有用。您可以製作對象的副本、進行編輯，然後儲存為新對象。


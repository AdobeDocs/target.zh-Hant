---
keywords: 客群; 選取客群; 選擇客群; 選取器
description: 根據對象條件定義哪些網站訪客加入您的Adobe [!DNL Target] 活動。
title: 如何在 [!DNL Target] A/B活動中選取對象？
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
TQID: https://experienceleague.adobe.com/7W8BrRxk4mKlYlgGb-GSOuc0kRMRWBvSochz9STYrTs
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 575
ht-degree: 10%

---

# 選取客群

對象會決定哪些符合資格的訪客進入了您的[!DNL Adobe Target]活動。

當[建立活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)時，三步驟引導式工作流程的[!UICONTROL 鎖定目標]步驟會顯示流程圖表，引導您完成指派對象及其流量百分比、選取流量分配方法，以及指定活動中每個體驗的流量分配的步驟。

![A/B 測試鎖定目標步驟](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

如需流程圖中所有選項的詳細資訊，請參閱[建立A/B測試活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

## 選取活動的對象

1. 按一下&#x200B;**[!UICONTROL 所有訪客]**&#x200B;控制項以選取活動的其他對象。

   [!UICONTROL 所有訪客]對象已設定為預設值。 如果您選取其他對象，其名稱會顯示在最左側的控制項中。

   針對沒有特定對象鎖定目標的A/B測試，請選擇預設值[!UICONTROL 所有訪客]。

   右側框架隨即顯示，可讓您新增或刪除對象，以及指派活動的訪客百分比。

1. 若要變更對象，請按一下右側框架中的&#x200B;**[!UICONTROL 取代]圖示** （ ![取代圖示](/help/main/assets/icons/Retweet.svg) ）。

1. 在[!UICONTROL 新增對象]對話方塊中，[選取所需的對象](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，然後按一下&#x200B;**[!UICONTROL 指派對象]**。

   依預設，所有訪客皆為對象。 但您可以變更對象。 對象是從[!UICONTROL 對象庫]中選取，或者您可以建立僅限於此活動的對象。 [!UICONTROL 對象庫]包含先前已定義的對象，包括一些隨著[!DNL Target]預先建置的常見對象。

1. （視條件而定）按一下&#x200B;**結合對象**&#x200B;至[建立結合多個對象的對象](/help/main/c-target/combining-multiple-audiences.md)。

1. （視條件而定）若要建立不在[!UICONTROL 對象庫]中的新對象，請按一下&#x200B;**建立對象**、定義對象，然後按一下&#x200B;**[!UICONTROL 完成]**。

   在[建立對象工作流程](/help/main/c-target/c-audiences/audiences.md)期間，您可以選擇下列選項：

   * **[!UICONTROL 受眾程式庫]**：建立儲存至[!UICONTROL 受眾程式庫]的隨選受眾，以供在其他活動中重複使用。
   * **[!UICONTROL 僅此活動]**：建立未儲存至[!UICONTROL 對象庫]且僅能用於目前活動的[活動特定對象](/help/main/c-target/creating-activity-only-audience.md)。

1. 按一下右窗格中的&#x200B;**[!UICONTROL 訪客百分比]**，然後指定要包含在活動中的合格訪客百分比。

1. 當您對對象感到滿意時，請按一下[下一步] ****，移至三步驟引導式工作流程的第三個步驟。

>[!NOTE]
>
>當您開啟[!UICONTROL 對象]清單時，系統會自動在背景匯入對象，且匯入的對象已超過10分鐘。

## 檢視對象資訊

1. 在[!UICONTROL 新增對象]對話方塊中，按一下對象旁的&#x200B;**[!UICONTROL 資訊]**&#x200B;圖示（ ![資訊圖示](/help/main/assets/icons/InfoOutline.svg) ），以檢視該對象的詳細資訊，包括其來源和屬性。

1. 按一下&#x200B;**[!UICONTROL 檢視完整詳細資料]**&#x200B;以檢視有關對象的更多詳細資料。 詳細資訊包括對象的屬性；對象的說明、工作區、型別和來源，以及參考此對象的活動清單。 您可以檢視有關每個對象的資訊，包括活動名稱、狀態、工作區、上次修改對象的時間以及修改者。

## 編輯或複製對象

您可以在[!UICONTROL 新增對象]對話方塊中，按一下所要對象旁的[!UICONTROL 更多動作]圖示（![更多動作圖示](/help/main/assets/icons/More.svg) ），然後按一下[!UICONTROL 編輯]或[!UICONTROL 複製]，即可編輯或複製對象。

如果想要建立一個類似現有對象的對象，則複製對象就很有用。 您可以複製對象、進行編輯，然後儲存為新對象。

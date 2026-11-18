---
keywords: 客群; 選取客群; 選擇客群; 選取器
description: 根據對象條件定義哪些網站訪客加入您的Adobe [!DNL Target]活動。
title: 如何在[!DNL Target] A/B活動中選取對象？
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
TQID: 'https://experienceleague.adobe.com/7W8BrRxk4mKlYlgGb-GSOuc0kRMRWBvSochz9STYrTs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 2%
---
# 選取客群 {#select-audience}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何選取、建立、合併、檢視、編輯及複製A/B活動的對象，以及如何設定要包含的訪客百分比。

>[!ENDSHADEBOX]

對象會決定哪些符合資格的訪客進入了您的[!DNL Adobe Target]活動。

當[建立活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)時，三步驟引導式工作流程的&#x200B;**[!UICONTROL 鎖定目標]**&#x200B;步驟會顯示流程圖表，引導您完成指派對象及其流量百分比、選取流量分配方法，以及指定活動中每個體驗的流量分配的步驟。

![A/B 測試鎖定目標步驟](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

如需流程圖中所有選項的詳細資訊，請參閱[建立A/B測試活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

## 選取活動的對象

對象可控制哪些人可以看到您的活動。 只有符合受眾的訪客才能進入，而您會決定這些訪客的參與比例。 依預設，活動會鎖定所有訪客。

1. 按一下&#x200B;**[!UICONTROL 所有訪客]**&#x200B;控制項以選取活動的其他對象。

   **[!UICONTROL 所有訪客]**&#x200B;為預設對象。 針對沒有特定受眾鎖定目標的A/B測試，請保留預設值。 如果您選取其他對象，其名稱會顯示在最左側的控制項中。

1. 按一下&#x200B;**[!UICONTROL 取代]圖示** （![取代圖示](/help/main/assets/icons/Retweet.svg) ）。

   ![](../../assets/audience_activity.png)

1. 在&#x200B;**[!UICONTROL 新增對象]**&#x200B;對話方塊中，瀏覽從&#x200B;**[!UICONTROL 對象庫]**&#x200B;中選取的對象，或者您可以建立僅限於此活動的對象。

   **[!UICONTROL 對象庫]**&#x200B;包含先前已定義的對象，包括一些隨著[!DNL Target]預先建置的常見對象。

   ![](../../assets/audience_activity_2.png)

1. 按一下對象旁的&#x200B;**[!UICONTROL 資訊]**&#x200B;圖示（ ![資訊圖示](/help/main/assets/icons/InfoOutline.svg)）可檢視該對象的詳細資訊，包括其來源和屬性。

   ![](../../assets/audience_activity_3.png)

   您也可以按一下「檢視完整詳細資料&#x200B;**[!UICONTROL 」]**，檢視有關對象的其他詳細資料。

1. （視條件而定）按一下&#x200B;**[!UICONTROL 結合對象]**&#x200B;至[建立結合多個對象的對象](/help/main/c-target/combining-multiple-audiences.md)。

   +++ 建立新對象的步驟

   若要建立不在&#x200B;**[!UICONTROL 對象庫]**&#x200B;中的新對象，請按一下&#x200B;**[!UICONTROL 建立對象]**、定義對象，然後按一下&#x200B;**[!UICONTROL 完成]**。

   在[建立對象工作流程](/help/main/c-target/c-audiences/audiences.md)期間，您可以選擇下列選項：

   * **[!UICONTROL 對象庫]**：建立儲存至&#x200B;**[!UICONTROL 對象庫]**&#x200B;的隨選對象，並可在其他活動中重複使用。
   * **[!UICONTROL 僅此活動]**：建立未儲存至&#x200B;**[!UICONTROL 對象庫]**&#x200B;且僅能用於目前活動的[活動特定對象](/help/main/c-target/creating-activity-only-audience.md)。

   +++

1. 您可以按一下所要對象旁的&#x200B;**[!UICONTROL 更多動作]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/More.svg) ），以編輯或複製對象。

1. 選取您的對象後，按一下&#x200B;**[!UICONTROL 指派對象]**。

1. 按一下右窗格中的&#x200B;**[!UICONTROL 訪客百分比]**，然後指定要包含在活動中的合格訪客百分比。

1. 當您對對象感到滿意時，請按一下[下一步] **&#x200B;**，移至三步驟引導式工作流程的第三個步驟。

>[!NOTE]
>
>當您開啟&#x200B;**[!UICONTROL 對象]**&#x200B;清單時，系統會自動在背景匯入對象，且匯入的對象已超過10分鐘。

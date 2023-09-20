---
keywords: 對象; 選取對象; 選擇對象; 選取器
description: 對象會決定哪些網站訪客進入您的Adobe [!DNL Target] 活動。
title: 如何在「 」中選取對象 [!DNL Target] A/B活動？
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: 676350453268e4ffc04df83dcda0525842ca8b07
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 70%

---

# 選取對象

對象會決定哪些網站訪客進入您的 [!DNL Adobe Target] 活動。

>[!NOTE]
>
>除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 在 [!UICONTROL 對象] 方塊中，按一下 **[!UICONTROL 編輯]** 圖示（垂直省略符號），然後按一下 **[!UICONTROL 取代對象]**.

   ![取代受眾選項](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/replace-audience.png)

   依預設，所有訪客皆為對象。但您可以變更對象。對象是從對象資料庫中選取，但您也可以建立僅限於此活動的對象。受眾資料庫包含先前已定義的受眾，包括一些隨著 [!DNL Target] 預先建置的共通受眾。

1. 選取或建立所需的對象：

   * 從資料庫中選取對象
   * [合併多個對象](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)
   * [建立新對象](/help/main/c-target/c-audiences/create-audience.md#task_1D507519D3AD4390B507F188BD294DC1)
   * [建立僅限於此活動的對象](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

   針對沒有特定對象鎖定目標的A/B測試，請選擇預設值 [!UICONTROL 所有訪客].

   您也可以將游標移至中所需的對象上，以編輯或複製對象。 [!UICONTROL 新增對象] 對話方塊，如下所示。

   如果想要建立一個類似現有對象的對象，則複製對象就很有用。您可以複製對象、進行編輯，然後儲存為新對象。其他活動類型也支援此暫留功能。

   ![受眾暫留](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audience_picker_hover-new.png)

   建立觀眾時，您可以選取位置 (mbox) 並指定該位置的參數。在 [!UICONTROL 自訂引數]，選取mbox，然後指定所需的引數。

   >[!NOTE]
   >
   >當您開啟對象清單時，系統會自動在背景匯入對象，且匯入的是登入超過 10 分鐘的對象。

1. （依條件）指定要包含在活動中的合格訪客百分比。

   例如，您可以選擇包含所有訪客的 50%。

   ![受眾百分比](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   您也可以選擇讓 Target [自動分配流量](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

## 培訓影片

以下影片含有本文章探討之概念的詳細資訊。

### 在 Adobe Target 中使用對象 (6:21) ![Overview badge](/help/main/assets/overview.png)

此影片說明如何在 [!DNL Target Standard/Premium] 中使用對象。

* 說明詞語「對象」
* 說明將對象用於最佳化的兩個方式
* 在對象清單中尋找對象
* 將活動鎖定至對象
* 對活動中的被動報表使用對象

>[!VIDEO](https://video.tv.adobe.com/v/17398)

### 活動工作流程 — 鎖定目標(2:14) ![教學課程徽章](/help/main/assets/tutorial.png)

此視訊包含有關如何設定對象的資訊。

* 指派對象至您的活動
* 向上或向下調節流量
* 選取您的流量分配方法
* 在不同體驗之間分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17385)

如需詳細資訊，請參閱[對象](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)。

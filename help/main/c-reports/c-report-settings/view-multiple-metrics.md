---
keywords: Target；報表；報表設定；多個量度；量度；顯示量度；隱藏量度
description: 了解如何使用Adobe Target在報表中選取多個要檢視的量度。
title: 如何在報表中檢視多個量度？
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
source-git-commit: d90e541588f51e16dd9b11ead1ece77e9ca1408b
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 59%

---

# 在報表中檢視多個量度

您可以選取多個量度以在 [!DNL Adobe Target] 報表。

在報表中使用多個量度時，請注意下列資訊:

* 可檢視多個量度 [A/B測試](/help/main/c-activities/t-test-ab/test-ab.md), [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)，和 [體驗鎖定](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活動。
* 針對使用 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。 您可以將活動中的量度新增至已新增活動的報表 *not* 使用A4T。
* 如果您選取多個量度，則無法使用[](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)「下載」選項將報表下載為 CSV。在只有選取一個量度的情況下，才能啟用[!UICONTROL 「下載」]選項。
* 您無法檢視2015年7月之前建立之活動的多個量度 [!DNL Target] 發行（2015年7月30日）。

**若要選取多個量度來顯示在報表中:**

1. 若要顯示報表，請按一下&#x200B;**[!UICONTROL 「活動」]**，從清單按一下需要的活動，然後按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;索引標籤。
1. 按一下&#x200B;**[!UICONTROL 「報表量度」]**&#x200B;下拉式清單，以顯示[!UICONTROL 「顯示量度」]和[!UICONTROL 「隱藏量度」]清單。

   ![](assets/multiple_metrics.png)

   您可以使用[!UICONTROL 「搜尋」]方塊，快速找到可用的量度來新增至[!UICONTROL 「顯示量度」]清單。

   請注意，從報表的[!UICONTROL 「表格檢視」]和[!UICONTROL 「圖表檢視」]模式中，您都可以選取多個量度。

1. 在[!UICONTROL 「隱藏量度」]清單中，將滑鼠指標移至所需的量度上，然後按一下&#x200B;**[!UICONTROL 「選取」]**，將這些量度移至[!UICONTROL 「顯示量度」]清單。

   或

   將所需的量度從[!UICONTROL 「隱藏量度」]清單中拖放至[!UICONTROL 「顯示量度」]清單。

   [!UICONTROL 「顯示量度」]清單中至少必須有一個量度。

   在[!UICONTROL 「顯示量度」]清單中，您可以將量度拖放成想要的順序，以重新排列量度。所選順序將反映在 [!UICONTROL 表格檢視] 和 [!UICONTROL 圖表檢視]. 若要從[!UICONTROL 「顯示量度」]清單中移除量度，請將滑鼠指標移至量度上，然後按一下 **X** 圖示。

1. 完成時，按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. （條件性）在 [!UICONTROL 表格檢視]，將滑鼠指標移至任何量度的欄標題上，即可顯示藍色箭頭。 按一下箭頭可展開表格，來顯示該量度的[!UICONTROL 提升度]和[!UICONTROL 信賴度]。

   ![](assets/multiple_metrics_table.png)

   您一次只能展開一個量度/欄。再按一次箭頭可折疊欄。

1. （條件性）在「圖表檢視」中檢視報表時，您可以從下拉式清單中選取要顯示的個別量度：

   ![](assets/multiple_metrics_graph.png)

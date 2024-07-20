---
keywords: Target；報表；報表設定；多個量度；量度；顯示的量度；隱藏的量度
description: 瞭解如何使用Adobe Target選取要在報表中檢視的多個量度。
title: 如何在報表中檢視多個量度？
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 12%

---

# 在報表中檢視多個量度

您可以選取要在[!DNL Adobe Target]報表中檢視的多個量度。

在報表中使用多個量度時，請注意下列資訊:

* 只有[A/B測試](/help/main/c-activities/t-test-ab/test-ab.md)、[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)和[體驗鎖定目標](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活動才可檢視多個量度。
* 對於使用[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活動，您無法將超過20個量度新增到報告中。 您可以將活動中的量度新增至&#x200B;*不*&#x200B;使用A4T之活動的報表。
* 如果您已選取多個量度，則無法使用[下載選項](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)將報表下載為CSV。 您必須僅選取單一量度才能啟用[!UICONTROL Download]選項。
* 您無法針對2015年7月[!DNL Target]版本（2015年7月30日）之前建立的活動檢視多個量度。

**若要選取多個量度來顯示在報表中:**

1. 若要顯示報表，請按一下&#x200B;**[!UICONTROL Activities]**，從清單按一下需要的活動，然後按一下&#x200B;**[!UICONTROL Reports]**&#x200B;索引標籤。
1. 按一下&#x200B;**[!UICONTROL Report Metric]**&#x200B;下拉式清單以顯示[!UICONTROL Shown Metrics]與[!UICONTROL Hidden Metrics]清單。

   ![多個量度影像](assets/multiple_metrics.png)

   您可以使用[!UICONTROL Search]方塊快速尋找可用的量度以新增至[!UICONTROL Shown Metrics]清單。

   請注意，您可以從報表的[!UICONTROL Table View]和[!UICONTROL Graph View]模式中選取多個量度。

1. 將滑鼠指標停留在[!UICONTROL Hidden Metrics]清單中所需的量度上，然後按一下&#x200B;**[!UICONTROL Select]**&#x200B;以將其移至[!UICONTROL Shown Metrics]清單。

   或

   將所需的量度從[!UICONTROL Hidden Metrics]清單拖放至[!UICONTROL Shown Metrics]清單。

   [!UICONTROL Shown Metrics]清單中必須至少有一個量度。

   您可以在[!UICONTROL Shown Metrics]清單中將量度拖放至所需的順序，藉此重新排列量度。 選取的順序將反映在[!UICONTROL Table View]和[!UICONTROL Graph View]中。 若要從[!UICONTROL Shown Metrics]清單移除量度，請將滑鼠指標停留在量度上，然後按一下&#x200B;**X**&#x200B;圖示。

1. 完成時，請按一下&#x200B;**[!UICONTROL Save]**。
1. （視條件而定）在[!UICONTROL Table View]中檢視報表時，將滑鼠指標暫留在任何量度的欄標題上，即可顯示藍色箭頭。 按一下箭頭以展開表格以顯示該量度的[!UICONTROL Lift]和[!UICONTROL Confidence]。

   ![multiple_metrics_table影像](assets/multiple_metrics_table.png)

   您一次只能展開一個量度/欄。再按一次箭頭可折疊欄。

1. （視條件而定）在「圖表檢視」中檢視報表時，您可以從下拉式清單中選取個別要顯示的量度：

   ![multiple_metrics_graph影像](assets/multiple_metrics_graph.png)

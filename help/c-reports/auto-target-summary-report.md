---
keywords: reports;auto-target;auto target;AT;report
description: 有關如何解譯Adobe Target中「自動目標摘要」報表的資訊。
title: 自動鎖定目標摘要報表
feature: Reports
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 55%

---


# ![](/help/assets/premium.png) PREMIUMAuto-Target摘要報告{#auto-target-summary-report}

有關如何解譯[!DNL Adobe Target]中的[!UICONTROL 自動目標摘要]報告的資訊。

>[!NOTE]
>
>[!UICONTROL 自動鎖定目標]是 [!DNL Target Premium] 解決方案內建的功能。它不包含在[!DNL Target Standard]中，而不含[Target Premium授權](/help/c-intro/intro.md#premium)。

要顯示[!UICONTROL 自動目標摘要]報告：

1. 在[!UICONTROL 活動]頁面中，按一下所需的[!UICONTROL 自動定位]活動。

   如果您有許多活動，則可從[!UICONTROL 類型]、[!UICONTROL 狀態]、[!UICONTROL 屬性]、[!UICONTROL 報告來源]、[!UICONTROL Experience Composer]、[!UICONTROL 量度類型]和[!UICONTROL 活動來源]下拉式清單。

1. 按一下「[!UICONTROL 報表]」標籤，然後按一下所要的圖示：

   * 表格檢視
   * 圖表檢視
   * 自動化區段
   * 重要屬性

## 表格檢視

下圖顯示在檢視[!UICONTROL Auto-Target]活動報表時，[!UICONTROL 表格檢視]中的典型摘要報表外觀：

![自動定位表格檢視報表](/help/c-reports/assets/at-table-view.png)

解譯[!UICONTROL Auto-Target]報表時的一些提示和注意事項：

* 表格中的各列可協助您瞭解活動效能。

   * 在報表頁面上，表格中最上方的兩列指出，在指派給控制的訪客 (亦即隨機提供的體驗) 與指派給個人化演算法的訪客之間，A/B 測試的結果。此資訊可用來對照隨機提供的控制，以測量個人化演算法的表現。
   * 剩餘的列會顯示體驗等級的結果。對於每個體驗，兩種訪客的平均回應之間會相互比較: 以隨機提供的控制來顯示體驗，或利用個人化演算法來顯示體驗。

* 在報表中，每個體驗旁的綠色勾號圖示表示已為該體驗產生個人化機器學習模型。時鐘圖示表示提供的流量還不足以建立模型。

   * 因為是針對每個體驗而建立模型，看到的模型可能屬於有綠色勾號的一些體驗，也可能屬於有時鐘圖示的體驗。
   * 在此情況下，為了加速活動來為所有體驗建立模型，更多流量會傳送至未建立模型的體驗。
   * 至少必須有兩個體驗已建立模型 (綠色勾號)，如此個人化才會開始。

* 在[!UICONTROL Auto-Target]中，比較體驗A與體驗B的轉換率並不正確。 問題在於智慧地或隨機地提供時 (即與控制相比)，體驗 A 何時表現較佳。市場行銷人員也要小心解讀個別體驗的提升度，因為個人化演算法會嘗試以整個活動的成功量度而最佳化，而非針對每個體驗。
* 提升度最高的體驗可視為在母體內有最大的差異性。亦即，演算法已找到一個最類似於該特定體驗的區段。
* 表格中的各欄顯示瀏覽次數、轉換率、平均提升度和信賴等級以及信賴度。 如需詳細資訊，請參閱[平均提升度、提升度界限和信賴區間](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md)。

## 圖表檢視

下圖顯示在檢視[!UICONTROL Auto-Target]活動報表時，「圖形檢視」[!UICONTROL 中的典型摘要報表外觀：]

![自動目標圖形檢視報表](/help/c-reports/assets/at-graph-view.png)

如下所示，您可以使用兩個下拉式清單來選擇所需的度量、計數方法等。 如需詳細資訊，請參閱[報表設定概觀](/help/c-reports/c-report-settings/report-settings.md):

![自動目標圖形檢視報表](/help/c-reports/assets/at-graph-view-2.png)

## 自動化區段

按一下「自動化區段」圖示。 此報表顯示不同訪客對您AP/AT活動中的選件／體驗的回應方式。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。

![自動化區段圖示](/help/c-reports/assets/icon-automated-sements.png)

如需詳細資訊，請參閱[自動化區段報表](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要屬性

按一下[!UICONTROL 重要屬性]表徵圖。 此報表顯示在不同活動中，不同屬性對於模型決定個人化的方式更重要（或更少）。 此報表顯示影響模型及其相對重要性的常見屬性。

![重要屬性圖示](/help/c-reports/assets/icon-important-attributes.png)

如需詳細資訊，請參閱[重要屬性報表](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

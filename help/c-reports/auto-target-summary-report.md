---
keywords: reports;auto-target;auto target;AT
description: 如何解讀自動鎖定目標摘要報表的相關資訊。
title: 自動鎖定目標摘要報表
subtopic: Multivariate Test
topic: Standard
uuid: a30fa886-e8df-408f-bbc9-11a917a592d8
translation-type: tm+mt
source-git-commit: 3faba3d3158bed69ae5d756fb70c97d17110c1d8

---


# 自動鎖定目標摘要報表{#auto-target-summary-report}

有關如何解譯「自動目標摘要」報表的資訊。

要顯示「自動目標摘要」報表，請執行以下操作：

1. 在「活 [!UICONTROL 動] 」頁面中，按一下所要的「自動定位」活動。

   如果您有許多活動，則可從「類型」、「狀態」、「屬性」、「報告來源」、「體驗撰寫器」、「量度類型」和「活動來源」下拉式清單中選取選項，以篩選清單。

1. 按一下[!UICONTROL 「報表」]標籤。

## 表格檢視

下圖顯示使用Auto-Target時，「表格檢視」中的典型摘要報表外觀：

![自動定位表格檢視報表](/help/c-reports/assets/at-table-view.png)

解讀自動鎖定目標報表時的一些秘訣和考量:

* 表格中的許多列有助於瞭解活動效能。

   * 在報表頁面上，表格中最上方的兩列指出，在指派給控制的訪客 (亦即隨機提供的體驗) 與指派給個人化演算法的訪客之間，A/B 測試的結果。此資訊可用來對照隨機提供的控制，以測量個人化演算法的表現。
   * 剩餘的列會顯示體驗等級的結果。對於每個體驗，兩種訪客的平均回應之間會相互比較: 以隨機提供的控制來顯示體驗，或利用個人化演算法來顯示體驗。

* 在報表中，每個體驗旁的綠色勾號圖示表示已為該體驗產生個人化機器學習模型。時鐘圖示表示提供的流量還不足以建立模型。

   * 因為是針對每個體驗而建立模型，看到的模型可能屬於有綠色勾號的一些體驗，也可能屬於有時鐘圖示的體驗。
   * 在此情況下，為了加速活動來為所有體驗建立模型，更多流量會傳送至未建立模型的體驗。
   * 至少必須有兩個體驗已建立模型 (綠色勾號)，如此個人化才會開始。

* 在自動鎖定目標中，比較體驗 A 的轉換率與體驗 B 的轉換率不是正確的比較。問題在於智慧地或隨機地提供時 (即與控制相比)，體驗 A 何時表現較佳。市場行銷人員也要小心解讀個別體驗的提升度，因為個人化演算法會嘗試以整個活動的成功量度而最佳化，而非針對每個體驗。
* 提升度最高的體驗可視為在母體內有最大的差異性。亦即，演算法已找到一個最類似於該特定體驗的區段。
* 表格中的各欄顯示瀏覽次數、轉換率、平均提升度和信賴等級以及信賴度。 如需詳細資訊，請參閱[平均提升度、提升度界限和信賴區間](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md)。

## 圖表檢視

下圖顯示使用Auto-Target時，「圖形檢視」中典型摘要報表的外觀：

![自動目標圖形檢視報表](/help/c-reports/assets/at-graph-view.png)

如下所示，您可以使用兩個下拉式清單來選擇所需的度量、計數方法等。 如需詳 [細資訊](/help/c-reports/c-report-settings/report-settings.md) ，請參閱報表設定概觀：

![自動目標圖形檢視報表](/help/c-reports/assets/at-graph-view-2.png)

## 自動化區段

按一下「自動化區段」圖示。 此報表顯示不同訪客對您AP/AT活動中的選件／體驗的回應方式。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。

![自動化區段圖示](/help/c-reports/assets/icon-automated-sements.png)

如需詳細資訊，請參閱「自 [動化區段」報表](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要屬性

按一下「重要屬性」圖示。 此報表顯示在不同活動中，不同屬性對於模型決定個人化的方式更重要（或更少）。 此報表顯示影響模型及其相對重要性的常見屬性。

![重要屬性圖示](/help/c-reports/assets/icon-important-attributes.png)

如需詳細資訊，請參閱重 [要屬性報表](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

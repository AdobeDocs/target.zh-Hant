---
keywords: 報表；自動目標；自動目標；AT;reports;auto-target;auto target;report
description: 瞭解如何解釋Adobe Target的「自動目標摘要」報告。 可以從此報告切換到「自動段」和「重要屬性」報告。
title: 如何使用自動目標摘要報告？
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 53%

---

# ![高級](/help/main/assets/premium.png) 自動目標摘要報告

有關如何解釋 [!UICONTROL 自動目標摘要] 報告 [!DNL Adobe Target]。

>[!NOTE]
>
>[!UICONTROL 自動鎖定目標]是 [!DNL Target Premium] 解決方案內建的功能。不包含在 [!DNL Target Standard] 沒有 [目標高級許可證](/help/main/c-intro/intro.md#premium)。

顯示 [!UICONTROL 自動目標摘要] 報告：

1. 從 [!UICONTROL 活動] 的子菜單。 [!UICONTROL 自動目標] 的子菜單。

   如果您有許多活動，則可以通過從 [!UICONTROL 類型]。 [!UICONTROL 狀態]。 [!UICONTROL 屬性]。 [!UICONTROL 報告源]。 [!UICONTROL 體驗作曲家]。 [!UICONTROL 度量類型], [!UICONTROL 活動源] 下拉清單。

1. 按一下 [!UICONTROL 報告] 頁籤，然後按一下所需的表徵圖：

   * 表格檢視
   * 圖表檢視
   * 自動化區段
   * 重要屬性

## 表格檢視

下圖顯示了典型摘要報告在中的外觀 [!UICONTROL 表視圖] 查看 [!UICONTROL 自動目標] 活動報告：

![自動目標表視圖報告](/help/main/c-reports/assets/at-table-view.png)

解釋時的一些提示和注意事項 [!UICONTROL 自動目標] 報告：

* 表中的各行有助於您瞭解活動效能。

   * 在報表頁面上，表格中最上方的兩列指出，在指派給控制的訪客 (亦即隨機提供的體驗) 與指派給個人化演算法的訪客之間，A/B 測試的結果。此資訊可用來對照隨機提供的控制，以測量個人化演算法的表現。
   * 剩餘的列會顯示體驗等級的結果。對於每個體驗，兩種訪客的平均回應之間會相互比較: 以隨機提供的控制來顯示體驗，或利用個人化演算法來顯示體驗。

* 在報告中，每個體驗旁的綠色勾號圖示表示已為該體驗產生的個人化機器學習模型。時鐘圖示表示，提供的流量還不足以建立模型。

   * 因為是針對每個體驗而建立模型，看到的模型可能屬於有綠色勾號的一些體驗，也可能屬於有時鐘圖示的體驗。
   * 在此情況下，為了加速活動來為所有體驗建立模型，更多流量會傳送至未建立模型的體驗。
   * 至少必須有兩個體驗已建立模型 (綠色勾號)，如此個人化才會開始。

* 將經驗A與經驗B的轉換率進行比較是不正確的 [!UICONTROL 自動目標]。 問題在於智慧地或隨機地提供時 (即與控制相比)，體驗 A 何時表現較佳。市場行銷人員也要小心解讀個別體驗的提升度，因為個人化演算法會嘗試以整個活動的成功量度而最佳化，而非針對每個體驗。
* 提升度最高的體驗可視為在母體內有最大的差異性。亦即，演算法已找到一個最類似於該特定體驗的區段。
* 表中各列顯示訪問次數、轉換率、平均提升和置信度以及置信度。 如需詳細資訊，請參閱[平均提升度、提升度界限和信賴區間](/help/main/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md)。

## 圖表檢視

下圖顯示了典型摘要報告在中的外觀 [!UICONTROL 圖形視圖] 查看 [!UICONTROL 自動目標] 活動報告：

![「Auto-Target graph view」報告](/help/main/c-reports/assets/at-graph-view.png)

如下所示，您可以使用兩個下拉清單來選擇所需的度量、計數方法等。 請參閱 [報告設定概述](/help/main/c-reports/c-report-settings/report-settings.md) 的子菜單：

![「Auto-Target graph view」報告](/help/main/c-reports/assets/at-graph-view-2.png)

## 自動化區段

按一下 [!UICONTROL 自動化段] 表徵圖 此報告顯示不同訪問者對AP/AT活動中的服務/體驗的不同反應。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。

![自動段表徵圖](/help/main/c-reports/assets/icon-automated-sements.png)

有關詳細資訊，請參見 [「 Automated Segments 」報告](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)。

## 重要屬性

按一下 [!UICONTROL 重要屬性] 表徵圖 此報表顯示在不同活動中，不同屬性對模型決定如何個性化更重要（或更不重要）。 此報表顯示影響模型及其相對重要性的常見屬性。

![重要屬性表徵圖](/help/main/c-reports/assets/icon-important-attributes.png)

有關詳細資訊，請參見 [重要屬性報告](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

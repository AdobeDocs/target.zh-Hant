---
keywords: 報表；自動鎖定目標；AT；報表
description: 了解如何解譯Adobe Target中的自動鎖定目標摘要報表。 您可以從此報表切換至「自動化區段」和「重要屬性」報表。
title: 如何使用自動鎖定目標摘要報表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 52%

---

# 自動鎖定目標摘要報表

有關如何解譯 [!UICONTROL 自動鎖定目標摘要] 報表 [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL 自動鎖定目標]是 [!DNL Target Premium] 解決方案內建的功能。不包含在 [!DNL Target Standard] 沒有 [Target Premium授權](/help/main/c-intro/intro.md#premium).

若要顯示 [!UICONTROL 自動鎖定目標摘要] 報表：

1. 從 [!UICONTROL 活動] 頁面，按一下所需 [!UICONTROL 自動鎖定目標] 活動。

   如果您有許多活動，您可以選取 [!UICONTROL 類型], [!UICONTROL 狀態], [!UICONTROL 屬性], [!UICONTROL 報表來源], [!UICONTROL 體驗撰寫器], [!UICONTROL 量度類型]，和 [!UICONTROL 活動來源] 下拉式清單。

1. 按一下 [!UICONTROL 報表] 標籤，然後按一下所需圖示：

   * 表格檢視
   * 圖表檢視
   * 自動化區段
   * 重要屬性

## 表格檢視

下圖顯示典型摘要報表在 [!UICONTROL 表格檢視] 檢視 [!UICONTROL 自動鎖定目標] 活動的報表：

![自動鎖定目標表格檢視報表](/help/main/c-reports/assets/at-table-view.png)

解讀時的一些提示和考量 [!UICONTROL 自動鎖定目標] 報表：

* 表格中的各列可協助您了解活動效能。

   * 在報表頁面上，表格中最上方的兩列指出，在指派給控制的訪客 (亦即隨機提供的體驗) 與指派給個人化演算法的訪客之間，A/B 測試的結果。此資訊可用來對照隨機提供的控制，以測量個人化演算法的表現。
   * 剩餘的列會顯示體驗等級的結果。對於每個體驗，兩種訪客的平均回應之間會相互比較: 以隨機提供的控制來顯示體驗，或利用個人化演算法來顯示體驗。

* 在報告中，每個體驗旁的綠色勾號圖示表示已為該體驗產生的個人化機器學習模型。時鐘圖示表示，提供的流量還不足以建立模型。

   * 因為是針對每個體驗而建立模型，看到的模型可能屬於有綠色勾號的一些體驗，也可能屬於有時鐘圖示的體驗。
   * 在此情況下，為了加速活動來為所有體驗建立模型，更多流量會傳送至未建立模型的體驗。
   * 至少必須有兩個體驗已建立模型 (綠色勾號)，如此個人化才會開始。

* 比較體驗A與體驗B的轉換率，並非 [!UICONTROL 自動鎖定目標]. 問題在於智慧地或隨機地提供時 (即與控制相比)，體驗 A 何時表現較佳。市場行銷人員也要小心解讀個別體驗的提升度，因為個人化演算法會嘗試以整個活動的成功量度而最佳化，而非針對每個體驗。
* 提升度最高的體驗可視為在母體內有最大的差異性。亦即，演算法已找到一個最類似於該特定體驗的區段。
* 表格中的各欄顯示瀏覽次數、轉換率、平均提升度和信賴等級以及信賴度。 如需詳細資訊，請參閱 [A/B測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## 圖表檢視

下圖顯示典型摘要報表在 [!UICONTROL 圖表檢視] 檢視 [!UICONTROL 自動鎖定目標] 活動的報表：

![自動鎖定目標圖表檢視報表](/help/main/c-reports/assets/at-graph-view.png)

如下所示，您可以使用兩個下拉式清單來選擇所需的量度、計數方法等。 請參閱 [報表設定概觀](/help/main/c-reports/c-report-settings/report-settings.md) 如需詳細資訊，請參閱：

![自動鎖定目標圖表檢視報表](/help/main/c-reports/assets/at-graph-view-2.png)

## 自動化區段

按一下 [!UICONTROL 自動化區段] 表徵圖。 此報表顯示不同訪客對您AP/AT活動中的選件/體驗有何不同的回應。 此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的選件/體驗。

![「自動化區段」圖示](/help/main/c-reports/assets/icon-automated-sements.png)

如需詳細資訊，請參閱 [「自動化區段」報表](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## 重要屬性

按一下 [!UICONTROL 重要屬性] 表徵圖。 此報表顯示在不同活動中，不同屬性對於模型決定個人化的方式或多或少都有不同的重要性。 此報表顯示影響模型及其相對重要性的常見屬性。

![「重要屬性」表徵圖](/help/main/c-reports/assets/icon-important-attributes.png)

如需詳細資訊，請參閱 [「重要屬性」報表](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

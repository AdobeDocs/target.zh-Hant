---
keywords: a4t;A4T;使用 Analytics 作為 Target 的報告來源
description: 瞭解如何在Adobe中建立自動分配和自動目標活動 [!DNL Target] 將Analytics用作報告源(A4T)。
title: A4T是否支援自動分配和自動目標活動？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1243'
ht-degree: 2%

---

# 自動分配和自動鎖定目標活動的 A4T 支援

的 [!DNL Adobe Target] — 到[!DNL Adobe Analytics] 整合，稱為 [目標分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)支援 [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 活動。

A4T整合允許您：

* 使用 [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)多武裝強盜駕車制勝經驗，
* 使用 [自動目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)整合機器學習算法為每個訪問者選擇最佳體驗。 Auto-Target在使用 [!DNL Adobe Analytics] 目標度量和 [!DNL Adobe Analytics]豐富的報告和分析能力。

確保你 [已實施A4T，用於A/BTest和經驗目標活動](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)。 如果您使用 `analyticsLogging = client_side`，您還必須通過 `sessionId` 值 [!DNL Analytics]。 有關詳細資訊，請參見 [目標(A4T)報告分析](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) 的 *Adobe TargetSDK* 的子菜單。

若要開始執行:

1. 建立A/BTest活動時， **[!UICONTROL 目標]** 的 **[!UICONTROL 流量分配方法]**:

   * [!UICONTROL 自動分配以獲得最佳體驗]
   * [!UICONTROL 個性化體驗的自動目標]

   ![流量分配方法選項：手動、自動分配和自動目標](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   有關詳細資訊和逐步說明，請參見 [建立自動分配活動](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) 和 [建立自動目標活動](/help/main/c-activities/auto-target/create-auto-target.md)。

1. 選擇 **[!UICONTROL Adobe Analytics]** 為 **[!UICONTROL 報告源]** 的 **[!UICONTROL 目標和設定]** ，然後選擇與所需優化目標對應的報告套件。

   ![「目標和設定」頁上的「報告源」部分](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 選擇主要目標度量。

   * 要使用 [!DNL Adobe Target] 要指定優化目標，請選擇 **[!UICONTROL 轉換]** 。
   * 選擇 **[!UICONTROL 使用分析度量]** 然後從中選擇度量 [!DNL Analytics] 作為優化目標。 您可以使用現成的 [!DNL Analytics] 轉換度量或 [!DNL Analytics] 自定義事件。

   請參閱 [支援的目標度量](#supported) 下面的。

1. 保存並激活活動。

   [!UICONTROL 自動分配] 使用所選指標優化活動，使訪問者體驗最大化目標指標的體驗。

   或

   [!UICONTROL 自動目標] 使用所選指標來優化活動，從而推動訪問者獲得個性化的最佳體驗。

1. 使用 **[!UICONTROL 報告]** 頁籤以查看活動的報告 [!DNL Adobe Analytics] 度量。 按一下 **[!UICONTROL 在分析中查看]** 深入挖掘並進一步細分報告資料。

## 支援的目標度量 {#supported}

[!UICONTROL A4T] 為 [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 允許您選擇以下任意度量類型作為優化的主要目標度量：

* [!DNL Adobe Target] 轉換量度
* [!DNL Adobe Analytics] 轉換量度
* [!DNL Adobe Analytics] 個自訂事件

[!UICONTROL A4T] 為 [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 要求您選擇基於二項式事件的度量。 二項式事件是否發生。 二項式事件包括點擊、轉換、命令等。 這些類型的事件有時也稱為Bernoulli、二進位或離散事件。

[!UICONTROL A4T] 為 [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 不支援連續度量的優化。 連續度量包括收入、訂購的產品數、會話持續時間、會話中的頁面視圖數等。 這些不受支援的度量類型有時也稱為非二項式度量或非伯努利度量。

不支援以下度量類型作為主要目標度量：

* [!DNL Adobe Target] 項目和收入指標
* [!DNL Adobe Analytics] 項目和收入指標

   可以選擇 [!DNL Analytics] 將項目或收入指標作為主要目標指標，因為 [!DNL Target] 無法識別和排除所有項目和收入指標 [!DNL Analytics]。 僅從中選擇二項式轉換度量或自定義事件 [!DNL Analytics]。

* [!DNL Adobe Analytics] 計算度量

## 限制和說明

某些限制和注釋適用於兩者 [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 活動。 其它限制和注釋適用於一種活動類型或另一種活動類型。

### 自動分配和自動鎖定目標 {#both}

* 使用時 [!DNL Adobe Analytics] 作為 [!UICONTROL 自動分配] 或 [!UICONTROL 自動目標]，應始終查看報告 [!DNL Analytics]。
* 無法更改報告源 [!DNL Analytics] 至 [!DNL Target] 或者在激活某個活動之後。
* 雖然不支援將計算的度量作為主要目標度量，但通常可以通過選擇自定義事件作為主要目標度量來實現預期的結果。 例如，如果要優化度量，例如「每個訪問者的表單完成」，請選擇與「表單完成」對應的自定義事件作為主要目標度量。 [!DNL Target] 根據每次訪問自動規範轉換度量，以考慮不均勻的通信量分佈，因此不需要使用計算的度量來執行規範化。
* 使用時 [!DNL Adobe Analytics] 作為 [!UICONTROL 自動分配] 或 [!UICONTROL 自動目標] 活動，您應始終在 [!DNL Analytics]。
* 無法更改報告源 [!DNL Analytics] 至 [!DNL Target] 激活活動後，反之亦然。
* 雖然不支援將計算的度量作為主要目標度量，但通常可以通過選擇自定義事件作為主要目標度量來實現預期的結果。 例如，如果要優化度量，例如「每個訪問者的表單完成」，請選擇與「表單完成」對應的自定義事件作為主要目標度量。 [!DNL Target] 按訪問者自動規範轉換度量，以 [!UICONTROL 自動分配] 活動，因此不必使用計算的度量來執行規範化。

### 自動分配 {#aa}

* **培訓頻率**: [!UICONTROL 自動分配] 模特們像往常一樣每小時訓練一次。
* **歸因模型**: [!DNL Target] 使用 [!DNL Adobe Analytics] 預設屬性模型[!UICONTROL  自動分配] 使用A4T的活動。
* **信心**:使用的置信公式 [!UICONTROL 自動分配] 活動與預設顯示的公式不同。 [!DNL Adobe Analytics] [!UICONTROL A4T] 的子菜單。 [如此處所述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 [!UICONTROL 自動分配] 比常規方法更保守 [!UICONTROL A/BTest] 活動。 這些保守的置信水準補償了對資料的反複評估（窺視）。 因此，中的預設報告 [!DNL Adobe Analytics] 顯示的置信區間比正在使用的區間窄 [!UICONTROL 自動分配] 算法。 但是，您可以確定哪些體驗受算法的青睞，基於哪些體驗會有更多獨特的訪問者被發送給它。
* **贏家狀態**:當前， [《尚未贏》和《贏家》徽章](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) 在 [!UICONTROL A4T] 面板 [!DNL Analysis Workspace]。 如果在中查看同一報告，則這些徽章也不可用 [!DNL Target]。 一枚獲獎的星章 [!DNL Target] 報告 [!UICONTROL 自動分配] 應忽略使用A4T的活動。 此徽章反映常規的置信度計算，而不是由 [!UICONTROL 自動分配]。

### 自動鎖定目標 {#at}

* [!UICONTROL 自動目標] 模型照常每24小時訓練一次。 但是，轉換事件資料來自 [!DNL Analytics] 延誤了6到24小時。 此延遲表示通信量的分配 [!DNL Target] 跟蹤記錄在 [!DNL Analytics]。 在活動初始激活後的頭48小時內，此延遲的影響最大。 此活動的效能將更加接近 [!DNL Analytics] 5天後的轉換行為。 考慮使用 [!UICONTROL 自動分配] 而不是 [!UICONTROL 自動目標] 短期活動，其中大多數流量在活動開始後的頭五天內發生。
* 使用時 [!DNL Analytics] 作為 [!UICONTROL 自動目標] 活動，會話在經過六小時後結束。 不計算六小時後發生的轉換。

有關詳細資訊，請參見 [屬性模型和回望窗口](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) 的 *分析工具指南*。

## 教程：如何在Analysis Workspace設定A4T報告以進行自動目標活動 {#tutorial}

儘管在中提供了豐富的分析功能 [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]，對預設值進行一些修改 [!UICONTROL 目標分析] 需要使用面板來正確解釋自動目標活動。 由於實驗活動(手動A/B和 [!UICONTROL 自動分配])和個性化活動([!UICONTROL 自動目標])。

本教程將指導您完成分析時建議的修改 [!UICONTROL 自動目標] 活動 [!UICONTROL 工作區]。

有關詳細資訊，請參見 [如何在Analysis Workspace設定A4T報告以進行自動目標活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) 在 *Adobe TargetTutorials*。

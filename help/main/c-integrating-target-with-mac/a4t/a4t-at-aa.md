---
keywords: a4t;A4T;使用 Analytics 作為 Target 的報告來源
description: 瞭解如何在Adobe中建立自動分配和自動目標活動 [!DNL Target] 將Analytics用作報告源(A4T)。
title: A4T是否支援自動分配和自動目標活動？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: e8fc28ef2497c1dfea523a769c9c817cbd74fea2
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 3%

---

# 自動分配和自動鎖定目標活動的 A4T 支援

的 [!DNL Adobe Target] — 到[!DNL Adobe Analytics] 整合，稱為 [目標分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)支援 [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 活動。

A4T整合允許您：

* 使用 [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)多武裝強盜駕車制勝經驗，
* 使用 [自動目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)整合機器學習算法為每個訪問者選擇最佳體驗。 Auto-Target在使用 [!DNL Adobe Analytics] 目標度量和 [!DNL Adobe Analytics]豐富的報告和分析能力。

確保你 [已實施A4T，用於A/BTest和經驗目標活動](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)。 如果您使用 `analyticsLogging = client_side`，您還必須通過 `sessionId` 值 [!DNL Analytics]。 有關詳細資訊，請參見 [目標(A4T)報告分析](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} *Adobe TargetSDK* 的子菜單。

若要開始執行:

1. 建立A/BTest活動時， **[!UICONTROL 目標]** 的 **[!UICONTROL 流量分配方法]**:

   * [!UICONTROL 自動分配以獲得最佳體驗]
   * [!UICONTROL 個性化體驗的自動目標]

   ![流量分配方法選項：手動、自動分配和自動目標](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   有關詳細資訊和逐步說明，請參見 [建立自動分配活動](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) 和 [建立自動目標活動](/help/main/c-activities/auto-target/create-auto-target.md)。

1. 選擇 **[!UICONTROL Adobe Analytics]** 為 **[!UICONTROL 報告源]** 的 **[!UICONTROL 目標和設定]** ，然後選擇與所需優化目標對應的報告套件。

   ![「目標和設定」頁上的「報告源」部分](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 選擇主要目標度量。 第一個下拉清單允許您在中指定目標 [!DNL Adobe Target] (然後將跟蹤 [!DNL Adobe Analytics] 作為度量「活動轉換」)，或 [!DNL Analytics] 作為目標。

   * 要使用 [!DNL Adobe Target] 要指定優化目標，請選擇 **[!UICONTROL 轉換]**，然後指定受眾必須執行的操作以指示已達到轉換目標。
   * 如果選擇 **[!UICONTROL 使用分析度量]**，然後將給您選擇應使用哪種類型的優化標準。  請參閱 [支援的目標度量和優化標準](#supported) 下面的。 指定優化條件後，可從中選擇相容度量 [!DNL Analytics] 作為優化目標。 您可以使用現成的 [!DNL Analytics] 轉換度量或 [!DNL Analytics] 自定義事件。


1. 保存並激活活動。

   [!UICONTROL 自動分配] 使用所選指標優化活動，使訪問者體驗最大化目標指標的體驗。

   或

   [!UICONTROL 自動目標] 使用所選指標來優化活動，從而推動訪問者獲得個性化的最佳體驗。

1. 使用 **[!UICONTROL 報告]** 頁籤，查看活動的報告並按一下 **[!UICONTROL 在分析中查看]** 在Adobe Analytics工作區中深入挖掘並進一步分段報告資料。 您可以按照以下教程查看如何在Worskpace中設定報告：
* 自動分配：見 [如何在Analysis Workspace設定A4T報告以進行自動分配活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) 在 *Adobe TargetTutorials*
* 自動目標：見 [如何在Analysis Workspace設定A4T報告以進行自動目標活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) 在 *Adobe TargetTutorials*。

## 支援的目標度量和優化標準 {#supported}

[!UICONTROL A4T] 為 [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 允許您選擇以下任意度量類型作為優化的主要目標度量：

* [!DNL Adobe Target] 轉換量度
* [!DNL Adobe Analytics] 轉換量度
* [!DNL Adobe Analytics] 個自訂事件

但是， [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 模型將優化 **歸一化** 這些度量的版本，具有完全標準化，具體取決於活動類型。 下表說明了每種活動類型的優化標準選項：

| 活動類型 | 度量源 | 優化准則 | 說明 |
|---------------|---------------|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 自動分配 | Analytics | 最大化唯一訪問者轉換率 | 模型嘗試查找具有最高唯一訪問者轉換率的「體驗」，該轉換率定義為分析度量為非零的訪問者數量除以訪問者總數（接收該體驗的訪問者）。 這意味著度量被視為二進位 — 對於活動中的每個唯一訪問者，為0或1。   如果您只關心執行特定操作的用戶比例，或者單個用戶的多個轉換事件沒有意義，則使用此選項。 |
| 自動分配 | 分析 | 最大化每個訪問者的度量值 | 模型嘗試查找每個訪問者具有最高度量值的體驗，該度量值定義為所有接觸該體驗的用戶的度量值總和除以接收該體驗的訪問者總數。 這意味著度量可以為活動中的每個唯一訪問者取任何值。 例如，如果訪問者進行多次轉換，則將計算每次轉換。  如果您對最大化連續度量（如總收入）感興趣，或者如果單個用戶的多個轉換事件比一個更有意義（例如，多個訂單的價值大於一個），請使用此選項 |
| 自動分配 | Target | （不可配置） | 該度量被視為二進位，並且使唯一訪問者轉換率最大化。 |
| 自動鎖定目標 | 分析 | 最大化唯一訪問轉換率 | 與自動分配或手動A/Btest不同，自動目標的個性化特性意味著訪問者在每次新訪問時看到的體驗都會發生變化。 然後，適當的速率是訪問歸一化轉換速率，其被定義為記錄非零度量的訪問的分數。 這是由自動目標優化的轉換率。   與「自動分配」類似，當您關心發生轉換的訪問次數時，應選擇此選項，即，當單個訪問發生多個轉換事件不重要時。 |
| 自動鎖定目標 | 分析 | 最大化每次訪問的度量值 | 當正針對優化的度量是連續的（例如收入），或當單個訪問中存在多個轉換事件是有意義的（例如多個訂單）時，您可以選擇將每次訪問的度量值最大化。 正在優化的&quot;比率&quot;是指度的總值，除以訪問次數。 |
| 自動鎖定目標 | 目標 | （不可配置） | 該度量被視為二進位，並且使唯一訪問轉換率最大化。 |



請注意，根據優化標準， [!DNL Adobe Analytics] 不支援度量。

* [!DNL Adobe Analytics] 不支援計算度量。
* [!DNL Adobe Analytics] 度量必須始終是可分割的，並且如果優化了每個訪問者/訪問者的值，則度量必須具有正極性（即正值比負值好）
* [!DNL Adobe Analytics] 使用的度量 [!DNL Auto-Target] 活動必須可用於DataWarehouse出口。

## 限制和說明

某些限制和注釋適用於兩者 [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 活動。 其它限制和注釋適用於一種活動類型或另一種活動類型。

### 自動分配和自動鎖定目標 {#both}

* 使用時 [!DNL Adobe Analytics] 作為 [!UICONTROL 自動分配] 或 [!UICONTROL 自動目標]，應始終查看報告 [!DNL Analytics]。
* 無法更改報告源 [!DNL Analytics] 至 [!DNL Target] 或者在激活某個活動之後。
* 雖然不支援將計算的度量作為主要目標度量，但通常可以通過選擇自定義事件作為主要目標度量來實現預期的結果。 例如，如果要優化度量，例如「每個訪問者的表單完成」，請選擇與「表單完成」對應的自定義事件作為主要目標度量。 如中所述 [支援的目標度量和優化標準](#supported)，取決於活動類型和優化標準， [!DNL Target] 將自動歸一化轉換度量，因此無需使用計算的度量來執行歸一化。


### 自動分配 {#aa}

* **培訓頻率**: [!UICONTROL 自動分配] 模特們像往常一樣每小時訓練一次。
* **歸因模型**: [!DNL Target] 使用 [!DNL Adobe Analytics] 預設屬性模型[!UICONTROL  自動分配] 使用A4T的活動。
* **信心**:使用的置信公式 [!UICONTROL 自動分配] 活動與預設顯示的公式不同。 [!DNL Adobe Analytics] [!UICONTROL A4T] 的子菜單。 [如此處所述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 [!UICONTROL 自動分配] 比常規方法更保守 [!UICONTROL A/BTest] 活動。 這些保守的置信水準補償了對資料的反複評估（窺視）。 因此，中的預設報告 [!DNL Adobe Analytics] 顯示的置信區間比正在使用的區間窄 [!UICONTROL 自動分配] 算法。 但是，您可以確定哪些體驗受算法的青睞，基於哪些體驗會有更多獨特的訪問者被發送給它。
* **贏家狀態**:當前， [《尚未贏》和《贏家》徽章](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) 在 [!UICONTROL A4T] 面板 [!DNL Analysis Workspace]。 如果在中查看同一報告，則這些徽章也不可用 [!DNL Target]。 一枚獲獎的星章 [!DNL Target] 報告 [!UICONTROL 自動分配] 應忽略使用A4T的活動。 此徽章反映常規的置信度計算，而不是由 [!UICONTROL 自動分配]。

### 自動鎖定目標 {#at}

* **培訓頻率**: [!UICONTROL 自動目標] 模型照常每24小時訓練一次。 但是，轉換事件資料來自 [!DNL Analytics] 延誤了6到24小時。 此延遲表示通信量的分配 [!DNL Target] 跟蹤記錄在 [!DNL Analytics]。 在活動初始激活後的頭48小時內，此延遲的影響最大。 此活動的效能將更加接近 [!DNL Analytics] 5天後的轉換行為。 考慮使用 [!UICONTROL 自動分配] 而不是 [!UICONTROL 自動目標] 短期活動，其中大多數流量在活動開始後的頭五天內發生。
* 使用時 [!DNL Analytics] 作為 [!UICONTROL 自動目標] 活動，會話在經過六小時後結束。 不計算六小時後發生的轉換。

有關詳細資訊，請參見 [屬性模型和回望窗口](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) 的 *分析工具指南*。

## 如何在Analysis Workspace設定A4T報告以進行自動目標和自動分配活動 {#tutorial}

儘管在中提供了豐富的分析功能 [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]，對預設值進行一些修改 [!UICONTROL 目標分析] 需要使用面板來正確解釋自動分配和自動目標活動。

由於中所述轉換率的細緻定義，需要作出這些修改 [支援的目標度量和優化標準](#supported)以及實驗活動(手動A/B和 [!UICONTROL 自動分配])和個性化活動([!UICONTROL 自動目標])。

這些教程將指導您瞭解建議的用於分析的修改 [!UICONTROL A4T] [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 活動 [!UICONTROL 工作區]。

如需詳細資訊，請參閱
* [如何在Analysis Workspace設定A4T報告以進行自動分配活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) 在 *Adobe TargetTutorials*。
* [如何在Analysis Workspace設定A4T報告以進行自動目標活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) 在 *Adobe TargetTutorials*。

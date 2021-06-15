---
keywords: a4t;A4T;使用 Analytics 作為 Target 的報告來源
description: 了解如何在以Analytics作為報表來源(A4T)的Adobe [!DNL Target] 中建立自動分配和自動鎖定目標活動。
title: A4T是否支援自動分配和自動鎖定目標活動？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 103ee22a4bf37569f8a02a91af194ebcdc79f3b4
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 3%

---

# 自動分配和自動鎖定目標活動的 A4T 支援

[!DNL Adobe Target]-to-[!DNL Adobe Analytics]整合(稱為[Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T))支援[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動。

A4T整合可讓您：

* 使用[自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)的多臂吃角子老虎機功能，將流量帶往勝出體驗。
* 使用[自動鎖定目標](/help/c-activities/auto-target/auto-target-to-optimize.md)的整體機器學習演算法來為每個訪客選擇最佳體驗。 自動鎖定目標會在使用[!DNL Adobe Analytics]目標量度和[!DNL Adobe Analytics]&#39;豐富的報表和分析功能時，根據使用者的設定檔、行為和內容選擇最佳體驗。

請確定您已實作[A4T以搭配A/B測試和體驗鎖定目標活動使用](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 如果您使用`analyticsLogging = client_side`，您也必須將`sessionId`值傳遞至[!DNL Analytics]。 如需詳細資訊，請參閱&#x200B;*Adobe Target SDK*&#x200B;指南中的[Analytics for Target(A4T)報表](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

若要開始執行:

1. 建立A/B測試活動時，在&#x200B;**[!UICONTROL Targeting]**&#x200B;頁面上，選取下列其中一個選項作為&#x200B;**[!UICONTROL 流量分配方法]**:

   * [!UICONTROL 自動分配至最佳體驗]
   * [!UICONTROL 針對個人化體驗自動鎖定目標]

   ![流量分配方法選項：手動、自動分配和自動鎖定目標](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   如需詳細資訊和逐步指示，請參閱[建立自動分配活動](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)和[建立自動鎖定目標活動](/help/c-activities/auto-target/create-auto-target.md)。

1. 在&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面上，為&#x200B;**[!UICONTROL 報表來源]**&#x200B;選取&#x200B;**[!UICONTROL Adobe Analytics]**，並選取與您所需的最佳化目標相對應的報表套裝。

   ![目標與設定頁面上的報表來源區段](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 選擇主要目標量度。

   * 若要使用[!DNL Adobe Target]來指定最佳化目標，請選擇&#x200B;**[!UICONTROL 轉換]** 。
   * 選擇&#x200B;**[!UICONTROL 使用Analytics量度]**，然後從[!DNL Analytics]中選取量度以用作最佳化目標。 您可以使用現成可用的[!DNL Analytics]轉換量度或[!DNL Analytics]自訂事件。

   如需詳細資訊，請參閱下方的[支援的目標量度](#supported)。

1. 儲存並啟動您的活動。

   [!UICONTROL 自動分配] 使用您選取的量度來最佳化活動，將訪客帶往可將目標量度最大化的體驗。

   或

   [!UICONTROL 自動鎖定目] 標使用您選取的量度來最佳化活動，進而推動訪客獲得個人化的最佳體驗。

1. 使用&#x200B;**[!UICONTROL Reports]**&#x200B;標籤，依您選擇的[!DNL Adobe Analytics]量度來檢視您活動的報表。 按一下「**[!UICONTROL 在Analytics中檢視]**」，深入探索並進一步區分您的報表資料。

## 支援的目標量度 {#supported}

[!UICONTROL A4] 自動 [!UICONTROL 分配] 和自動 [!UICONTROL 鎖定目] 標可讓您選擇下列任何量度類型，作為最佳化的主要目標量度：

* [!DNL Adobe Target] 轉換量度
* [!DNL Adobe Analytics] 轉換量度
* [!DNL Adobe Analytics] 個自訂事件

[!UICONTROL A4] 自動 [!UICONTROL 分配] 和自動 [!UICONTROL 鎖定目] 標需要您選擇以二項式事件為基礎的量度。二項式事件不發生或不發生。 二項式事件包括點按、轉換、訂單等。 這些類型的事件有時也稱為伯努利、二進位或離散事件。

[!UICONTROL 自動分] 配 [!UICONTROL 和自動] 鎖定 [!UICONTROL 目標的A4] 不支援連續量度的最佳化。持續量度包括收入、訂購的產品數、工作階段期間、工作階段中的頁面檢視次數等。 這些不支援的量度類型有時也稱為非二項式或非伯努利量度。

下列量度類型不支援作為主要目標量度：

* [!DNL Adobe Target] 參與與收入量度
* [!DNL Adobe Analytics] 參與與收入量度

   您可以選取[!DNL Analytics]參與或收入量度作為主要目標量度，因為[!DNL Target]無法識別並排除[!DNL Analytics]中的所有參與和收入量度。 從[!DNL Analytics]僅選取二項式轉換量度或自訂事件。

* [!DNL Adobe Analytics] 計算量度

## 限制和附註

有些限制和附註適用於[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動。 其他限制和附註適用於一個或另一個活動類型。

### 自動分配和自動鎖定目標

* 使用[!DNL Adobe Analytics]作為[!UICONTROL 自動分配]或[!UICONTROL 自動鎖定目標]的報表來源時，您應一律在[!DNL Analytics]中檢視報表。
* 報表來源無法從[!DNL Analytics]變更為[!DNL Target]，或在啟動活動後反之。
* 雖然計算量度不支援作為主要目標量度，但您通常可以改為選取自訂事件作為主要目標量度，以達到預期結果。 例如，如果您想針對「每位訪客表單完成次數」等量度進行最佳化，請選取與「表單完成次數」對應的自訂事件作為主要目標量度。 [!DNL Target] 根據每次造訪自動標準化轉換量度，以考慮不均勻的流量分佈，因此不需要使用計算量度來執行標準化。
* [!DNL Target] 使用自動分配功能中的「同一次接觸」歸 [!UICONTROL 因模] 型：目標分析(A4T)。

### 自動分配

* [!UICONTROL 自動分] 配模型照常每兩小時進行一次培訓。

### 自動鎖定目標

* [!UICONTROL 自動鎖] 定目標模型照常每24小時進行一次訓練。不過，來自[!DNL Analytics]的轉換事件資料會額外延遲6到24小時。 此延遲表示[!DNL Target]所分配的流量會跟蹤[!DNL Analytics]中記錄的最新事件。 此延遲在活動初始啟動後的前48小時內有最大的影響。 活動的效能將更密切地反映5天後的[!DNL Analytics]轉換行為。 請考慮對於短期活動使用[!UICONTROL 自動分配]而非[!UICONTROL 自動鎖定目標]，其中大部分流量發生在活動生命週期的前五天內。
* 使用[!DNL Analytics]作為[!UICONTROL 自動鎖定目標]活動的資料來源時，工作階段會在6小時後結束。 六小時後發生的轉換不會計算。

如需詳細資訊，請參閱&#x200B;*Analytics工具指南*&#x200B;中的[歸因模型與回顧期間](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)。

## 教學課程：如何在Analysis Workspace中設定A4T報表以用於自動鎖定目標活動 {#tutorial}

雖然[!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]中提供豐富分析功能，但若要正確解譯自動鎖定目標活動，需對預設[!UICONTROL  Analytics for Target]面板進行一些修改。 由於實驗活動（手動A/B和[!UICONTROL 自動分配]）與個人化活動（[!UICONTROL 自動鎖定目標]）之間的差異，因此需要進行這些修改。

本教學課程會逐步引導您了解在[!UICONTROL Workspace]中分析[!UICONTROL 自動鎖定目標]活動的建議修改。

如需詳細資訊，請參閱&#x200B;*Adobe TargetTutorials*&#x200B;中的[如何在Analysis Workspace中為自動鎖定目標活動設定A4T報表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html)。

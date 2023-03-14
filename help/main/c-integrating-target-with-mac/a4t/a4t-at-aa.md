---
keywords: a4t;A4T;使用 Analytics 作為 Target 的報告來源
description: 了解如何建立 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動 [!DNL Target] 使用 [!DNL Analytics] 作為報表來源(A4T)時啟用。
title: A4T支援嗎 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: tm+mt
source-wordcount: '1292'
ht-degree: 5%

---

# [!UICONTROL 自動分配和自動鎖定目標活動的 A4T 支援]

此 [!DNL Adobe Target] — 到 — [!DNL Adobe Analytics] 整合，稱為 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)支援 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動。

A4T整合可讓您：

* 使用 [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)的多臂吃角子老虎機功能，可將流量帶往獲勝的體驗。
* 使用 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)的整體機器學習演算法，可為每個訪客選擇最佳體驗。 [!UICONTROL 自動鎖定目標] 在使用 [!DNL Adobe Analytics] 目標量度和 [!DNL Adobe Analytics]「豐富的報告和分析功能。

請確定您 [實作A4T以搭配A/B測試和體驗鎖定目標活動使用](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). 如果您使用 `analyticsLogging = client_side`，您也必須傳遞 `sessionId` 值 [!DNL Analytics]. 如需詳細資訊，請參閱 [Analytics for Target(A4T)報表](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} 在 *Adobe Target SDK* 指南。

若要開始執行:

1. 建立 [!UICONTROL A/B測試] 活動，在 **[!UICONTROL 定位]** 頁面中，選擇以下選項之一作為 **[!UICONTROL 流量分配方法]**:

   * [!UICONTROL 自動分配至最佳體驗]
   * [!UICONTROL 針對個人化體驗自動鎖定目標]

   ![流量分配方法選項：手動、自動分配和自動鎖定目標](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   如需詳細資訊和逐步指示，請參閱 [建立自動分配活動](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) 和 [建立自動鎖定目標活動](/help/main/c-activities/auto-target/create-auto-target.md).

1. 選擇 **[!UICONTROL Adobe Analytics]** 為 **[!UICONTROL 報表來源]** 在 **[!UICONTROL 目標與設定]** 頁面，然後選取與您所需的最佳化目標相對應的報表套裝。

   ![目標與設定頁面上的報表來源區段](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 選擇 [!UICONTROL 主要目標] 量度。

   * 使用 [!DNL Adobe Target] 要指定優化目標，請選擇 **[!UICONTROL 轉換]** .
   * 選擇 **[!UICONTROL 使用Analytics量度]** 然後選取量度 [!DNL Analytics] 作為最佳化目標。 您可以使用現成可用的 [!DNL Analytics] 轉換量度或 [!DNL Analytics] 自訂事件。

   請參閱 [支援的目標量度](#supported) 以取得詳細資訊。

1. 儲存並啟動您的活動。

   [!UICONTROL 自動分配] 使用您選取的量度來最佳化活動，將訪客帶往可將目標量度最大化的體驗。

   或

   [!UICONTROL 自動鎖定目標] 使用您選取的量度來最佳化活動，將訪客帶往個人化的最佳體驗。

1. 使用 **[!UICONTROL 報表]** 索引標籤來檢視活動的報表，依您選擇 [!DNL Adobe Analytics] 量度。 按一下 **[!UICONTROL 在Analytics中檢視]** 深入深入和進一步劃分您的報表資料。

## 支援的目標量度 {#supported}

[!UICONTROL A4T] for [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 可讓您選擇下列任何量度類型，作為最佳化的主要目標量度：

* [!DNL Adobe Target] 轉換量度
* [!DNL Adobe Analytics] 轉換量度
* [!DNL Adobe Analytics] 個自訂事件

[!UICONTROL A4T] for [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 需要您選擇以二項式事件為基礎的量度。 二項式事件不發生或不發生。 二項式事件包括點按、轉換、訂單等。 這些類型的事件有時也稱為伯努利、二進位或離散事件。

[!UICONTROL A4T] for [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 不支援持續量度的最佳化。 持續量度包括收入、訂購的產品數、工作階段期間、工作階段中的頁面檢視次數等。 這些不支援的量度類型有時也稱為非二項式或非伯努利量度。

下列量度類型不支援作為主要目標量度：

* [!DNL Adobe Target] 參與與收入量度
* [!DNL Adobe Analytics] 參與與收入量度

   您可以選取 [!DNL Analytics] 參與或收入量度作為主要目標量度，因為 [!DNL Target] 無法識別和排除 [!DNL Analytics]. 僅選取「二項式」轉換量度或自訂事件 [!DNL Analytics].

* [!DNL Adobe Analytics] 計算量度

## 限制和附註

部分限制和附註適用於兩者 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動。 其他限制和附註適用於一個或另一個活動類型。

### 自動分配和自動鎖定目標 {#both}

* 使用時 [!DNL Adobe Analytics] 作為的報表來源 [!UICONTROL 自動分配] 或 [!UICONTROL 自動鎖定目標]時，您應一律在 [!DNL Analytics].
* 無法從 [!DNL Analytics] to [!DNL Target] 或在活動啟動後反之。
* 雖然計算量度不支援作為主要目標量度，但您通常可以改為選取自訂事件作為主要目標量度，以達到預期結果。 例如，如果您想針對「每位訪客表單完成次數」等量度進行最佳化，請選取與「表單完成次數」對應的自訂事件作為主要目標量度。 [!DNL Target] 根據每次造訪自動標準化轉換量度，以考慮不均勻的流量分佈，因此不需要使用計算量度來執行標準化。
* 使用時 [!DNL Adobe Analytics] 作為的報表來源 [!UICONTROL 自動分配] 或 [!UICONTROL 自動鎖定目標] 活動時，您應一律檢視報表 [!DNL Analytics].
* 無法從 [!DNL Analytics] to [!DNL Target] 或在活動啟動後反之。
* 雖然計算量度不支援作為主要目標量度，但您通常可以改為選取自訂事件作為主要目標量度，以達到預期結果。 例如，如果您想針對「每位訪客表單完成次數」等量度進行最佳化，請選取與「表單完成次數」對應的自訂事件作為主要目標量度。 [!DNL Target] 依每位訪客自動標準化轉換量度， [!UICONTROL 自動分配] 活動，因此不需要使用計算量度來執行標準化。

### 自動分配 {#aa}

* **訓練頻率**: [!UICONTROL 自動分配] 照常，模型繼續每小時進行訓練。
* **歸因模型**: [!DNL Target] 使用 [!DNL Adobe Analytics] 預設歸因模型[!UICONTROL  自動分配] 使用A4T的活動。
* **信賴度**:使用的信賴公式 [!UICONTROL 自動分配] 活動與中預設顯示的公式不同， [!DNL Adobe Analytics] [!UICONTROL A4T] 中。 [如此處所述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL 自動分配] 使用比規則更保守的信賴區間 [!UICONTROL A/B測試] 活動。 這些保守的信賴水準可補償資料的重複評估（窺視）。 因此， [!DNL Adobe Analytics] 會顯示較所用的信賴區間窄 [!UICONTROL 自動分配] 演算法。 不過，您可以根據哪些體驗會傳送更多不重複訪客給該體驗，來判斷演算法青睞哪個體驗。
* **獲勝者狀態**:目前， [「尚未有贏家」和「贏家」徽章](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) 在 [!UICONTROL A4T] 面板 [!DNL Analysis Workspace]. 若在中檢視相同報表，則這些徽章也無法使用 [!DNL Target]. 優勝者「星號」徽章顯示於 [!DNL Target] 報表 [!UICONTROL 自動分配] 應忽略使用A4T的活動。 此徽章會反映一般信賴計算，而非 [!UICONTROL 自動分配].

### 自動鎖定目標 {#at}

* [!UICONTROL 自動鎖定目標] 照常，模型每24小時繼續訓練一次。 不過，轉換事件資料來自 [!DNL Analytics] 多延六至二十四小時。 此延遲表示流量的分配方式 [!DNL Target] 會追蹤 [!DNL Analytics]. 此延遲在活動初始啟動後的前48小時內有最大的影響。 活動的效能反映得更為密切 [!DNL Analytics] 5天後的轉換行為。

   請考慮使用 [!UICONTROL 自動分配] 而非 [!UICONTROL 自動鎖定目標] 短期活動中，大部分流量都發生在活動生命週期的前五天內。

* 使用時 [!DNL Analytics] 作為 [!UICONTROL 自動鎖定目標] 活動，工作階段會在6小時後結束。 六小時後發生的轉換不會計算。

如需詳細資訊，請參閱 [歸因模型與回顧期間](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) 在 *Analytics工具指南*.

## 教學課程

雖然 [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]，對預設值進行一些修改 [!UICONTROL Analytics for Target] 需要面板才能正確解譯 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動。 由於實驗活動(手動A/B和 [!UICONTROL 自動分配])和個人化活動([!UICONTROL 自動鎖定目標])。

### 在 [!DNL Analysis Workspace] 中設定[!UICONTROL 自動分配]活動的 A4T 報告

本教學課程會逐步引導您了解分析時的建議修改 [!UICONTROL 自動分配] 活動 [!DNL Analysis Workspace].

如需詳細資訊，請參閱 [如何在Analysis Workspace中設定A4T報表以用於自動分配活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank} in *Adobe TargetTutorials*.

### 在 [!DNL Analysis Workspace] 中設定[!UICONTROL 自動鎖定目標]活動的 A4T 報告

本教學課程會逐步引導您了解分析時的建議修改 [!UICONTROL 自動鎖定目標] 活動 [!DNL Analysis Workspace].

如需詳細資訊，請參閱 [如何在Analysis Workspace中設定A4T報表以用於自動鎖定目標活動](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank} in *Adobe TargetTutorials*.



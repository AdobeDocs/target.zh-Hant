---
keywords: a4t；A4T；Analytics作為Target的報表來源；Analytics for Target
description: 瞭解如何建立 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 中的活動 [!DNL Target] 使用 [!DNL Analytics] 作為報表來源(A4T)。
title: A4T是否支援 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 99bd509988a7d1545a6a1fe59aa59f35ef0a7d11
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 7%

---

# [!UICONTROL 自動分配和自動鎖定目標活動的 A4T 支援]

此 [!DNL Adobe Target]-to-[!DNL Adobe Analytics] 整合，稱為 [目標分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，支援 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動。

A4T整合可讓您：

* 使用 [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) 多臂吃角子老虎機功能，可將流量引導至成功體驗。
* 使用 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 整合機器學習演演算法，為每位訪客選擇最佳體驗。 [!UICONTROL 自動鎖定目標] 根據每位使用者的個人資料、行為和內容選擇最佳體驗，同時使用 [!DNL Adobe Analytics] 目標量度與的豐富報告和分析功能 [!DNL Adobe Analytics].

確定您擁有 [實作A4T以用於A/B測試和體驗鎖定目標活動](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). 如果您使用 `analyticsLogging = client_side`，您也必須傳遞 `sessionId` 值至 [!DNL Analytics]. 如需詳細資訊，請參閱 [Analytics for Target (A4T)報表](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} 在 *Adobe Target開發人員指南*.

若要開始執行:

1. 當 [建立 [!UICONTROL A/B測試] 活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)，位於 **[!UICONTROL 目標定位]** 頁面，選取下列其中一個選項作為 **[!UICONTROL 流量分配方法]**：

   * [!UICONTROL 自動分配至最佳體驗]
   * [!UICONTROL 針對個人化體驗自動鎖定目標]

   ![流量分配方法選項：手動、自動分配和自動鎖定目標](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   如需詳細資訊和逐步指示，請參閱 [建立自動分配活動](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) 和 [建立自動鎖定目標活動](/help/main/c-activities/auto-target/create-auto-target.md).

1. 選取 **[!UICONTROL Adobe Analytics]** 您的 **[!UICONTROL 報表來源]** 於 **[!UICONTROL 目標與設定]** 頁面，並選取與您所需最佳化目標對應的報表套裝。

   ![「目標與設定」頁面上的「報表來源」區段](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 選擇 [!UICONTROL 主要目標] 量度。

   * 使用 [!DNL Adobe Target] 若要指定最佳化目標，請選擇 **[!UICONTROL 轉換]** .
   * 選擇 **[!UICONTROL 使用Analytics度量]** 然後從中選取量度 [!DNL Analytics] 以作為最佳化目標。 您可以使用現成可用的 [!DNL Analytics] 轉換量度或 [!DNL Analytics] 自訂事件。

   另請參閱 [支援的目標量度](#supported) 詳細資訊，請參閱下文。

1. 儲存並啟動您的活動。

   [!UICONTROL 自動分配] 會使用您選取的量度來最佳化活動，將訪客引導至最大化目標量度的體驗。

   或

   [!UICONTROL 自動鎖定目標] 使用您選取的量度來最佳化活動，促使訪客獲得個人化的最佳體驗。

1. 使用 **[!UICONTROL 報表]** 標籤來檢視活動的報表，依據您選擇的選項 [!DNL Adobe Analytics] 量度。 按一下 **[!UICONTROL 在Analytics中檢視]** 以深入剖析並進一步細分您的報告資料。

## 支援的目標量度 {#supported}

[!UICONTROL A4T] 的 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 可讓您選擇下列任何量度型別作為最佳化的主要目標量度：

* [!DNL Adobe Target] 轉換量度
* [!DNL Adobe Analytics] 轉換量度
* [!DNL Adobe Analytics] 個自訂事件

[!DNL Target]可讓您在為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動使用 [!UICONTROL A4T] 時，選擇以二項式事件為基礎的量度，或是以持續事件為基礎的量度。

* **根據二項式事件的量度**：二項式事件不會發生。 二項式事件包括點選、轉換、訂購等。 這類事件有時也稱為Bernoulli、二進位或分散式事件。

* **以連續事件為基礎的量度**. 持續量度包括收入、訂購的產品數量、工作階段持續時間、工作階段中的頁面檢視數量等。 這類事件有時也稱為非二項式或非伯努利量度。

>[!IMPORTANT]
>
>截至 [!DNL Adobe Target Standard/Premium] 22.15.1版（2023年3月8日和9日）， [!DNL Target] 會使用目前不支援的量度來持續支援現有活動（列於下表中）。 但是，在2023年9月9日之後，現有活動將不再支援這些量度，並將停止所有使用不支援量度的活動，以強制現有活動移轉至新行為。

### 對的影響 [!UICONTROL 自動分配] 活動

| 量度名稱 | 不再支援： |
| --- | --- |
| [!UICONTROL averagepagedepth] | 轉換率，最大化量度值 |
| [!UICONTROL averagetimespentonsite] | 轉換率，最大化量度值 |
| [!UICONTROL 彈回建立] | 轉換率，最大化量度值 |
| [!UICONTROL bounces] | 轉換率，最大化量度值 |
| [!UICONTROL 個專案] | 轉換率，最大化量度值 |
| [!UICONTROL 退出點] | 轉換率，最大化量度值 |
| [!UICONTROL 頁面檢視] | 最大化量度值 |
| [!UICONTROL 重新載入] | 最大化量度值 |
| [!UICONTROL 訪客] | 轉換率，最大化量度值 |
| [!UICONTROL 瀏覽次數] | 最大化量度值 |

### 對的影響 [!UICONTROL 自動鎖定目標] 活動

| 量度名稱 | 不再支援： |
| --- | --- |
| [!UICONTROL cartremovals] | 最大化量度值 |
| [!UICONTROL 頁面檢視] | 最大化量度值 |
| [!UICONTROL 訪客] | 轉換率，最大化量度值 |
| [!UICONTROL 瀏覽次數] | 最大化量度值 |

## 限制和備註

部分限制和附註同時適用於兩者 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動。 其他限制和附註適用於一種活動型別。

### 自動分配和自動鎖定目標 {#both}

* 使用時 [!DNL Adobe Analytics] 作為的報表來源 [!UICONTROL 自動分配] 或 [!UICONTROL 自動鎖定目標]，請一律檢視以下專案的報表： [!DNL Analytics].
* 報表來源不能從 [!DNL Analytics] 至 [!DNL Target] 在活動啟動後，反之亦然。
* 雖然計算量度不支援作為主要目標量度，但通常可以透過選擇自訂事件作為主要目標量度來達到預期結果。 例如，如果您想要針對「每位訪客的表單完成數」等量度最佳化，請選取與「表單完成數」對應的自訂事件作為主要目標量度。 [!DNL Target] 會根據每次造訪自動標準化轉換量度，以處理不均衡的流量分佈，因此不需要使用計算量度來執行標準化。

### 自動分配 {#aa}

* **訓練頻率**： [!UICONTROL 自動分配] 一如往常，模型繼續每小時訓練一次。
* **歸因模型**： [!DNL Target] 使用 [!DNL Adobe Analytics] 預設歸因模型[!UICONTROL  自動分配] 使用A4T的活動。
* **信賴度**：使用的信賴度公式 [!UICONTROL 自動分配] 活動與中預設顯示的公式不同 [!DNL Adobe Analytics] [!UICONTROL A4T] 面板。 [如這裡所述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)， [!UICONTROL 自動分配] 使用比一般更保守的信賴區間 [!UICONTROL A/B測試] 活動。 這些保守的信賴等級可補償資料的反複評估（窺視）。 因此，中的預設報表 [!DNL Adobe Analytics] 顯示較下列專案所使用的那些區間更窄的信賴區間： [!UICONTROL 自動分配] 演演算法。 不過，您可以根據傳送給哪個體驗的獨特訪客更多，來判斷演演算法偏好的體驗。
* **獲勝者狀態**：目前， [「尚未有贏家」和「贏家」徽章](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) 不可用於 [!UICONTROL A4T] 面板於 [!DNL Analysis Workspace]. 如果在中檢視相同的報表，則也無法使用這些徽章 [!DNL Target]. 中顯示的贏家「明星」徽章 [!DNL Target] 報告 [!UICONTROL 自動分配] 應該忽略使用A4T的活動。 此徽章反映的是常規可信度計算，而不是使用者使用的計算。 [!UICONTROL 自動分配].

### 自動鎖定目標 {#at}

* [!UICONTROL 自動鎖定目標] 一如往常，模型會持續訓練每24小時。 不過，轉換事件資料來自 [!DNL Analytics] 會額外延遲6至24小時。 此延遲表示流量分配依據 [!DNL Target] 追蹤中記錄的最新事件 [!DNL Analytics]. 此延遲在活動初次啟動後的前48小時內影響最大。 活動的效能會更密切地反映出來 [!DNL Analytics] 經過5天後的轉換行為。

   考慮使用 [!UICONTROL 自動分配] 而非 [!UICONTROL 自動鎖定目標] 適用於大多數流量發生在活動期限前五天的短期活動。

* 使用時 [!DNL Analytics] 作為 [!UICONTROL 自動鎖定目標] 活動，工作階段會在六小時後結束。 六小時後發生的轉換不會計算在內。

如需詳細資訊，請參閱 [歸因模型與回顧期間](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) 在 *Analytics工具指南*.

## 教學課程

雖然中提供了豐富的分析功能， [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]，對預設值進行了一些修改 [!UICONTROL 目標分析] 需要面板才能正確解譯 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動。 由於實驗活動(手動A/B和 [!UICONTROL 自動分配])和個人化活動([!UICONTROL 自動鎖定目標])。

### 在 [!DNL Analysis Workspace] 中設定[!UICONTROL 自動分配]活動的 A4T 報告

本教學課程將逐步引導您瞭解建議的修改內容，以便進行分析 [!UICONTROL 自動分配] 中的活動 [!DNL Analysis Workspace].

如需詳細資訊，請參閱 [如何在Analysis Workspace中為自動分配活動設定A4T報表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank} 在 *Adobe TargetTutorials*.

### 在 [!DNL Analysis Workspace] 中設定[!UICONTROL 自動鎖定目標]活動的 A4T 報告

本教學課程將逐步引導您瞭解建議的修改內容，以便進行分析 [!UICONTROL 自動鎖定目標] 中的活動 [!DNL Analysis Workspace].

如需詳細資訊，請參閱 [如何在Analysis Workspace中為自動鎖定目標活動設定A4T報表](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank} 在 *Adobe TargetTutorials*.



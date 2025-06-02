---
keywords: a4t；A4T；Analytics作為Target的報表來源；Analytics for Target
description: 瞭解如何在 [!DNL Target] 中建立使用 [!DNL Analytics] 作為報告來源(A4T)的[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動。
title: A4T是否支援[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: ddced04c730519dae74e70a60bed26462825ad23
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 4%

---

# [!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動的A4T支援

[!DNL Adobe Target]至[!DNL Adobe Analytics]整合(稱為[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T))支援[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動。

A4T整合可讓您：

* 使用[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) multi-armed Bandit功能將流量引導至成功體驗。
* 使用[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)整體機器學習演演算法，為每位訪客選擇最佳體驗。 [!UICONTROL Auto-Target]會根據每位使用者的設定檔、行為和內容來選擇最佳體驗，同時使用[!DNL Adobe Analytics]目標量度和[!DNL Adobe Analytics]的豐富報告和分析功能。

確定您已實施[搭配A/B測試和體驗鎖定目標活動使用的A4T](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)。 如果您使用`analyticsLogging = client_side`，也必須將`sessionId`值傳遞給[!DNL Analytics]。 如需詳細資訊，請參閱&#x200B;*Adobe Target開發人員指南*&#x200B;中的[Analytics for Target (A4T)報告](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html?lang=zh-Hant){target=_blank}。

若要開始執行:

1. 在[建立[!UICONTROL A/B Test]活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)時，請在&#x200B;**[!UICONTROL Targeting]**&#x200B;頁面上按一下&#x200B;**[!UICONTROL Traffic Allocation]**&#x200B;控制項，然後在右窗格中選擇所需的流量分配方法。

   ![流量分配方法設定](/help/main/c-activities/assets/auto-target.png)

   下列為可用的流量分配方法：

   * **[!UICONTROL Manual (Default)]**：指定您希望在各體驗上看見的加入者百分比。 您可以在所有體驗之間分割百分比，或對每個體驗指定較高或較低的百分比。所有體驗的總計必須等於 100%。

   * **[!UICONTROL Auto-Allocate to best experience]**：系統會自動將多數活動加入者導向表現較佳的體驗。 有些訪客會被分配至所有體驗，以保持能夠利用體驗並且可識別效能趨勢中的變更。如需詳細資訊，請參閱[[!UICONTROL Auto-Allocate]總覽](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

   * **[!UICONTROL Auto-Target for personalized experiences]**： [!DNL Target]會使用進階機器學習來個人化內容，並透過識別多個高效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。 如需詳細資訊，請參閱[自動鎖定目標總覽](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。

   如需詳細資訊和逐步指示，請參閱[建立自動分配活動](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)和[建立自動鎖定目標活動](/help/main/c-activities/auto-target/create-auto-target.md)。

1. 在「**[!UICONTROL Goals & Settings]**」頁面上，為您的&#x200B;**[!UICONTROL Reporting Source]**&#x200B;選取「**[!UICONTROL Adobe Analytics]**」，並選取與您想要的最佳化目標對應的公司和報表套裝。

   目標與設定頁面上的![報告Source區段](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 指定追蹤伺服器和沙箱。

1. 選擇[!UICONTROL Primary Goal]量度。

   * 若要使用[!DNL Adobe Target]來指定最佳化目標，請選擇&#x200B;**[!UICONTROL Conversion]** 。
   * 選擇&#x200B;**[!UICONTROL Use an Analytics metric]**，然後從[!DNL Analytics]中選取要作為最佳化目標的量度。 您可以使用現成的[!DNL Analytics]轉換量度或[!DNL Analytics]自訂事件。

   如需詳細資訊，請參閱下方的[支援的目標量度](#supported)。

1. 儲存並啟動您的活動。

   [!UICONTROL Auto-Allocate]會使用您選取的量度來最佳化活動，將訪客引導至最大化目標量度的體驗。

   或

   [!UICONTROL Auto-Target]會使用您選取的量度來最佳化活動，將訪客引導至個人化的最佳體驗。

1. 使用&#x200B;**[!UICONTROL Reports]**&#x200B;索引標籤，依您選擇的[!DNL Adobe Analytics]量度檢視活動的報表。 按一下「**[!UICONTROL View in Analytics]**」以深入分析並進一步細分您的報告資料。

## 支援的目標量度 {#supported}

[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]的[!UICONTROL A4T]可讓您選擇下列任何量度型別作為最佳化的主要目標量度：

* [!DNL Adobe Target]個轉換量度
* [!DNL Adobe Analytics]個轉換量度
* [!DNL Adobe Analytics]個自訂事件

>[!NOTE]
>
>選取[!UICONTROL Use an Analytics Metric]之後，選取[!UICONTROL Maximize Unique Visitor Conversion Rate]以檢視可用的[!DNL Adobe Analytics]個轉換量度，並選取[!UICONTROL Maximize Metric Value per Visitor]以探索[!DNL Adobe Analytics]個自訂事件。

針對[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動使用[!UICONTROL A4T]時，[!DNL Target]可讓您根據二項式事件選擇量度，或根據連續事件選擇量度。

* **以二項式事件為基礎的量度**：二項式事件不會發生。 二項式事件包括點選、轉換、訂購等。 這些型別的事件有時也稱為Bernoulli、二進位或離散事件。

* **以連續事件為基礎的量度**。 持續量度包括收入、訂購的產品數量、工作階段持續時間、工作階段中的頁面檢視數量等。 這些型別的事件有時也稱為非二項式或非伯努利量度。

>[!IMPORTANT]
>
>自[!DNL Adobe Target Standard/Premium] 22.15.1版（2023年3月8日至9日）起，[!DNL Target]持續支援現有活動，但量度目前不支援（如下表所列）。 但是，在2023年9月9日之後，這些量度將不再受現有活動的支援，並將停止所有使用不支援量度的活動，以強制現有活動遷移至新行為。

### 對[!UICONTROL Auto-Allocate]個活動的影響

| 量度名稱 | 不再支援： |
| --- | --- |
| [!UICONTROL averagepagedepth] | 轉換率，量度值最大化 |
| [!UICONTROL averagetimespentonsite] | 轉換率，量度值最大化 |
| [!UICONTROL bouncerate] | 轉換率，量度值最大化 |
| [!UICONTROL bounces] | 轉換率，量度值最大化 |
| [!UICONTROL entries] | 轉換率，量度值最大化 |
| [!UICONTROL exits] | 轉換率，量度值最大化 |
| [!UICONTROL pageviews] | 最大化量度值 |
| [!UICONTROL reloads] | 最大化量度值 |
| [!UICONTROL visitors] | 轉換率，量度值最大化 |
| [!UICONTROL visits] | 最大化量度值 |

### 對[!UICONTROL Auto-Target]個活動的影響

| 量度名稱 | 不再支援： |
| --- | --- |
| [!UICONTROL cartremovals] | 最大化量度值 |
| [!UICONTROL pageviews] | 最大化量度值 |
| [!UICONTROL visitors] | 轉換率，量度值最大化 |
| [!UICONTROL visits] | 最大化量度值 |

## 限制和備註

某些限制和附註同時適用於[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動。 其他限制和附註適用於一種活動型別或另一種活動型別。

### 自動分配和自動鎖定目標 {#both}

* 使用[!DNL Adobe Analytics]做為[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target]的報告來源時，您應該一律在[!DNL Analytics]中檢視報告。
* 在活動啟動後，無法將報表來源從[!DNL Analytics]變更為[!DNL Target]，反之亦然。
* 雖然計算量度不支援作為主要目標量度，但通常可以透過選取自訂事件作為主要目標量度來達到預期結果。 例如，如果您想要最佳化量度（例如「每位訪客的表單完成數」），請選取與「表單完成數」對應的自訂事件作為主要目標量度。 [!DNL Target]會根據每次造訪自動標準化轉換量度，以考慮不平均的流量分佈，因此不需要使用計算量度來執行標準化。

### 自動分配 {#aa}

* **訓練頻率**： [!UICONTROL Auto-Allocate]模型繼續像往常一樣每小時訓練一次。
* **歸因模型**： [!DNL Target]針對使用A4T的[!UICONTROL &#x200B; Auto-Allocate]個活動使用[!DNL Adobe Analytics]預設歸因模型。
* **信賴度**： [!UICONTROL Auto-Allocate]活動使用的信賴度公式與[!DNL Adobe Analytics] [!UICONTROL A4T]面板中預設顯示的公式不同。 [如這裡所述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)，[!UICONTROL Auto-Allocate]使用比一般[!UICONTROL A/B Test]活動更保守的信賴區間。 這些保守的信賴等級可補償重複評估（窺視）資料。 因此，[!DNL Adobe Analytics]中的預設報表顯示的信賴區間會比[!UICONTROL Auto-Allocate]演演算法所使用的區間窄。 不過，您可以根據傳送給哪個體驗的獨特訪客多於哪個體驗，來決定演演算法偏好的體驗。
* **獲勝者狀態**：目前[!DNL Analysis Workspace]中的[!UICONTROL A4T]面板無法使用[「尚未有獲勝者」和「獲勝者」徽章](/help/main/c-activities/automated-traffic-allocation/determine-winner.md)。 如果在[!DNL Target]中檢視相同的報表，則也無法使用這些徽章。 使用A4T的[!UICONTROL Auto-Allocate]活動在[!DNL Target]報告中顯示的獲勝者「星星」徽章應予以忽略。 此徽章反映的是常規可信度計算，而不是[!UICONTROL Auto-Allocate]使用的計算。

### 自動鎖定目標 {#at}

* [!UICONTROL Auto-Target]模型一如往常每24小時訓練一次。 不過，來自[!DNL Analytics]的轉換事件資料會額外延遲6至24小時。 此延遲表示[!DNL Target]的流量分配會追蹤[!DNL Analytics]中記錄的最新事件。 此延遲在活動初次啟動後的前48小時內影響最大。 活動效能在5天後更密切地反映[!DNL Analytics]轉換行為。

  考慮針對大多數流量發生在活動期限前五天的短期活動，使用[!UICONTROL Auto-Allocate]而非[!UICONTROL Auto-Target]。

* 使用[!DNL Analytics]做為[!UICONTROL Auto-Target]活動的資料來源時，工作階段會在六小時後結束。 六小時後發生的轉換則不會計算在內。

如需詳細資訊，請參閱&#x200B;*Analytics工具指南*&#x200B;中的[歸因模型和回顧期間](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=zh-Hant)。

## 教學課程

雖然[!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]中提供了豐富的分析功能，但必須修改預設[!UICONTROL Analytics for Target]面板，才能正確解譯[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動。 由於實驗活動（手動A/B和[!UICONTROL Auto-Allocate]）和個人化活動([!UICONTROL Auto-Target])之間的差異，需要這些修改。

### 在[!DNL Analysis Workspace]中為[!UICONTROL Auto-Allocate]個活動設定A4T報告

本教學課程將逐步引導您瞭解在[!DNL Analysis Workspace]中分析[!UICONTROL Auto-Allocate]個活動的建議修改。

如需詳細資訊，請參閱&#x200B;*Adobe Target教學課程*&#x200B;中的[如何在Analysis Workspace中為自動分配活動設定A4T報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=zh-Hant){target=_blank}。

### 在[!DNL Analysis Workspace]中為[!UICONTROL Auto-Target]個活動設定A4T報告

本教學課程將逐步引導您瞭解在[!DNL Analysis Workspace]中分析[!UICONTROL Auto-Target]個活動的建議修改。

如需詳細資訊，請參閱&#x200B;*Adobe Target教學課程*&#x200B;中的[如何在Analysis Workspace中為自動鎖定目標活動設定A4T報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=zh-Hant){target=_blank}。



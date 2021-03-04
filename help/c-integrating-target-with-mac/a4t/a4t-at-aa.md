---
keywords: a4t;A4T;使用 Analytics 作為 Target 的報告來源
description: 瞭解如何在Adobe Target建立使用Analytics作為報告來源(A4T)的「自動分配」和「自動目標」活動。
title: A4T是否支援自動分配和自動定位活動？
feature: 目標分析 (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 3%

---


# A4T支援自動分配和自動定位活動

[!DNL Adobe Target]-to-[!DNL Adobe Analytics]整合，稱為[Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T)支援[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動。

A4T整合可讓您：

* 使用[自動配置](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)的多武裝強盜功能，將流量帶入成功體驗。
* 使用[Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md)的整合機器學習演算法，為每個訪客選擇最佳體驗。 Auto-Target會根據使用者的設定檔、行為和內容選擇最佳體驗，同時使用[!DNL Adobe Analytics]目標量度和[!DNL Adobe Analytics]的豐富報表和分析功能。

請確定您已實作[ A4T，以便與A/B測試和體驗定位活動](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)搭配使用。 如果您使用`analyticsLogging = client_side`，則還必須將`sessionId`值傳遞至[!DNL Analytics]。 如需詳細資訊，請參閱&#x200B;*Adobe TargetSDK*&#x200B;指南中的[Analytics for Target(A4T)reporting](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)。

若要開始執行:

1. 在建立A/B測試活動時，在&#x200B;**[!UICONTROL 定位]**&#x200B;頁面上，選取下列其中一個選項作為&#x200B;**[!UICONTROL 流量分配方法]**:

   * [!UICONTROL 自動配置以獲得最佳體驗]
   * [!UICONTROL 自動鎖定個人化體驗]

   ![流量分配方法選項：手動、自動分配和自動目標](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   如需詳細資訊和逐步指示，請參閱[建立自動分配活動](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)和[建立自動目標活動](/help/c-activities/auto-target/create-auto-target.md)。

1. 在&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面上，為&#x200B;**[!UICONTROL 報表來源]**&#x200B;選取&#x200B;**[!UICONTROL Adobe Analytics]**，並選取與所需最佳化目標對應的報表套裝。

   ![「目標與設定」頁面上的「報告來源」區段](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 選擇主要目標量度。

   * 若要使用[!DNL Adobe Target]指定最佳化目標，請選擇&#x200B;**[!UICONTROL 轉換]**。
   * 選擇&#x200B;**[!UICONTROL 使用Analytics量度]**，然後從[!DNL Analytics]中選取量度，以用作最佳化目標。 您可以使用現成可用的[!DNL Analytics]轉換度量或[!DNL Analytics]自訂事件。

   如需詳細資訊，請參閱下方的[支援的目標量度](#supported)。

1. 儲存並啟動您的活動。

   [!UICONTROL 自動配置] 使用您選取的量度來最佳化活動，將訪客帶往體驗，以最大化您的目標量度。

   或

   [!UICONTROL 自動定位] 使用您選取的量度來最佳化活動，將訪客帶向個人化的最佳體驗。

1. 使用&#x200B;**[!UICONTROL 報表]**&#x200B;標籤，依您選擇的[!DNL Adobe Analytics]量度來檢視您活動的報表。 按一下「Analytics中的檢視」，深入探索並進一步細分報表資料。****

## 支援的目標量度{#supported}

[!UICONTROL A4] T for  [!UICONTROL Auto-] Allocate和 [!UICONTROL Auto-] Target可讓您選擇下列任一量度類型作為最佳化的主要目標量度：

* [!DNL Adobe Target] 轉換量度
* [!DNL Adobe Analytics] 轉換量度
* [!DNL Adobe Analytics] 個自訂事件

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocate和 [!UICONTROL Auto-] Target要求您選擇以二項式事件為基礎的量度。二項式事件是否發生。 二項式事件包括點按、轉換、訂購等。 這些類型的事件有時也稱為Bernoulli、二進位或離散事件。

[!UICONTROL A4] T for  [!UICONTROL Auto-] Allocate和 [!UICONTROL Auto-Target不支援] 對連續度量進行最佳化。持續度量包括收入、訂購的產品數量、作業期間、作業中的頁面檢視次數等。 這些不支援的量度類型有時也稱為非二項式或非伯努利量度。

下列量度類型不支援做為主要目標量度：

* [!DNL Adobe Target] 參與度與收入度量
* [!DNL Adobe Analytics] 參與度與收入度量

   您可以選擇[!DNL Analytics]參與或收入量度作為主要目標量度，因為[!DNL Target]無法識別並排除[!DNL Analytics]中的所有參與和收入量度。 僅從[!DNL Analytics]選取二項式轉換度量或自訂事件。

* [!DNL Adobe Analytics] 計算量度

## 限制與附註

某些限制和注釋適用於[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動。 其他限制和附註適用於一種或另一種活動類型。

### 自動分配和自動目標

* 報告來源不能從[!DNL Analytics]變更為[!DNL Target]，或在活動啟動後變更。
* 雖然計算量度不支援做為主要目標量度，但通常可以選擇自訂事件作為主要目標量度，以達到預期結果。 例如，如果您想要最佳化度量（例如「每位訪客表單填寫」），請選取與「表單填寫」對應的自訂事件作為主要目標度量。 [!DNL Target] 自動標準化每次瀏覽的轉換量度，以考慮不均勻的流量分佈，因此不需要使用計算量度來執行標準化。
* [!DNL Target] 使用「自動配置」功能中的「相同觸 [!UICONTROL 控」歸] 因模型：Analytics for Target(A4T)。

### 自動分配

* [!UICONTROL 自動配置] 機型會像往常一樣每兩小時進行一次培訓。

### 自動鎖定目標

* [!UICONTROL 自動定] 位機型會照常每24小時進行一次培訓。但是，來自[!DNL Analytics]的轉換事件資料會延遲6到24小時。 此延遲表示[!DNL Target]的流量分配會追蹤[!DNL Analytics]中記錄的最新事件。 此延遲在初始啟動活動後的前48小時有最大的影響。 活動的效能將更密切地反映經過五天後的[!DNL Analytics]轉換行為。 考慮對於短期活動使用[!UICONTROL 自動分配]而非[!UICONTROL 自動目標]，在短期活動中，大部分流量都發生在活動生命週期的前五天內。
* 當使用[!DNL Analytics]作為[!UICONTROL 自動目標]活動的資料源時，會話會在經過6小時後結束。 六小時後發生的轉換不會計算在內。

如需詳細資訊，請參閱&#x200B;*分析工具指南*&#x200B;中的[歸因模型和回顧windows](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)。

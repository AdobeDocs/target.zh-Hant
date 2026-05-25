---
keywords: 活動；活動；見解儀表板
description: '[!UICONTROL Adobe Target Dashboard]讓您概略瞭解貴組織如何隨著時間使用 [!DNL Target] 、呈現採用、活動量和實驗使用量。'
title: Adobe Target見解控制面板
feature: Activities
exl-id: 042befcd-025b-4592-a6b2-5dc0b952b031
source-git-commit: 346b54882d4082f14bbc16ede350758a362ee418
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 0%

---

# Adobe Target見解控制面板

[!UICONTROL Adobe Target Dashboard]提供貴組織在一段時間內如何使用[!DNL Adobe Target]的高階檢視。 它有助於團隊一眼就瞭解採用、活動量和實驗用法。

儀表板是專為想要快速瞭解[!DNL Target]使用情況的從業人員與利害關係人設計的，無需深入瞭解個別活動報告。

檢閱此控制面板時，請記住下列事項：

* 量度可能包括在所選時間範圍之前開始或之後結束的活動。
* 根據其生命週期（例如，已發佈及已完成），活動可在多個量度中計算。
* 儀表板專注於使用和採用，而不是績效結果。

如需詳細的結果、提升度或統計效能，請參閱[!DNL Adobe Target]內的[個別活動報告](../c-reports/reports.md)。

![](assets/insights-1.png)

## [!UICONTROL Experimentation Accelerator]

您儀表板上的橫幅可讓您直接存取&#x200B;**[!UICONTROL Experimentation Accelerator]**，這是一個輕量型的進入點，可讓您存取簡化實驗工作流程、簡化實驗設定、分析和決策的工具。

## 時間範圍選取

若要設定控制面板上顯示的資料範圍，請選取時間範圍，例如上週、去年或所有時間。 選取的時間範圍會一致地套用至控制面板上的所有量度和圖表。

![](assets/insights-2.png)

解譯所選時間範圍內的量度時，請牢記下列事項：

* 有些量度會反映此時間範圍內任何時間點上線的活動。

* 其他則反映在該時間範圍內建立、發佈或完成的活動。

* 因此，各量度的總計可能不會完全相加。 例如，許多活動可在相同的時間範圍內開始和完成。

您也可以從進階功能表中選取&#x200B;**[!UICONTROL Download as PNG]**，以匯出儀表板的快照。

![](assets/insights-3.png)

## 量度

儀表板將其量度組織為四個互補的檢視，每個檢視都回答有關您[!DNL Target]使用情況的不同問題： [KPI](#kpis)提供活動計數的一覽摘要，[活動型別劃分](#activity-type-breakdown)顯示您最依賴的功能，[A/B測試量度](#ab-testing-metrics)放大實驗使用，以及[隨著時間的活動](#activities-over-time)顯示所選時間範圍內的趨勢。

### KPI

頁面頂端的KPI卡片會一目瞭然地摘要所選時間範圍內的關鍵活動計數。 每張卡片都會聚焦於活動生命週期的不同階段、即時、已修改、已結束或已發佈，因此您可以快速評估整體使用情況和動向。

![](assets/insights-4.png)

**已上線活動總數**&#x200B;量度會詳細列出所選時間範圍內任何時間點已上線的活動數目。 如果活動主動提供流量，即使活動在所選期間之前或之後開始，仍會視為已上線。 使用此量度來：

* 瞭解在這段期間內如何使用[!DNL Target]。
* 評估個人化和測試工作的整體規模。

**已上線或修改的活動**&#x200B;量度代表貴組織在選取的時間範圍內已上線、建立或修改的活動總數。 使用此量度來：

* 瞭解[!DNL Target]活動程式庫的整體大小，以及使用中的活動數目。

* 追蹤您的實驗與個人化方案的長期成長。

**已結束的活動**&#x200B;量度代表在選取的時間範圍內達到完成或停止日期的活動數目。 使用此量度來：

* 瞭解在該時段內完成的活動數。
* 追蹤一段時間的完成量。

**已發佈活動**&#x200B;量度詳細說明了在選取的時間範圍內已發佈的活動數目。 活動首次上線時會被視為已發佈。 如果活動上線、停止，然後再次上線，此量度中只會計算第一次發生次數。 使用此量度來：

* 測量已啟動的新活動數。
* 瞭解活動的建立和發佈速度。

### 活動型別劃分

![](assets/insights-5.png)

[!UICONTROL Activity Type]圖表會依型別顯示所選時間範圍內的上線活動分佈，包括：

* [!UICONTROL A/B Test]
* [!UICONTROL Experience Targeting]
* [!UICONTROL Recommendations]
* [!UICONTROL Automated Personalization]
* [!UICONTROL Multivariate Test]

使用此圖表來識別貴組織最仰賴的[!DNL Target]功能，並找出機會，以擴大您執行的活動型別組合。

### A/B測試量度

![](assets/insights-6.png){align="center"}

本節強調與&#x200B;**[!UICONTROL A/B Test]**&#x200B;活動相關的使用方式。

**[!UICONTROL Total live A/B Test activities]**&#x200B;量度會顯示所選時間範圍內任何時間點上線的&#x200B;**[!UICONTROL A/B Test]**&#x200B;活動數目。

**[!UICONTROL Total A/B Tests published]**&#x200B;顯示所選時間範圍內已發行的&#x200B;**[!UICONTROL A/B Test]**&#x200B;活動數目。

使用這些量度來瞭解A/B測試的使用頻率，並追蹤一段時間內的實驗量和採用情況。

### 一段時間內的活動

![](assets/insights-7.png){align="center"}

**[!UICONTROL Activities Over Time]**&#x200B;圖表會追蹤在選取的時間範圍內建立、修改和發佈的活動數量，讓您在實驗方案中輕鬆發現趨勢、尖峰或靜默期。


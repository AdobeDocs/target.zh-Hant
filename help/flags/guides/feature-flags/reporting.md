---
title: 報表
description: 瞭解如何使用Customer Journey Analytics檢視旗標中的功能標幟報告。
hide: true
exl-id: edddca99-f263-461b-a16f-b46ee7c15f6c
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# 報表 {#reporting}

旗標會透過&#x200B;**Customer Journey Analytics (CJA)**&#x200B;傳送報表。 每個功能標幟和功能群組詳細資訊頁面上都有&#x200B;**報告**&#x200B;索引標籤。 它可讓您檢視範圍限定為直接內嵌在頁面中之特定標幟或群組的CJA報表。

>[!NOTE]
>
>預設會以&#x200B;**30天**&#x200B;報告期間開啟報告。 您可以調整面板標頭的範圍。

## 先決條件 {#prerequisites}

檢視報表之前，請確定：

1. 已為您的應用程式設定報告 — 請參閱[使用Customer Journey Analytics設定報告](#setup)。
1. 您的功能標幟或功能群組處於作用中狀態，並已累積資料。

## 檢視報告 {#view-report}

### 開啟「報表」標籤，並挑選資料檢視 {#open-report-tab}

1. 開啟功能標幟或功能群組並選取&#x200B;**報表**&#x200B;標籤。
1. **選取資料檢視**&#x200B;對話方塊開啟，其中列出可供您使用的CJA資料檢視。 預設會選取第一個專案。
1. 選擇您想要的資料檢視，並選取&#x200B;**檢視報告**。 選取&#x200B;**取消**&#x200B;關閉對話方塊而不載入報告。
1. 報表會在標籤內載入，範圍限定為該標幟或群組的實體ID。

在功能標幟的詳細資訊頁上![報告標籤](assets/report-tab.png)

>[!NOTE]
>
>此對話方塊僅列出您在目前沙箱中有權存取的資料檢視。 如果沒有可用專案，對話方塊會顯示訊息，且&#x200B;**檢視報告**&#x200B;保持停用 — 檢查您的資料檢視許可權或切換沙箱。

![選取資料檢視對話方塊](assets/select-dataview.png)

### 檢視效能報表 {#view-performance-report}

內嵌&#x200B;**旗標總覽**&#x200B;儀表板隨即顯示：

* **總人數**、**依日期的人員參與率**，以及&#x200B;**依變體的人員參與率** （控制組與變體ID）
* **總覽**&#x200B;表格列出每個變體及其人員計數和參與百分比

從面板標題調整日期範圍，以重新繪製不同視窗（預設為30天）。

![標幟總覽效能報告](assets/performance-report.png)

### 探索實驗結果 {#explore-experimentation-results}

1. 在&#x200B;**Experimentation**&#x200B;面板中，已預先選取&#x200B;**Experiment** （旗標或群組實體ID）和&#x200B;**控制變體**。
1. 使用&#x200B;**新增量度**&#x200B;新增&#x200B;**成功量度**，並根據您要繪製的圖表選擇&#x200B;**標準化量度** （預設&#x200B;**人員**）。
1. 選擇性地啟用&#x200B;**包含信賴上/下限**。
1. 選取&#x200B;**建置**&#x200B;以針對選取的量度計算每個變體的&#x200B;**提升度**、**信賴度**&#x200B;和&#x200B;**轉換率**。

![實驗面板，包含實驗、控制變體和量度選擇器](assets/experimentation-selection.png)

請參閱[Experimentation面板檔案](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/panels/experimentation)，以取得如何計算這些量度的詳細資訊。

![依變體顯示提升度、信賴度和轉換率的實驗結果](assets/experimentation.png)

### 在CJA中分析（選用） {#analyze-in-cja}

載入報告後，**在CJA中分析**&#x200B;按鈕會出現在「報告」標籤的右上方。 選取此專案，即可在新的瀏覽器標籤中在Customer Journey Analytics開啟相同的報表完整頁面，讓您擁有完整的CJA工具集，以進行更深入的Ad Hoc分析。

在Customer Journey Analytics工作區中開啟的![標幟概觀報告](assets/cja-workspace.png)

>[!IMPORTANT]
>
>報告會以暫時、未儲存的專案開啟。 如果您在CJA中自訂它（新增量度、變更面板、調整篩選器等）並想要保留這些變更，請使用「**專案>另存為範本**」來儲存它。 否則，當您關閉報表時，您的編輯將會遺失。

![醒目提示「另存為範本」的「專案」功能表](assets/save-as-template.png)

## 使用Customer Journey Analytics設定報告 {#setup}

報表需要將Customer Journey Analytics資料集連線至您的Flags應用程式。 請聯絡Flags支援或您的Adobe代表，為您的應用程式啟用報告功能。

>[!NOTE]
>
>在功能要求中傳遞的身分不需要連結到設定檔。 評估會在執行階段進行，且事件會傳送至Customer Journey Analytics。

## 另請參閱 {#see-also}

* [建立您的第一個功能標幟](create-your-first-feature-flag.md)
* [使用功能標幟的A/B測試](a-b-testing.md)
* [建立功能群組](create-a-feature-group.md)

<!-- -->

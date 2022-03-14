---
keywords: Target;報表;報表設定;預設集;target 預設集;量度;對象;日期範圍;設定;下載;表格檢視;圖表檢視;平均提升度;提升度;提升度界限;信賴區間;信賴;位置貢獻;執行中的平均值;計數方法
description: 瞭解如何在Adobe Target配置報告設定，包括度量、受眾、日期範圍等。
title: 如何配置報告設定？
feature: Reports
exl-id: 337579d1-c678-43b6-9e80-b5abe159c2d3
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1918'
ht-degree: 69%

---

# 報表設定

幫助您設定要在報表中顯示的元素的資訊 [!DNL Adobe Target]。 可以儲存報表設定以供稍後使用。

若要顯示報表:

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，然後從清單按一下需要的活動。
1. 按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。

   ![報表 UI](/help/main/c-reports/c-report-settings/assets/report_ui-new.png)

## Target 預設集 {#section_51F67341465045BEB4F1A2FB638A8EB1}

視需要設定個別活動報表後，您最多可以儲存十個不同的預設集 (量度、日期範圍、對象、進階設定等)。全部 [!DNL Target] 用戶可以顯示、編輯和刪除各種預設，而不管這些預設是誰建立的。

您也可以視需要設定個別活動報表，然後將該設定儲存為預設/我的最愛預設集。檢視活動報表進展時就會顯示這個畫面。

### 建立預設或預設預設

1. 根據需要配置活動的報告。

   下面將介紹可用設定，包括度量、日期範圍、受眾、高級設定等。

1. 在 **[!UICONTROL Target 預設集]**&#x200B;旁邊，依序按下三個垂直的點圖示 > **[!UICONTROL 「另存新檔」]**。

   ![報表預設集](/help/main/c-reports/c-report-settings/assets/report_preset-new.png)

   隨即顯示「新的預設集」對話方塊:

   ![新預設集對話方塊](/help/main/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. 查看 **[!UICONTROL 篩選器]** 和 **[!UICONTROL 設定]** 部分，確保根據需要配置報告，然後指定 **[!UICONTROL 預設名稱]** （最多50個字元）。
1. （條件）如果希望此視圖為預設/收藏夾報表視圖，請滑動 **[!UICONTROL 設定為預設預設]** 切換到「開啟」位置。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

### 選擇其他預設

從&#x200B;**[!UICONTROL 「Target 預設集」]**&#x200B;下拉式清單選取所需的預設集。

![預設集下拉式清單](/help/main/c-reports/c-report-settings/assets/report_preset_drop-down-new.png)

### 編輯預設

1. 選取要編輯的預設集。
1. 視需要編輯報表設定 (量度、日期範圍、對象、進階設定等)。

   在編輯報表的設定後，按一下[!UICONTROL 「儲存」]，預設集名稱後面會顯示一個星號 ( * )，表示預設集已變更，如下所示:

   ![報表預設集 (含星號)](/help/main/c-reports/c-report-settings/assets/report_preset_asterisk-new.png)

1. 依序按下「三個垂直橢圓圖示 > **[!UICONTROL 另存新檔」]**&#x200B;以建立新預設集。

   或

   依序按下「三個垂直橢圓圖示 > **[!UICONTROL 更新」]**&#x200B;以更新目前的預設集。

   ![報表預設更新](/help/main/c-reports/c-report-settings/assets/report_preset_update-new.png)

### 刪除預設

1. 選取要刪除的預設集。
1. 依序按下三個垂直的點 > **[!UICONTROL 「刪除」]**。

   ![報表預設刪除](/help/main/c-reports/c-report-settings/assets/report_preset_delete-new.png)

1. 按一下 **[!UICONTROL 刪除]** 再次確認刪除（無法恢復已刪除的預設）。

### 預設錯誤處理

報表中的警示和訊息可讓您知道預設集是否無效。警示或訊息指示您選擇其他對象、量度、主機群組或體驗，以製作有效的預設集。

下表說明可能造成預設集變成無效的一些情況:

* 報表對象已從活動中移除，但在預設集定義中參照。
* 已刪除一或多個量度，但在預設集定義中參照。例如，您可以從活動中刪除一或多個量度，然後新增量度。
* 一或多個主機群組 (環境) 不存在，但在預設集定義中參照。
* 建立預設集之後，已刪除一或多個體驗，但在預設集定義中參照。
* 預設集的語意無效，因為轉介的實體仍然存在，但是預設集定義在語義上變更的方式已更新。例如，假設您最初建立名為「Revenue on Chrome」的預設集。之後更新活動以測量「轉換」量度，而非「收入」。此對活動定義的更新在語義上使預設定義無效。

## 報表量度 {#section_894ABD7148244806B7CE556EBBA2AD62}

按一下&#x200B;**[!UICONTROL 「報表量度」]**&#x200B;下拉式清單，選取不同的[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)或多個量度以顯示於圖表中。

依預設，主要量度是在您建立活動時於成功量度設定中決定。如果您變更設定並重新儲存活動，報表的主要量度會更新。

如需選取多個量度以便於報表中檢視的相關資訊，請參閱[在報表中檢視多個量度](/help/main/c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7)。

## 對象 {#section_70926EB4618945D9AFF2B0564FF3717B}

按一下[!UICONTROL 「對象」]下拉式清單，以變更報表所顯示的對象。

如需詳細資訊，請參閱[對象](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)。

## 日期範圍 {#section_A410A768403C4E01891F95CB357E63ED}

「日期範圍」框顯示報表的當前日期範圍。 按一下下拉式圖示以顯示可讓您變更報表日期範圍的日曆。

![日曆](/help/main/c-reports/c-report-settings/assets/date_range-new.png)

為報表選取新的&#x200B;**[!UICONTROL 「開始」]**&#x200B;和&#x200B;**[!UICONTROL 「結束」]**&#x200B;日期。您還可以使用 **[!UICONTROL 從活動開始]** 和 **[!UICONTROL 直到活動結束]** 的雙曲餘切值。

按一下&#x200B;**[!UICONTROL 「自訂日期」]**&#x200B;以選取預先定義的日期範圍: 最近 7 天、最近 15 天，或最近 30 天。這些預先定義的日期範圍是動態範圍。如果開始日期早於於所選天數，則日曆將顯示從開始日期開始的範圍，一旦開始日期變成晚於活動持續時間增加時選擇的天數，則會動態變更範圍。

報表具有下列日期限制:

* 報表的開始日期必須在最近兩年內。
* 服務組報告限制為從今天起99天。
* 每小時報表限制為 15 天。

## 設定 {#section_D99CE462107D45CABE0960F820E1E972}

配置報告設定：

1. 按一下齒輪表徵圖，進行所需的更改（如下所述）。
1. 完成時，按一下&#x200B;**[!UICONTROL 「儲存」]**。

下圖顯示 A/B 活動的「設定」對話方塊:

![設定對話方塊](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog-new.png)

視選取的活動類型而定，選項會有所不同:

### 計算方法

選擇所需的方法：

* 訪客
* 瀏覽次數
* 活動曝光次數

### 控制

選擇計算和比較電梯時要使用的控制體驗。

### 環境

選擇要用於報告的環境（主機組）。 如需詳細資訊，請參閱[主機](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

### 重設報告資料

重置報告資料以刪除舊資料。 目前的訪客將保留在活動中。此選項僅適用於 [!UICONTROL 批准者] 權限。

>[!IMPORTANT]
>
>此為永久性動作，無法還原。

### 排除極端值

的 [!UICONTROL 排除極值] 切換僅應用於具有「收入」和「項目」度量類型的活動。 如需詳細資訊，請參閱[排除極端訂單](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

## 下載 {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

按一下 **[!UICONTROL 下載]** 表徵圖，在 [!DNL .csv] 格式，用於快速導入到Excel、Access或其他資料分析程式。

![下載表徵圖](/help/main/c-reports/c-report-settings/assets/download-icon.png)

如需詳細資訊，請參閱[將資料下載為 CSV 檔案](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)。

## 重新整理 {#section_E203729F2F314DF3856D2EE67C60B370}

按一下 **[!UICONTROL 刷新]** 表徵圖，以刷新報表的表和圖形視圖，而不刷新整個頁面、其配置或其日期範圍。

## 更多選項 {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

按一下「更多選項」圖示 (三個垂直橢圓)，以存取[!UICONTROL 「編輯活動」]和[!UICONTROL 「檢視體驗 URL」]選項。

## 查看選項

您可以根據活動類型以各種格式查看報告。 選擇所要的選項.

![查看選項表徵圖](/help/main/c-reports/c-report-settings/assets/view-options.png)

* **表視圖**:按一下 **[!UICONTROL 表視圖]** 表徵圖以表格形式查看報表。
* **圖形視圖**:按一下 **[!UICONTROL 圖形視圖]** 表徵圖，以圖形形式查看報表。
* **自動化段**:(僅適用於Automated Personalization(AP)和自動目標(AT)活動。) 按一下**[!UICONTROL 自動化段] 表徵圖 [自動段報告](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)。
* **重要屬性**:(僅適用於Automated Personalization(AP)和自動目標(AT)活動。) 按一下**[!UICONTROL 重要屬性] 表徵圖 [重要屬性報告](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)。

## 平均提升度、提升度界限和信賴區間 {#section_0D87615B1D3344B3858BA494EEBC16FB}

報表包含數個資料點和視覺效果表示法，可表達與活動相關聯的提升度界限和信賴水準。這可協助您正準確地判斷獲勝者。

如需詳細資訊，請參閱[平均提升度、提升度界限和信賴區間](/help/main/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md#topic_AFFDC672A8A34D028B100EF6BE5D8129)。

考慮以下事項:

* 只有以「表格檢視」來檢視報表時才可用。
* 此功能無法供以[ Analytics 作為報表來源 (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) 的活動使用。

## 位置貢獻 {#section_5832F126AC114AE1ABFFF4D9B904393B}

按一下&#x200B;**[!UICONTROL 「位置貢獻」]**&#x200B;圖示，將報表切換為依位置來顯示貢獻。

## 體驗 {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

(只有在圖表檢視中檢視報表時才可供使用)

在圖表左側選取或取消選取體驗，以決定在圖表中顯示或隱藏相對應的體驗。

在下圖中，只有預設、中東和總計體驗會顯示在報表中。圖表中的亞洲體驗為隱藏狀態。

![體驗](/help/main/c-reports/c-report-settings/assets/report_experiences-new.png)

## 執行中的平均值 {#section_59066693158C4433B87D07402C2BC6CD}

(只有在圖表檢視中檢視報表時才可供使用)

「運行平均值」反映累積轉換（從報告窗口的開始到圖形上表示的日期）除以累積訪問者。

選取所需的圖表檢視:

* 執行中的平均值
* 執行中的平均值提升
* 每日
* 每日提升

![報表執行中的平均值](/help/main/c-reports/c-report-settings/assets/report_running_average-new.png)

此下拉清單的名稱因所選視圖而異，但將是上面列出的視圖之一。

## 計算方法 {#section_01B0ED5665C74AE1AE97259800190C3E}

(只有在圖表檢視中檢視報表時才可供使用)

您可以為報表中的圖形選擇計算方法。請注意， [!UICONTROL Automated Personalization] （美聯社）活動。

訪問 [!UICONTROL 計數方法] 選項，在圖形模式下查看報告時，按一下 **[!UICONTROL 我的主要目標]** 下拉，然後選擇計數方法。

此計數方法與上述[!UICONTROL 「設定」]對話方塊中選取的方法相同。

![計算方法](/help/main/c-reports/c-report-settings/assets/counting_methodology_2-new.png)

依預設會以[!UICONTROL 「每日」]模式繪製圖表。

通過按一下 [!UICONTROL 每日] 下拉清單，然後選擇累積選項。

![累積](/help/main/c-reports/c-report-settings/assets/counting_methodology-new.png)

>[!NOTE]
>
>此下拉式清單的名稱會依選取的模式而不同。

「自動鎖定目標」活動有四種模式: 每日控制、每日已鎖定目標、累積控制和累積目標。

圖表的預設繪製順序如下:

* **A/BTest(包括自動分配和Automated Personalization)**:體驗建立的順序，按降序排列。
* **體驗目標(XT)**:活動中的體驗順序。
* **多元Test**:按經驗名稱字母。
* **Recommendations**:體驗建立的順序，按降序排列。

使用計數方法選項時，請注意下列警告:

* 對於 [自動目標活動](/help/main/c-activities/auto-target/auto-target-to-optimize.md)，沒有選擇&quot;訪問者&quot;作為計數方法的選項。 「自動鎖定目標」是唯一無法依訪客來繪製的活動類型。
* 用於使用 [作為報告源的分析(A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md)不能累積地策劃&quot;訪客&quot;,&quot;訪問&quot;或&quot;印象&quot;。

## 使用在活動中有16個以上經驗的圖表

如果活動的體驗少於 16 個，圖表中會以不同顏色繪製每一個體驗。

如果活動的體驗超過 16 個，圖表中會顯示前 16 個體驗的彩色線條。剩餘的體驗會在左側「體驗」窗格中呈現灰色，圖表中不會顯示對應的繪圖線條。任何時候都只能顯示 16 個體驗的線條。

如果暫留在灰色體驗上，對應於該體驗的新灰色繪圖線條會短暫出現在圖表中。若要以色彩顯示灰色體驗的繪圖線條，您可以對彩色顯示的體驗按一下名稱將它取消選取，然後對所需的灰色體驗按一下名稱來選取它。

舉例來說，下圖顯示活動的圖表有 26 個體驗:

![](assets/graph_1.png)

圖表會顯示前 16 個體驗 (部分重疊，所以看起來少於 16 條線)。在左側的體驗窗格中，每一個體驗名稱旁的彩色點會指出體驗的繪圖線條，以對應的顏色顯示。

如果您在體驗窗格中向下捲動，可看到第 17 個至第 26 個體驗的名稱變成灰色，如下圖所示:

![](assets/graph_2.png)

如果暫留在其中一個灰色體驗上，對應於該體驗的新灰色繪圖線條會短暫出現在圖表中。

假設您想顯示體驗 R 的繪圖線條，而不想看到體驗 P 的線條。您可以按一下體驗 P 的名稱將它取消選取，然後按一下體驗 R 的名稱來選取它，如下所示:

![](assets/graph_3.png)

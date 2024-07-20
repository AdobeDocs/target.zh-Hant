---
keywords: analytics for target；a4t；Analytics作為報表來源；Analytics
description: 瞭解如何將Analytics用於 [!DNL Target] (A4T)。 對於使用Analytics量度和受眾區段的 [!DNL Target] 活動，A4T可讓您存取Analytics報表。
title: 如何在A4T中使用報表？
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 39%

---

# A4T 報表

使用[!DNL Adobe Analytics]做為[!DNL Adobe Target] (A4T)的報告來源，可讓您存取[!DNL Target]活動的[!DNL Analytics]報告。

您可以在[!DNL Analytics]和[!DNL Target]中檢視活動的報告。

若要針對[!DNL Target]使用[!DNL Analytics]的報告最佳實務，[請造訪此Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)。

## 總覽 {#section_035A62D65608423285D8A5A54731E2C5}

[!DNL Analytics]和[!DNL Target]都會報告測量加入者（進入測試的人），而不是網站的訪客。

每次訪客在頁面上看到活動內容時，[!DNL Target]都會對[!DNL Analytics]發出直接的伺服器對伺服器呼叫，包括訪客看到的活動和體驗。 每次進行轉換時，[!DNL Target]也會呼叫[!DNL Analytics]。 [!DNL Analytics]將轉換新增為名為「活動轉換」的特定新[!DNL Analytics]事件，此事件會與[!DNL Analytics]收集的其他資料一起追蹤。

使用[!UICONTROL Select]作業且您對&#x200B;*加入者*&#x200B;排序時，報表中只會顯示所選時段內收到加入者的體驗。

>[!NOTE]
>
>由[!DNL Target]提供支援的報表會延遲四分鐘。 對於由A4T支援的活動，在[!DNL Target]和[!DNL Analytics]報表中，可能需要24小時的時間，才能在活動最初儲存後，依體驗劃分報表資料。 在這最初 24 小時收集的資料仍然正確，且會指派給正確的體驗。

## Analytics 中的報表 {#analytics}

在[!DNL Analytics]中，啟用A4T整合後，有數個維度和量度可供使用。

### 維度

* [!UICONTROL Analytics for Target] — 透過整合傳入的父識別碼。 此維度的格式為`Activity ID:Experience ID:3rd ID`。 以下維度是此維度的分類。
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity] > [!UICONTROL Experience]
* [!UICONTROL 3rd ID] — 可以忽略

### 量度

* [!UICONTROL Activity Impressions] — 符合[!DNL Target]報告中的[!UICONTROL Entrants]數字。
* [!UICONTROL Activity Conversions] — 符合[!DNL Target]報告中的[!UICONTROL Custom Conversions]數字。

在[!DNL Analysis Workspace]中，使用[!UICONTROL Analytics for Target]面板，以提升度和信賴度分析您的[!DNL Target]活動和體驗。 如需詳細資訊，請參閱&#x200B;*Analytics工具指南*&#x200B;中的[Analytics for Target (A4T)面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html??lang=zh-Hant)。

>[!IMPORTANT]
>
>如果您在[!DNL Analytics]中的[!UICONTROL Target Activities]報表列出「未指定」，而非列出您的活動，則需要更新您已布建的帳戶。 請聯絡客戶服務以解決此問題。

如需詳細資訊和範例，請開啟Adobe Experience League提供的[Analytics &amp; Target： Analysis最佳實務](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)教學課程。

## [!DNL Target]中的報告 {#section_C0D1F17F88374B6690BF904D7B83B42E}

當使用[!DNL Analytics]做為報告來源時，[!DNL Target]中的報告會顯示從[!DNL Analytics]收集到的資料。 此報告與其他[!DNL Target]報告有些不同：

* [!UICONTROL Audiences]清單顯示[!DNL Analytics]報表套裝可用的對象。
* [!UICONTROL Metric]清單會顯示每個可透過[!DNL Analytics]使用的量度。

  每個量度皆可使用，包括[!DNL Analytics]內建的任何自訂或計算量度。

  任何增加的數字都會在報表中顯示為正數，即使不需要增加時亦然。 例如，即便您想要較低的跳出率仍顯示了較高的跳出率，因為獲勝者會具有最高的提升度。根據報表進行決策時，請注意這些和類似的量度，以及是否您偏好減少或增加這些數字。

您可以在活動開始後，或甚至在測試完成後，在[!DNL Target]中將量度或對象套用至報表。 您事先完全不需要知道要測量什麼。

按一下以直接從活動報告頁面檢視完整[!DNL Analytics]報告。

## 活動建立 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在建立活動期間，您必須在[!UICONTROL Settings]頁面上指定活動的目標。 此目標會成為報表的預設量度，且一律列為量度選取器的第一個選項。您無法像一般 Target 活動一樣選取要報告的區段。具有[!DNL Analytics]的測試使用[!DNL Adobe Analytics]個區段，而非[!DNL Target]個對象。

## 執行Analytics for Adobe Target (A4T)的離線計算 {#section_B34BD016C8274C97AC9564F426B9607E}

您可以使用[!DNL Target] [完整可信度計算器](/help/main/assets/complete_confidence_calculator.xlsx) Excel檔案，對A4T的信賴度和可信度區間執行離線計算，但是它需要在[!DNL Analytics]中進行資料匯出的步驟。

若是A4T，我們針對連續變數使用[Welch的t檢定](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}計算（而非二進位量度）。 在 Analytics 中，一律會追蹤訪客，並統計每一個採取的動作。因此，如果訪客多次購物或多次造訪成功量度，這些額外的點閱會納入計算。這會使量度變成連續變數。若要執行Welch的t檢定計算，必須使用「平方和」來計算變異數（用於t統計的分母）。 [A/Bn測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)說明使用的數學公式的詳細資料。 可從[!DNL Analytics]擷取平方和。 若要取得平方和資料，您需要針對想要最佳化的量度，在樣本期間內執行訪客等級的匯出。

例如，如果您正在最佳化為每位訪客的頁面檢視次數，您可以匯出指定時間段內每位訪客的頁面檢視總數的範例，或許幾天（只需要幾千個資料點）。 接著，您會求每一個值的平方，並算出總和 (此處的運算順序很重要)。然後，在「完整信賴度計算機」中會使用此「平方和」值。針對這些值，使用該試算表的「收入」區段。

**使用 [!DNL Analytics] 資料匯出功能來這樣做:**

1. 登入 [!DNL Adobe Analytics]。
1. 按一下&#x200B;**[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**。
1. 在&#x200B;**[!UICONTROL Data Warehouse Request]**&#x200B;標籤上，填寫欄位。

   如需每一個欄位的相關資訊，請參閱[資料倉儲](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html)中的「資料倉儲說明」。

   | 欄位 | 指示 |
   |--- |--- |
   | 請求名稱 | 指定要求的名稱。 |
   | 報告日期 | 指定時段和精度。<br>最佳做法是不要為第一個要求選擇超過一小時或一天的資料。所要求的時段越長，資料倉儲檔案處理的時間就越長，最好一律先要求較短時段的資料，以確保檔案傳回預期的結果。接著，前往「要求管理程式」，複製要求，再第二次要求更多資料。此外，如果您將詳細程度切換為「無」以外的任何值，檔案大小將大幅增加。<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | 可用區段 | 視需要套用區段。 |
   | 劃分 | 選取所需的維度：「標準」是內建(OOTB)，而「自訂」包含eVar和prop。 如需訪客ID層級資訊，建議您使用「訪客ID」，而非「Experience Cloud訪客ID」。<ul><li>訪客 ID 是 Analytics 使用的最終 ID。這會是 AID (如果客戶是舊的) 或 MID (如果客戶是新的，或已清除從 MC 訪客 ID 服務啟動以來的 Cookie)。</li><li>僅針對新的客戶，或客戶已清除從 MC 訪客服務啟動以來的 Cookie，才會設定 Experience Cloud 訪客 ID。</li></ul> |
   | 量度 | 選取所需的量度。標準是 OOTB，而「自訂」包含自訂事件。 |
   | 報表預覽 | 在排定報表之前檢閱設定。<br>![Data Warehouse2](/help/main/c-reports/assets/datawarehouse2.png) |
   | 計劃傳送 | 輸入要傳送檔案的電子郵件地址，命名檔案，然後選取[!UICONTROL Send Immediately]。<br>注意：可在[!UICONTROL Advanced Delivery Options]<br>![排程傳送](/help/main/c-reports/assets/datawarehouse3.png)下透過FTP傳送檔案。 |

1. 按一下 **[!UICONTROL Request this Report]**。

   檔案傳送最多可能需要 72 小時，視所要求的資料量而定。您可以隨時按一下「[!UICONTROL Tools] > [!UICONTROL Data Warehouse] > [!UICONTROL Request Manager]」來檢查要求的進度。

   如果您想要重新要求您過去曾要求的資料，您可以視需要複製[!UICONTROL Request Manager]中的舊要求。

如需 [!DNL Data Warehouse] 的相關資訊，請參閱 [!DNL Analytics] 說明文件中的下列連結:

* [建立Data Warehouse要求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [Data Warehouse最佳實務](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)

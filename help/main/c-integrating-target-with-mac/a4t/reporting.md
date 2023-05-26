---
keywords: analytics for target；a4t；analytics作為報表來源；analytics
description: 瞭解如何將Analytics用於 [!DNL Target] (A4T)。 A4T可讓您存取的Analytics報表 [!DNL Target] 使用Analytics量度和受眾區段的活動。
title: 如何在A4T中使用報表？
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 45%

---

# A4T 報表

使用 [!DNL Adobe Analytics] 作為的報告來源 [!DNL Adobe Target] (A4T)可讓您存取 [!DNL Analytics] 您的報表 [!DNL Target] 活動。

您可以在中檢視活動的報表 [!DNL Analytics] 和 [!DNL Target].

對於報告最佳實務，請使用 [!DNL Analytics] 的 [!DNL Target]， [造訪此Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## 總覽 {#section_035A62D65608423285D8A5A54731E2C5}

兩者 [!DNL Analytics] 和 [!DNL Target] 報表會測量加入者（進入測試的人），而非網站的訪客。

每次訪客看到頁面上的活動內容時， [!DNL Target] 對進行直接的伺服器對伺服器呼叫 [!DNL Analytics]，包括訪客所看到的活動和體驗。 [!DNL Target] 也呼叫 [!DNL Analytics] 每次進行轉換時。 [!DNL Analytics] 將轉換新增為特定新的 [!DNL Analytics] 名為「活動轉換」的事件，此事件會連同收集的其他資料一起受到追蹤 [!DNL Analytics].

當 [!UICONTROL 選取] 作業已使用且您排序於 *加入者*，則報告中只會顯示選定時段內收到加入者的體驗。

>[!NOTE]
>
>報表提供者： [!DNL Target] 延遲四分鐘。 對於由A4T支援的活動，兩者皆在 [!DNL Target] 和 [!DNL Analytics] 在報表中，可能最多需要24小時的時間，才會開始儲存活動後，報表資料才可依體驗細分。 在這最初 24 小時收集的資料仍然正確，且會指派給正確的體驗。

## Analytics 中的報表 {#analytics}

在 [!DNL Analytics]，在啟用A4T整合後，有數個維度和量度可供使用。

### 維度

* [!UICONTROL 目標分析]  — 透過整合傳入的父系ID。 此維度的格式為 `Activity ID:Experience ID:3rd ID`. 以下維度是此維度的分類。
* [!UICONTROL Target 活動]
* [!UICONTROL 目標體驗]
* [!UICONTROL Target活動] > [!UICONTROL 體驗]
* [!UICONTROL 第3個ID]  — 可忽略

### 量度

* [!UICONTROL 活動曝光次數]  — 比對 [!UICONTROL 加入者] 中的數字 [!DNL Target] 報告。
* [!UICONTROL 活動轉換]  — 比對 [!UICONTROL 自訂轉換] 中的數字 [!DNL Target] 報告。

在 [!DNL Analysis Workspace]，使用 [!UICONTROL 目標分析] 面板以分析您的 [!DNL Target] 提升度和可信度的活動和體驗。 如需詳細資訊，請參閱 [Analytics for Target (A4T)面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html??lang=zh-Hant) 在 *Analytics工具指南*.

>[!IMPORTANT]
>
>若您的 [!UICONTROL Target活動] 報告位置 [!DNL Analytics] 列出「未指定」而非列出您的活動，而是需要更新您的布建帳戶。 請聯絡客戶服務以解決此問題。

如需詳細資訊和範例，請開啟 [Analytics與Target：分析最佳實務](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) 教學課程，由Adobe Experience League提供。

## 中的報表 [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

時間 [!DNL Analytics] 會作為報表來源，報表位於 [!DNL Target] 顯示收集自的資料 [!DNL Analytics]. 此報告與其他報告略有不同 [!DNL Target] 報告：

* 此 [!UICONTROL 受眾] 清單會顯示您可用的對象： [!DNL Analytics] 報告套裝。
* 此 [!UICONTROL 量度] 清單會顯示每個可用的量度，透過 [!DNL Analytics].

   每個量度皆可使用，包括內建的任何自訂量度或計算量度 [!DNL Analytics].

   任何增加的數字都會在報表中顯示為正數，即使增加不是好事。 例如，即便您想要較低的跳出率仍顯示了較高的跳出率，因為獲勝者會具有最高的提升度。根據報表進行決策時，請注意這些和類似的量度，以及是否您偏好減少或增加這些數字。

您可以在下列位置將量度或受眾套用至報表： [!DNL Target] 活動開始之後，或甚至在測試完成之後。 您事先完全不需要知道要測量什麼。

按一下以檢視完整內容 [!DNL Analytics] 直接從活動報告頁面報告。

## 活動建立 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在建立活動期間，您必須在[!UICONTROL 「設定」]頁面上指定活動的目標。此目標會成為報表的預設量度，且一律列為量度選取器的第一個選項。您無法像一般 Target 活動一樣選取要報告的區段。測試 [!DNL Analytics] 使用 [!DNL Adobe Analytics] 區段，而非 [!DNL Target] 對象。

## 對Analytics for Adobe Target (A4T)執行離線計算 {#section_B34BD016C8274C97AC9564F426B9607E}

您可以使用 [!DNL Target] [完整可信度電腦](/help/main/assets/complete_confidence_calculator.xlsx) Excel檔案，但需要在中進行資料匯出的步驟 [!DNL Analytics].

若是A4T，我們使用 [韋爾奇的t檢定](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} 計算連續變數（而非二進位量度）。 在 Analytics 中，一律會追蹤訪客，並統計每一個採取的動作。因此，如果訪客多次購物或多次造訪成功量度，這些額外的點閱會納入計算。這會使量度變成連續變數。若要執行Welch的t檢定計算，需要「平方和」來計算變異數，此變異數會用在t統計量的分母中。 [A/Bn測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) 說明使用的數學公式的詳細資訊。 平方總和可以從 [!DNL Analytics]. 若要取得平方和資料，您需要針對想要最佳化的量度，在樣本期間內執行訪客等級的匯出。

例如，如果您正在最佳化為每位訪客的頁面檢視次數，您可以匯出指定時間段內每位訪客的頁面檢視總數樣本，也許幾天即可（只需要幾千個資料點）。 接著，您會求每一個值的平方，並算出總和 (此處的運算順序很重要)。然後，在「完整信賴度計算機」中會使用此「平方和」值。針對這些值，使用該試算表的「收入」區段。

**使用 [!DNL Analytics] 資料匯出功能來這樣做:**

1. 登入 [!DNL Adobe Analytics]。
1. 按一下「**[!UICONTROL 工具]** > **[!UICONTROL 資料倉儲]**」。
1. 在&#x200B;**[!UICONTROL 「資料倉儲要求」]**&#x200B;標籤上，填寫欄位。

   如需每一個欄位的相關資訊，請參閱[資料倉儲](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html)中的「資料倉儲說明」。

   | 欄位 | 指示 |
   |--- |--- |
   | 請求名稱 | 指定要求的名稱。 |
   | 報告日期 | 指定時段和精度。<br>最佳做法是不要為第一個要求選擇超過一小時或一天的資料。所要求的時段越長，資料倉儲檔案處理的時間就越長，最好一律先要求較短時段的資料，以確保檔案傳回預期的結果。接著，前往「要求管理程式」，複製要求，再第二次要求更多資料。此外，如果您將詳細程度切換為「無」以外的任何值，檔案大小都會大幅增加。<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | 可用區段 | 視需要套用區段。 |
   | 劃分 | 選取所需的維度:標準是內建 (OOTB)，而「自訂」包含 eVars 與屬性。如需訪客ID層級資訊，建議您使用「訪客ID」，而非「Experience Cloud訪客ID」。<ul><li>訪客 ID 是 Analytics 使用的最終 ID。這會是 AID (如果客戶是舊的) 或 MID (如果客戶是新的，或已清除從 MC 訪客 ID 服務啟動以來的 Cookie)。</li><li>僅針對新的客戶，或客戶已清除從 MC 訪客服務啟動以來的 Cookie，才會設定 Experience Cloud 訪客 ID。</li></ul> |
   | 量度 | 選取所需的量度。標準是 OOTB，而「自訂」包含自訂事件。 |
   | 報表預覽 | 在排定報表之前檢閱設定。<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | 計劃傳送 | 輸入要將檔案傳送到哪個電子郵件地址、命名檔案，然後選取[!UICONTROL 「立即傳送」]。<br>注意: 在[!UICONTROL 「進階傳送選項」]<br>![下，您可以透過 FTP 傳送檔案排程傳送](/help/main/c-reports/assets/datawarehouse3.png)。 |

1. 按一下&#x200B;**[!UICONTROL 「請求此報表」]**。

   檔案傳送最多可能需要 72 小時，視所要求的資料量而定。您隨時可以按一下「[!UICONTROL 工具] > [!UICONTROL 資料倉儲] > [!UICONTROL 要求管理程式]」，以檢查要求的進度。

   如果您想重新要求您過去曾要求的資料，您可以複製以下專案的舊請求： [!UICONTROL 請求管理員] 視需要。

如需 [!DNL Data Warehouse] 的相關資訊，請參閱 [!DNL Analytics] 說明文件中的下列連結:

* [建立 Data Warehouse 請求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [Data Warehouse最佳實務](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)

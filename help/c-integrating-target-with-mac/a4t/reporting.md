---
keywords: target的分析；a4t;analytics作為報告來源；analytics
description: 瞭解如何使用Analytics for Target(A4T)。 A4T提供使用Analytics量度和觀眾區隔之Target活動的Analytics報表存取權。
title: 如何在A4T中使用報表？
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 7b2d5251275f42da66d09370501d0882671d5cca
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 28%

---


# A4T 報表{#a-t-reporting}

使用[!DNL Adobe Analytics]作為[!DNL Adobe Target](A4T)的報告來源，可讓您存取[!DNL Target]活動的[!DNL Analytics]報告。

您可以在[!DNL Analytics]和[!DNL Target]中檢視活動的報表。

如需使用[!DNL Target]的[!DNL Analytics]報告最佳實務，請造訪本Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)。[

## 概述 {#section_035A62D65608423285D8A5A54731E2C5}

[!DNL Analytics]和[!DNL Target]報表都會測量進入者（進入測試的人員），而非網站的訪客。

每次訪客在頁面上看到活動內容時，[!DNL Target]會對[!DNL Analytics]進行伺服器間直接呼叫，包括訪客所看見的活動和體驗。 [!DNL Target] 也會在 [!DNL Analytics] 進行轉換時呼叫。[!DNL Analytics] 將轉換新增為名為「活 [!DNL Analytics] 動轉換」的特定新事件，此事件會與收集到的其他資料一起追蹤 [!DNL Analytics]。

當使用[!UICONTROL Select]操作且您對&#x200B;*進入者*&#x200B;排序時，報表中只會顯示在選定時段內接收進入者的體驗。

>[!NOTE]
>
>由[!DNL Target]提供支援的報表延遲4分鐘。 對於由A4T提供支援的活動，在[!DNL Target]和[!DNL Analytics]報表中，最多需要24小時的時間，在活動最初儲存後，報表資料才能依體驗劃分。 在這最初 24 小時收集的資料仍然正確，且會指派給正確的體驗。

## Analytics 中的報表  {#analytics}

在[!DNL Analytics]中，啟用A4T整合後，有數個維度和量度可供使用。

### 維度

* [!UICONTROL Analytics for Target]  —— 透過整合傳入的父ID。此維的格式為`Activity ID:Experience ID:3rd ID`。 以下維度是此維度的分類。
* [!UICONTROL Target 活動]
* [!UICONTROL 目標體驗]
* [!UICONTROL 目標活動] >體 [!UICONTROL 驗]
* [!UICONTROL 第3個ID] -可以忽略

### 量度

* [!UICONTROL 活動印象] -符合報  表中的入口 [!DNL Target] 數。
* [!UICONTROL 活動轉換] -符合報 [!UICONTROL 表] 中的自訂轉換 [!DNL Target] 數目。

在[!DNL Analysis Workspace]中，使用[!UICONTROL  Analytics for Target]面板，以提升度和自信度分析您的[!DNL Target]活動和體驗。 如需詳細資訊，請參閱&#x200B;*分析工具指南*&#x200B;中的[Analytics for Target(A4T)面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html)。

>[!IMPORTANT]
>
>如果[!DNL Analytics]中的[!UICONTROL Target活動]報表列出「未指定」，而非列出您的活動，則需要對您布建的帳戶進行更新。 請聯絡客戶服務以解決此問題。

如需詳細資訊和範例，請開啟[Analytics &amp; Target:分析最佳做法](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)教學課程，由Adobe Experience League提供。

## Target 中的報表 {#section_C0D1F17F88374B6690BF904D7B83B42E}

當[!DNL Analytics]用作報告來源時，[!DNL Target]中的報告會顯示從[!DNL Analytics]收集的資料。 此報告與其他[!DNL Target]報告有所不同：

* [!UICONTROL 觀眾]清單顯示[!DNL Analytics]報表套裝的觀眾。
* [!UICONTROL 量度]清單顯示透過[!DNL Analytics]可用的每個量度。

   每個量度都可用，包括[!DNL Analytics]內建的任何自訂或計算量度。

   任何增加的數字都會在報告中顯示為正面，即使不希望增加也是如此。 例如，即便您想要較低的跳出率仍顯示了較高的跳出率，因為獲勝者會具有最高的提升度。根據報表進行決策時，請注意這些和類似的量度，以及是否您偏好減少或增加這些數字。

您可以在活動開始後或甚至測試完成後，將量度或對象套用至[!DNL Target]中的報表。 您事先完全不需要知道要測量什麼。

按一下，直接從活動報表頁面檢視完整的[!DNL Analytics]報表。

## 活動建立 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在建立活動期間，您必須在[!UICONTROL 「設定」]頁面上指定活動的目標。此目標會成為報表的預設量度，且一律列為量度選取器的第一個選項。您無法像一般 Target 活動一樣選取要報告的區段。具有[!DNL Analytics]的測試使用[!DNL Adobe Analytics]區段，而非[!DNL Target]對象。

## 執行Analytics for Target的離線計算(A4T){#section_33A97A691F3A45D497DAF57A844388F0}

您可以為 A4T 執行離線計算，但是它需要在 [!DNL Analytics] 中進行資料匯出的步驟。

如需詳細資訊，請參閱[對 Analytics for Target (A4T) 執行離線計算](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。

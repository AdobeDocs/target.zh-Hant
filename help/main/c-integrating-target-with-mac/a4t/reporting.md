---
keywords: 目標分析；a4t;analytics作為報告源；analytics
description: 瞭解如何使用分析 [!DNL Target] (A4T)。 A4T提供對Analytics報表的訪問 [!DNL Target] 使用分析度量和受眾段的活動。
title: 如何在A4T中使用Reporting?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 29%

---

# A4T 報表

使用 [!DNL Adobe Analytics] 作為報告源 [!DNL Adobe Target] (A4T)允許您訪問 [!DNL Analytics] 報告 [!DNL Target] 活動。

您可以查看兩者中活動的報告 [!DNL Analytics] 和 [!DNL Target]。

用於報告最佳做法 [!DNL Analytics] 為 [!DNL Target]。 [訪問Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)。

## 總覽 {#section_035A62D65608423285D8A5A54731E2C5}

兩者 [!DNL Analytics] 和 [!DNL Target] 報告衡量的是進入者(進入test的人員)，而不是站點的訪問者。

每次訪問者在頁面上看到活動內容， [!DNL Target] 進行伺服器到伺服器的直接呼叫 [!DNL Analytics]包括參觀者看到的活動和體驗。 [!DNL Target] 也是 [!DNL Analytics] 進行轉換時。 [!DNL Analytics] 將轉換添加為特定的新 [!DNL Analytics] 名為「活動轉換」的事件，該事件與收集的其他資料一起跟蹤 [!DNL Analytics]。

當 [!UICONTROL 選擇] 操作，然後排序 *新入者*，則報告中只顯示在選定時間段內接收到的參賽者的體驗。

>[!NOTE]
>
>報告由 [!DNL Target] 有四分鐘的延遲。 對於由A4T驅動的活動， [!DNL Target] 和 [!DNL Analytics] 報告時，在最初保存活動後最多需要24小時，然後才能按經驗分解報告資料。 在這最初 24 小時收集的資料仍然正確，且會指派給正確的體驗。

## Analytics 中的報表 {#analytics}

在 [!DNL Analytics]，在啟用A4T整合後，有幾個維和度量可用。

### 維度

* [!UICONTROL 目標分析]  — 通過整合傳入的父ID。 此維的格式為 `Activity ID:Experience ID:3rd ID`。 以下維是此維的分類。
* [!UICONTROL Target 活動]
* [!UICONTROL 目標體驗]
* [!UICONTROL 目標活動] > [!UICONTROL 經驗]
* [!UICONTROL 第3個ID]  — 可忽略

### 量度

* [!UICONTROL 活動印象]  — 匹配 [!UICONTROL 新入者] 的 [!DNL Target] 報告。
* [!UICONTROL 活動轉換]  — 匹配 [!UICONTROL 自定義轉換] 的 [!DNL Target] 報告。

在 [!DNL Analysis Workspace]，使用 [!UICONTROL 目標分析] 分析 [!DNL Target] 充滿信心的活動和經驗。 有關詳細資訊，請參見 [目標(A4T)分析面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html??lang=zh-Hant) 的 *分析工具指南*。

>[!IMPORTANT]
>
>如果 [!UICONTROL 目標活動] 報告 [!DNL Analytics] 列出「未指定」而不是列出您的活動，需要更新您的預配帳戶。 請聯絡客戶服務以解決此問題。

有關詳細資訊和示例，請開啟 [分析和目標：分析的最佳做法](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) 教程，由Adobe Experience League提供。

## 報告 [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

當 [!DNL Analytics] 用作報告源，在 [!DNL Target] 顯示從 [!DNL Analytics]。 報告與其他報告有所不同 [!DNL Target] 報告：

* 的 [!UICONTROL 觀眾] 清單顯示您可用的受眾 [!DNL Analytics] 報表套件。
* 的 [!UICONTROL 度量] 清單顯示每個可用度量 [!DNL Analytics]。

   每個度量都可用，包括任何內置的自定義或計算度量 [!DNL Analytics]。

   任何增加的數字都會在報告中顯示為正數，即使不希望增加。 例如，即便您想要較低的跳出率仍顯示了較高的跳出率，因為獲勝者會具有最高的提升度。根據報表進行決策時，請注意這些和類似的量度，以及是否您偏好減少或增加這些數字。

您可以將度量或受眾應用於中的報告 [!DNL Target] 活動啟動後，甚至test完成後。 您事先完全不需要知道要測量什麼。

按一下以查看完整 [!DNL Analytics] 直接從活動報告頁報告。

## 活動建立 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在建立活動期間，您必須在[!UICONTROL 「設定」]頁面上指定活動的目標。此目標會成為報表的預設量度，且一律列為量度選取器的第一個選項。您無法像一般 Target 活動一樣選取要報告的區段。test [!DNL Analytics] 使用 [!DNL Adobe Analytics] 段 [!DNL Target] 觀眾。

## 正在為Adobe Target分析執行離線計算(A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

您可以為 A4T 執行離線計算，但是它需要在 [!DNL Analytics] 中進行資料匯出的步驟。

如需詳細資訊，請參閱[對 Analytics for Target (A4T) 執行離線計算](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。

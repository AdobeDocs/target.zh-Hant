---
keywords: faq;常見問題集;analytics for target;a4T;提升度;隨選;報表產生器;可信度
description: 使用Analytics時查找有關提升和信心問題的答案 [!DNL Target] (A4T)。 A4T允許您使用Analytics報告 [!DNL Target] 活動。
title: 在哪裡可以找到有關A4T提升和信心的資訊？
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 28%

---

# 提升度和可信度 - A4T 常見問題集

本主題包含使用時經常詢問的有關提升和信心的問題的答案 [!DNL Adobe Analytics] 作為 [!DNL Adobe Target] (A4T)。

## 我可以對 A4T 執行離線計算嗎? {#section_55B5B750E17D414CAECBEECE27B15D81}

您可以為 A4T 執行離線計算，但是它需要在 [!DNL Analytics] 中進行資料匯出的步驟。如需詳細資訊，請參閱[信賴等級與信賴區間](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)中的「對 Target (A4T) 執行離線計算」。

## 如何計算提升度? {#section_8CAE788EED5646C4B1D64A0D22070734}

提升度是控制頁面結果與成功測試變量之間的百分比差異。

## 如何計算可信度? {#section_97DB24D833E742988318CA65DA65DAD9}

置信度是以百分比表示的等於 `1 - p-value`的子菜單。 `p-value` 從ttest計算。 請參閱 [轉換率](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。

## 在計算量度上為何看不到提升度和可信度? {#lift-confidence}

提升函式和置信函式當前不支援計算度量。 分析在聚合級別而不是訪問者級別計算度量。 特別是，信心是訪客層面的計算。

非計算（標準）事件在提升和置信度方面得到支援。 在升力功能中，他們成為分子；分子本身不能是計算。 分母是標準化指標（印象、訪問或訪問者）。 標準事件的一些示例包括訂單、收入、活動轉換、自定義事件1-1000等。 通常的優化指標，如會話率（訂單/訪問者）和RPV（收入/訪問者），都受到支援，以提升信心。

不支援的度量或使用案例的示例包括：

* 平均訂單值（收入/訂單，每訪問者）。 不支援AOV，因為分子是計算度量。 相反，建議考慮AOV的兩個影響指標 — Revenue Per Visitor和Conversion Rate。
* 計算的度量是標準事件的總和。 例如，您可以將十個不同的潛在顧客表單跟蹤到十個獨立的事件中，然後將它們相加以獲得總的潛在顧客提交。 跟蹤這些事件的推薦方法是在分析中實施單個線索提交事件，然後使用eVar收集線索表單的類型。 使用此方法需要的變數較少，並確保在提升函式和置信度函式中可以使用單個線索提交度量。

## A4T 如何處理可信度計算? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

[!DNL Adobe Analytics] 將所有度量視為非二進位，因此，以與常規ttest中使用二進位度量不同的方式計算置信度/p值。 具體而言，A4T使用的計算允許每個用戶具有連續的度量結果（不僅是每個用戶1或0），因此必須適當地計算每個體驗的方差（或相關的標準差）。 不考慮極端命令。 此外，置信度計算不適用於多個報價的Bonferroni修正。

## 提升度和可信度可用在隨選和報表產生器中嗎? 如果不是原生功能，我可以在產生器中自行操作嗎? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

提升度和可信度在隨選或報表產生品中沒有作用，您也不能自行對連續變數做這種計算。可手動針對二進位量度進行計算嗎?

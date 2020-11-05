---
keywords: faq;frequently asked questions;analytics for target;a4T;lift;ad hoc;report builder;confidence
description: 此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於提升度和可信度問題的回答。
title: 提升度和可信度 - A4T 常見問題集
feature: a4t troubleshooting
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 50%

---


# 提升度和可信度 - A4T 常見問題集{#lift-and-confidence-a-t-faq}

此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於提升度和可信度問題的回答。

## 我可以對 A4T 執行離線計算嗎? {#section_55B5B750E17D414CAECBEECE27B15D81}

您可以為 A4T 執行離線計算，但是它需要在 [!DNL Analytics] 中進行資料匯出的步驟。如需詳細資訊，請參閱[信賴等級與信賴區間](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)中的「對 Target (A4T) 執行離線計算」。

## 如何計算提升度? {#section_8CAE788EED5646C4B1D64A0D22070734}

提升度是控制頁面結果與成功測試變量之間的百分比差異。

## 如何計算可信度? {#section_97DB24D833E742988318CA65DA65DAD9}

信賴水準是指除了單獨因為機遇以外的其他理由，而造成測量轉換率與優勝頁面轉換率不同的機率。

## 在計算量度上為何看不到提升度和可信度? {#lift-confidence}

提升度和信賴函式目前不支援計算量度。 這是由於Analytics會在匯總層級計算量度，而非在訪客層級計算量度。 信賴度尤其是訪客層級的計算。

非計算（標準）事件支援提升度和可信度。 它們成為提升函式中的分子；分子本身不能是計算。 分母是標準化量度（印象、瀏覽或訪客）。 標準事件的一些範例包括訂購、收入、活動轉換、自訂事件1-1000等。 這表示一般最佳化度量，例如對話率（訂購／訪客）和RPV（收入／訪客）都支援提升度和可信度。

不支援的度量或使用案例的範例包括：

* 平均訂購值（每個訪客的收入／訂購）。 不支援AOV，因為分子是計算量度。 建議改為考慮AOV的兩個影響度量- 「每位訪客收入」和「轉換率」。
* 作為標準事件總和的計算量度。 例如，您可以追蹤10個不同的銷售機會表單，並將它們加在一起，以取得總的銷售機會提交。 建議的追蹤這些事件方法是在Analytics中實作單一銷售機會提交事件，然後使用eVar來收集銷售機會表單類型。 使用此方法所需的變數較少，並可確保您在提升度和可信度函式中使用單一銷售機會提交量度。

## A4T 如何處理可信度計算? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T 對平方和資料採用非二進位量度計算。變數是利用平方和資料來計算。極端順序不納入考量。此外，信賴計算不適用於多個選件的Bonferroni修正。

## 提升度和可信度可用在隨選和報表產生器中嗎? 如果不是原生功能，我可以在產生器中自行操作嗎? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

提升度和可信度在隨選或報表產生品中沒有作用，您也不能自行對連續變數做這種計算。可手動針對二進位量度進行計算嗎?

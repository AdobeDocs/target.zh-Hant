---
keywords: faq;常見問題集;analytics for target;a4T;提升度;隨選;報表產生器;可信度
description: 為 [!DNL Target] (A4T)使用Analytics時，尋找提升度和可信度的相關問題解答。 A4T可讓您對 [!DNL Target] 個活動使用Analytics報告。
title: 哪裡可以找到A4T的提升度和可信度相關資訊？
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 25%

---

# 提升度和可信度 - A4T 常見問題集

此主題包含使用[!DNL Adobe Analytics]做為[!DNL Adobe Target] (A4T)的報表來源時，經常詢問關於提升度和可信度問題的回答。

## 我可以對 A4T 執行離線計算嗎? {#section_55B5B750E17D414CAECBEECE27B15D81}

+++回答
您可以為 A4T 執行離線計算，但是它需要在 [!DNL Analytics] 中進行資料匯出的步驟。如需詳細資訊，請參閱[A/Bn測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

+++

## 如何計算提升度? {#section_8CAE788EED5646C4B1D64A0D22070734}

+++回答
提升度是控制頁面結果與成功測試變量之間的百分比差異。

+++

## 如何計算可信度? {#section_97DB24D833E742988318CA65DA65DAD9}

+++回答
信賴等級是以百分比表示並等於`1 - p-value`的機率，其中`p-value`是從t檢定算出的。 檢視A/Bn測試中的[統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

+++

## 在計算量度上為何看不到提升度和可信度? {#lift-confidence}

+++回答
提升度和可信度函式目前不支援計算量度。 Analytics會在彙總層級計算量度，而非訪客層級。 信賴度尤其是一種訪客層級的計算。

提升度和可信度支援非計算（標準）事件。 它們會成為提升函式中的分子；分子不能是計算本身。 分母是標準化量度（曝光數、造訪次數或訪客）。 標準事件的部分範例包括訂購、收入、活動轉換、自訂事件1-1000等。 提升度和可信度支援常見的最佳化量度，例如交談率（訂單/訪客）和RPV （收入/訪客）。

不支援的量度或使用案例包括：

* 平均訂購值（收入/訂購、每位訪客）。 不支援AOV，因為分子是計算量度。 建議改為考慮兩個影響AOV的量度：每位訪客帶來的收入和轉換率。
* 作為標準事件總和的計算量度。 例如，您可以將10個不同的潛在客戶表單追蹤為10個不同的事件，然後將它們相加以取得潛在客戶提交總數。 追蹤這些事件的建議方法是，在Analytics中實作單一銷售機會提交事件，然後使用eVar收集銷售機會表單的型別。 使用此方法所需的變數較少，並可確保您可在提升度和信賴函式中使用單一銷售機會提交量度。

+++

## A4T 如何處理可信度計算? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

+++回答
[!DNL Adobe Analytics]將所有量度視為非二進位，因此計算可信度/p值的方式與在一般t測試中使用二進位量度不同。 具體來說，A4T使用的計算允許每個使用者都有連續的量度結果（不僅僅每個使用者為1或0），因此每個體驗的變異數（或相關的標準差）必須適當地計算。 極端訂單不予考慮。 此外，信賴度計算不會針對多個選件套用Bonferroni校正。

+++

## 提升度和可信度可用在隨選和報表產生器中嗎? 如果不是原生功能，我可以在產生器中自行操作嗎? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

+++回答
提升度和可信度在隨選或報表產生品中沒有作用，您也不能自行對連續變數做這種計算。可手動針對二進位量度進行計算嗎?
+++

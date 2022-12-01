---
keywords: faq;常見問題集;analytics for target;a4T;提升度;隨選;報表產生器;可信度
description: 針對使用Analytics時的提升度和可信度問題尋找解答 [!DNL Target] (A4T)。 A4T可讓您對 [!DNL Target] 活動。
title: 哪裡可以找到關於A4T提升度和可信度的資訊？
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 15%

---

# 提升度和可信度 - A4T 常見問題集

此主題包含使用時經常詢問關於提升度和可信度問題的回答 [!DNL Adobe Analytics] 作為的報表來源 [!DNL Adobe Target] (A4T)。

## 我可以對 A4T 執行離線計算嗎? {#section_55B5B750E17D414CAECBEECE27B15D81}

+++答案您可以對A4T執行離線計算，但需要中進行資料匯出的步驟 [!DNL Analytics]. 如需詳細資訊，請參閱 [A/Bn測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## 如何計算提升度? {#section_8CAE788EED5646C4B1D64A0D22070734}

+++「答案提升度」是控制頁面結果與成功測試變體之間的百分比差異。

+++

## 如何計算可信度? {#section_97DB24D833E742988318CA65DA65DAD9}

+++答案信賴等級是以百分比表示，等於 `1 - p-value`，其中 `p-value` 是從t檢定計算。 請參閱 [A/Bn測試中的統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## 在計算量度上為何看不到提升度和可信度? {#lift-confidence}

+++提升度和可信度函式目前不支援答案計算量度。 Analytics會在匯總層級計算量度，而非在訪客層級計算。 可信度尤其是訪客層級的計算。

提升度和可信度支援非計算（標準）事件。 他們成為提升度函式中的分子；分子不能是計算本身。 分母是標準化量度（曝光數、造訪或訪客）。 標準事件的某些範例包括訂購、收入、活動轉換、自訂事件1-1000等。 提升度和可信度可支援通用最佳化量度，例如對話率（訂購/訪客）和RPV（收入/訪客）。

不支援的量度或使用案例範例包括：

* 平均訂購值（每位訪客的收入/訂購）。 不支援AOV，因為分子是計算量度。 相反地，建議考慮AOV的兩個影響量度 — 每位訪客的收入和轉換率。
* 標準事件總和的計算量度。 例如，您可以將10個不同的銷售機會表單追蹤為10個不同的事件，然後將其加入一起，以取得銷售機會提交總數。 追蹤這些事件的建議方法是在Analytics中實作單一銷售機會提交事件，然後使用eVar來收集銷售機會表單類型。 使用此方法需要的變數較少，且可確保在提升度和可信度函式中使用單一銷售機會提交量度。

+++

## A4T 如何處理可信度計算? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

+++回答
[!DNL Adobe Analytics] 將所有量度視為非二進位，因此，會以與在一般t檢定中使用二進位量度不同的方式計算信賴/p值。 具體而言，A4T所使用的計算可讓每位使用者擁有持續的量度結果（而非每位使用者只有1或0），因此必須適當計算每個體驗的變異數（或相關的標準差）。 不考慮極端訂單。 此外，可信度計算不會對多個選件套用Bonferroni校正。

+++

## 提升度和可信度可用在隨選和報表產生器中嗎? 如果不是原生功能，我可以在產生器中自行操作嗎? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

+++回答提升度和可信度在臨機或Report Builder中無法運作，且無法自行計算連續變數。 可手動針對二進位量度進行計算嗎?
+++

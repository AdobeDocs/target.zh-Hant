---
description: 此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於提升度和可信度問題的回答。
keywords: faq;常見問題集;analytics for target;a4T;提升度;隨選;報表產生器;可信度
seo-description: 此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於提升度和可信度問題的回答。
seo-title: 提升度和可信度 - A4T 常見問題集
solution: Target
title: 提升度和可信度 - A4T 常見問題集
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 提升度和可信度 - A4T 常見問題集{#lift-and-confidence-a-t-faq}

此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於提升度和可信度問題的回答。

## 我可以對 A4T 執行離線計算嗎? {#section_55B5B750E17D414CAECBEECE27B15D81}

您可以為 A4T 執行離線計算，但是它需要在 [!DNL Analytics] 中進行資料匯出的步驟。如需詳細資訊，請參閱[信賴等級與信賴區間](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)中的「對 Target (A4T) 執行離線計算」。

## 如何計算提升度? {#section_8CAE788EED5646C4B1D64A0D22070734}

提升度是控制頁面結果與成功測試變量之間的百分比差異。

## 如何計算可信度?  {#section_97DB24D833E742988318CA65DA65DAD9}

信賴水準是指除了單獨因為機遇以外的其他理由，而造成測量轉換率與優勝頁面轉換率不同的機率。

## 在計算量度上為何看不到提升度和可信度?  {#section_D3E44E24782A409DBD88AE4D1595CB58}

目前無法為計算量度產生提升度和可信度。不過，在大部情況下，這不會有問題，因為正規化量度會將提升度正規化。例如，若您為順序選取提升度，而正規化量度是造訪，則會依兩者的比例 (即轉換率) 計算提升度。

## A4T 如何處理可信度計算?  {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T 對平方和資料採用非二進位量度計算。變數是利用平方和資料來計算。極端順序不納入考量。

任何 Analytics 區段皆可套用至報表。在其他區段選項以外出現「極端順序」的原因在此。也可建立量度來做限制，例如訪客的轉換次數。

## 提升度和可信度可用在隨選和報表產生器中嗎? 如果不是原生功能，我可以在產生器中自行操作嗎? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

提升度和可信度在隨選或報表產生品中沒有作用，您也不能自行對連續變數做這種計算。可手動針對二進位量度進行計算嗎?

---
keywords: 自動化流量分配；鎖定目標；獲勝者；統計保證；信賴度；決定獲勝者；提升度；信賴度；預設；預設體驗；自動分配；自動分配
description: 瞭解如何解譯[!UICONTROL 自動分配] A/B活動結果，並著重於提升度和信賴度等關鍵指標。
title: 如何解譯[!UICONTROL 自動分配]報告？
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
TQID: 'https://experienceleague.adobe.com/o4mFGMk-M5QUvJ57kYnfjMPvVZL8l6YegJQSJyHjAxc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f2d0aafb-18af-41a0-a32e-2788eafacc2b
    internal-label: Auto-allocate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 174d4631b6f4a481c039bd7fff52a8e70161e19e
workflow-type: tm+mt
source-wordcount: '1357'
ht-degree: 3%
---
# 解譯[!UICONTROL 自動分配]報告 {#interpret-auto-allocate-reports}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何識別&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動的成功體驗（由&#x200B;**[!UICONTROL 自動分配]**&#x200B;提供的統計保證），以及如何讀取報告中的提升度和信賴度數字。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中&#x200B;**[!UICONTROL 自動分配]** A/B活動的報告會顯示該活動是否已找到獲勝者，以及[!DNL Target]對該結果的信賴度。 獲勝者徽章、提升度和信賴度等指標可協助您解讀結果。

許多行銷人員犯了一種錯誤，在結果指出明確的贏家之前便提早宣告獲勝體驗。 [!DNL Target]讓您更容易決定獲勝者。 如需宣告獲勝者的一般資訊，請參閱[十個常見的A/B測試陷阱以及避免方法](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)。

## 識別成功體驗 {#identify-winner}

當您使用&#x200B;**[!UICONTROL 自動分配]**&#x200B;功能時，[!DNL Target]會在活動頁面頂端顯示徽章。 在活動達到最低轉換次數且有足夠信賴度之前，徽章會指出「尚未有贏家」。

![無贏家徽章](/help/main/c-activities/automated-traffic-allocation/assets/no-winner-new.png)

宣告明確的獲勝者時，[!DNL Target]會顯示「獲勝者：體驗&#x200B;*X*」徽章。

![獲勝者徽章](/help/main/c-activities/automated-traffic-allocation/assets/winner-new.png)

獲勝者徽章也會顯示在&#x200B;**[!UICONTROL 活動]**&#x200B;清單中的活動資訊快顯視窗中，因此您可以看到&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動的狀態，而不需要開啟它。

>[!NOTE]
>
>**[!UICONTROL 自動分配]**&#x200B;活動旨在從所有選項中尋找最佳體驗，而不只是與控制項進行成對比較。

## [!UICONTROL 自動分配]的統計保證 {#statistical-guarantees}

在A/B活動結束時，**[!UICONTROL 自動分配]**&#x200B;可保證已決定的獲勝者有5%的有效誤判率。 這表示在活動的所有體驗之中，只有 5% 的時間，決定的獲勝者實際上不是最佳體驗。

對於[A/A測試](/help/main/c-activities/t-test-ab/aa-testing.md) （具有相同的體驗），[!DNL Target]會結束不到5%時間的測試。 A/A測試的預期行為是無限期執行，因此獲勝者徽章絕不會出現。

### 信賴度和p值 {#confidence-p-values}

[!DNL Target]沒有對&#x200B;**[!UICONTROL 自動分配]**&#x200B;使用p值型信賴度。 **[!UICONTROL 自動分配]**&#x200B;活動中的&#x200B;**[!UICONTROL 信賴度]**&#x200B;欄會顯示體驗在1%的錯誤邊際內成為獲勝者的機率。 演演算法使用最佳和次最佳轉換率之間的最小可偵測效果為1%，並使用[Bernstein不等式](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29)來計算此機率。

一般A/B測試是根據p值來計算可信度，而p值會「大致」計算指定體驗與控制體驗不同的機率。 這些 p 值只能用來判斷體驗是否可能與控制不同。 無法用來判斷某個體驗是否與其他體驗（而非控制）不同。

>[!IMPORTANT]
>
>在預先定義的最低轉換次數後，[!DNL Target]會顯示獲勝者。 不過，挑選獲勝者的最終決定應一律以[!DNL Adobe Target]樣本大小計算器的結果為基礎。 [!DNL Target]不考慮網站的基本轉換率，以及饋送至計算器以決定活動持續期間的其他重要方面。 因此，根據最低轉換次數，[!DNL Target]可能會顯示比保證更早的獲勝者。 如需詳細資訊，請參閱[樣本大小電腦](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)。

## 瞭解提升度和可信度報告 {#lift-confidence}

**[!UICONTROL 自動分配]**&#x200B;活動的&#x200B;**[!UICONTROL 報表]**&#x200B;索引標籤會顯示下列圖：

| 圖 | 說明 |
|---|---|
| **控制體驗** | 第一個體驗（預設為體驗A）一律定義為&#x200B;**[!UICONTROL 報表]**&#x200B;標籤上的「控制」體驗。 在用來判斷體驗效能的模型中，此體驗不會被視為真正的統計控制，但會被視為報表中某些圖表的參考或基準。 |
| **提升度** | 「提升度」值以及每個體驗的95%界限一律會參考定義的「控制」體驗進行計算。 「控制」體驗本身無法具有提升度，因此報告會顯示此體驗的空白「 — 」值。<br>不同於A/B測試，在&#x200B;**[!UICONTROL 自動分配]**&#x200B;測試中，如果體驗的執行效能比定義的控制項差，則不會報告負提升值。 而是顯示「 — 」。 |
| **信賴區間** | 顯示的&#x200B;**[!UICONTROL 信賴區間]**&#x200B;長條代表某個體驗平均轉換率預估值的95%信賴區間。 這些長條會根據定義的「控制」體驗以不同色彩標示：<ul><li>「控制」體驗的列永遠是灰色。</li><li>信賴區間低於「控制」體驗信賴區間的部分為紅色。</li><li>在「控制」體驗的信賴區間以上的信賴區間部分為綠色。</li></ul> |
| **獲勝者** | 領先體驗的95% **[!UICONTROL 信賴區間]**&#x200B;與任何其他體驗不重疊時，就會找到獲勝者。 成功體驗會在體驗名稱左側和「成功者」橫幅中指定綠色星形徽章。 看不到任何星星時，橫幅會顯示「尚未有贏家」，而且尚未找到贏家。 |
| **信賴數** | 目前領先或勝出的體驗旁邊也會報告「信賴度」數字。 此數字只會在領先體驗的&#x200B;**[!UICONTROL 信賴度]**&#x200B;達到至少60%時報告。<ul><li>如果&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動中有兩個體驗存在，數字代表該體驗表現優於其他體驗的信賴等級。</li><li>如果存在兩個以上的體驗，數字代表體驗的執行效能優於定義的「控制」體驗的信賴等級。</li><li>如果「控制」體驗獲勝，則不會報告「信賴度」數字。</li></ul> |

## 常見問題集 {#faq}

請考量下列常見問題的回答。

+++ 此活動已進行幾天。 為何所有信賴值仍顯示0%？

下列任一原因可說明為何所有體驗之報表的&#x200B;**[!UICONTROL 信賴度]**&#x200B;欄中會顯示0%：

* 手動A/B測試和&#x200B;**[!UICONTROL 自動分配]**&#x200B;使用不同的統計資料來顯示&#x200B;**[!UICONTROL 信賴度]**&#x200B;值。

  手動A/B測試使用以[Welch的t檢定](https://en.wikipedia.org/wiki/Welch%27s_t-test)為基礎的p值。 p值是尋找在體驗與控制之間觀察到（或更極端）之差異的機率，因為實際上並沒有這種差異。 這些p值只能用來判斷觀察到的資料是否與指定體驗一致，並且有相同的控制。 無法用來判斷某個體驗是否與其他體驗（而非控制）不同。

  **[!UICONTROL 自動分配]**&#x200B;會顯示指定體驗成為活動中所有體驗之真正獲勝者的機率。 只有成功體驗（最有可能是成功者）具有非零信賴值。 所有其他最有可能是損失者，並顯示0%。

* **[!UICONTROL 自動分配]**&#x200B;只有在成功體驗收集到60%的信賴度後，才會開始顯示信賴度。 這些信賴等級通常大約會顯示在一般A/B測試完成所需時間的一半（雖然此時間範圍並無保證）。 若要判斷一般A/B測試會執行多久，請使用[!DNL Adobe Target] [樣本大小電腦](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)：在「基準轉換率」中輸入控制項的轉換率，「提升度」為&quot;5%&quot;，「信賴度」為95%。 通常，信賴度會在每個體驗收集至少50%的必要範例後開始顯示。 這讓您知道何時開始出現可信度。

* 如果報表在各個方面顯示0%，則活動可能為時尚早。

+++

+++ 使用[!UICONTROL Analytics]做為報告來源(A4T)的[!UICONTROL 自動分配]活動是否有「無贏家」、「贏家」和「星星」徽章可用？

「尚未有贏家」和「贏家」徽章會出現在&#x200B;**[!UICONTROL 活動]**&#x200B;清單中的活動資訊快顯視窗中。 在[!DNL Analysis Workspace]的&#x200B;**[!UICONTROL A4T]**&#x200B;面板中或您在[!DNL Target]中檢視相同報表時，不會顯示這些報表。 如果A4T **[!UICONTROL 自動分配]**&#x200B;活動的[!DNL Target]報告顯示獲勝者「星星」徽章，請忽略該報告。

如需此專案以及其他限制和附註的詳細資訊，請參閱[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動&#x200B;*在* A4T支援中的[自動分配](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa)。

+++

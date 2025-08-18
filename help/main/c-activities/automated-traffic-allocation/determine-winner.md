---
keywords: 自動化流量分配；鎖定目標；獲勝者；統計保證；信賴度；決定獲勝者；提升度；信賴度；預設；預設體驗；自動分配；自動分配
description: 探索如何解譯[!UICONTROL Auto-Allocate] A/B活動結果，並專注於提升度和信賴度等關鍵指標。
title: 如何解譯[!UICONTROL Auto-Allocate]報表？
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 20%

---

# 解譯[!UICONTROL Auto-Allocate]報告

透過檢查重要指標（包括提升度和信賴度）來解譯[!UICONTROL Auto-Allocate]中[!UICONTROL Adobe Target] A/B活動的結果。

許多行銷人員犯了一種錯誤，在結果指出明確的贏家之前便提早宣告獲勝體驗。[!DNL Target]讓您更容易決定獲勝者。

如需宣告獲勝者的一般資訊，請參閱[十個常見的A/B測試陷阱以及避免方法](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)。

## 識別成功體驗 {#section_24007470CF5B4D30A06610CE8DD23CE3}

使用[!UICONTROL Auto-Allocate]功能時，[!DNL Target]會在活動的頁面上方顯示徽章，指出「尚未有贏家」，直到活動達到具有足夠信賴的最低轉換數量為止。

![無贏家徽章](/help/main/c-activities/automated-traffic-allocation/assets/no-winner-new.png)

宣告明確的獲勝者時，[!DNL Target]會顯示「獲勝者：體驗&#x200B;*X*」徽章。

![獲勝者徽章](/help/main/c-activities/automated-traffic-allocation/assets/winner-new.png)

>[!NOTE]
>
>[!UICONTROL Auto-Allocate]活動的設計目的，是為了在所有選項中尋找最佳體驗，而不只是與控制項進行成對比較。

## [!UICONTROL Auto-Allocate]的統計保證 {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

在A/B活動結束時，[!UICONTROL Auto-Allocate]可保證已決定的獲勝者有5%的有效誤判率。 這表示在活動的所有體驗之中，只有 5% 的時間，決定的獲勝者實際上不是最佳體驗。對於[A/A測試](/help/main/c-activities/t-test-ab/aa-testing.md) （具有相同的體驗），[!DNL Target]會結束不到5%時間的測試。 A/A 測試 (使用相同的體驗) 的預期行為是無限期執行，所以獲勝者徽章永遠不會出現。

[!DNL Target]沒有對[!UICONTROL Auto-Allocate]使用p值型信賴度。

[!UICONTROL Confidence]活動中的[!UICONTROL Auto-Allocate]欄會顯示體驗在1%的錯誤邊際內成為獲勝者的機率。 演演算法使用最佳和次最佳轉換率之間的最小可偵測效果為1%。 演演算法使用[Bernstein不等式](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29)來計算此機率。

一般 A/B 測試會根據 p 值來計算信賴度。[!UICONTROL Auto-Allocate]不使用p值。 P 值會「寬鬆」計算所給定體驗與控制項不同的機率。這些 p 值只能用來判斷體驗是否可能與控制不同。這些值只能用來判斷體驗是否與另一個體驗 (非控制) 不同。

>[!IMPORTANT]
>
>[!DNL Target]會在預先定義的最低轉換次數之後顯示獲勝者；不過，挑選獲勝者的最終決定應一律會在[!DNL Adobe Target]樣本大小電腦的結果上做出。 [!DNL Target]不考慮網站的基本轉換率，以及饋送至計算器以決定活動持續期間的其他重要方面。 因此，根據最低轉換次數，[!DNL Target]可能會顯示比保證更早的獲勝者。 如需詳細資訊，請參閱[樣本大小電腦](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)。

## 瞭解[!UICONTROL Auto-Allocate]活動中的提升度和可信度報告 {#lift-confidence}

在[!UICONTROL Auto-Allocate]活動中，第一個體驗（預設為體驗A）一律定義為[!UICONTROL Reports]索引標籤上的「控制」體驗。 在用來判斷體驗效能的模型中，此體驗不會被視為真正的統計控制，但會被視為報表中某些圖表的參考或基準。

「提升度」數值和每個體驗的95%界限一律會參考定義的「控制」體驗進行計算。 定義的「控制」體驗不能有相對於本身的提升度，因此會報告此體驗的空白「 — 」值。 不同於A/B測試，在[!UICONTROL Auto-Allocate]測試中，如果體驗的執行效能比定義的控制項差，則不會報告負的提升值，而是顯示「 — 」。

顯示的[!UICONTROL Confidence Interval]長條代表體驗轉換率平均估計值的95%信賴區間。 這些長條也會針對定義的「控制」體驗進行色彩編碼。 「控制」體驗的列一律為灰色。 「控制」體驗信賴區間下方的信賴區間部分會以紅色顯示，而「控制」體驗上方的信賴區間部分則會以綠色顯示。

當領導體驗的95% [!UICONTROL Confidence Interval]與任何其他體驗不重疊時，就會找到獲勝者。 成功體驗會在體驗名稱左側和「成功者」橫幅中指定綠色星形徽章。 看不到任何星星時，橫幅會顯示「尚未有贏家」，而且尚未找到贏家。

目前領先或勝出的體驗旁邊也會報告「信賴度」數字。 此數字只會在領先體驗的[!UICONTROL Confidence]達到至少60%時報告。 如果[!UICONTROL Auto-Allocate]活動中存在兩個體驗，此數字代表該體驗執行優於其他體驗的信賴等級。 如果[!UICONTROL Auto-Allocate]活動中存在兩個以上的體驗，此數字代表體驗的執行勝過定義的「控制」體驗的信賴等級。 如果「控制」體驗獲勝，則不會報告「信賴度」數字。

## 常見問題集 {#section_C8E068512A93458D8C006760B1C0B6A2}

請考量下列常見問題的回答：

### 此活動已進行幾天。 為何所有信賴值仍顯示0%？

下列任一原因說明為什麼0%會在報表所有活動的[!UICONTROL Confidence]欄中顯示：

* 手動A/B測試和[!UICONTROL Auto-Allocate]使用不同的統計資料來顯示[!UICONTROL Confidence]值。

  手動A/B測試使用以[Welch的t檢定](https://en.wikipedia.org/wiki/Welch%27s_t-test)為基礎的p值。 由於實際上並沒有這種差異，P 值是尋找在體驗與控制之間觀察到 (或更極端) 之差異的機率。這些 P 值只能用來判斷觀察到的資料是否與指定體驗一致，並且有相同的控制。這些值只能用來判斷體驗是否與另一個體驗 (非控制) 不同。

  [!UICONTROL Auto-Allocate]會顯示指定體驗在活動中的所有體驗中成為真正成功者的機率。 只有成功體驗（最有可能是成功者）具有非零信賴值。 所有其他最有可能是損失者，並顯示0%。

* [!UICONTROL Auto-Allocate]只有在成功體驗收集到60%的信賴度後，才會開始顯示信賴度。 這些信賴等級通常大約會顯示在一般A/B測試完成所需時間的一半（雖然此時間範圍並無保證）。 若要判斷一般A/B測試會執行多久，請使用[!DNL Adobe Target] [樣本大小電腦](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)：在「基準轉換率」中插入控制項的轉換率，「提升度」為&quot;5%&quot;，「信賴度」為95%。 通常在每一個體驗至少累積每一體驗必要樣本的 50% 之後，才會開始出現信賴度。這讓您知道何時開始出現可信度。

* 如果報表完全顯示 0%，可能表示太早進入活動。

### 「沒有贏家」、「贏家」和「星星」徽章適用於使用[!UICONTROL Auto-Allocate] (A4T)的[!UICONTROL Analytics as the reporting source]活動嗎？

「尚未有贏家」和「贏家」徽章目前在[!UICONTROL A4T]的[!DNL Analysis Workspace]面板中無法使用。 如果在[!DNL Target]中檢視相同的報表，則也無法使用這些徽章。 使用A4T的[!DNL Target]活動在[!UICONTROL Auto-Allocate]報告中顯示的獲勝者「星星」徽章應予以忽略。

如需此專案以及其他限制和附註的詳細資訊，請參閱[和](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa)活動&#x200B;*在[!UICONTROL Auto-Allocate]A4T支援中的[!UICONTROL Auto-Target]自動分配*。

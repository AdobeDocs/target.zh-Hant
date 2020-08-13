---
keywords: automated traffic allocation;targeting;winner;statistical guarantee;confidence;determine winner;lift;confidence;default;default experience
description: 檢視 Target UI 中的指示器，來判斷自動分配 A/B 活動中的獲勝者。
title: 決定獲勝者
feature: auto-allocate
topic: Standard
uuid: 0bcc11b2-44bd-450c-a504-a8ff7a4d72e6
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 49%

---


# 解譯自動分配報表 {#determine-a-winner}

在Target UI中檢查重要指標，包括提升度和信賴度，以解譯自動分配A/B活動的結果。

許多行銷人員犯了一種錯誤，在結果指出明確的贏家之前便提早宣告獲勝體驗。我們現在已經可讓您輕鬆決定獲勝者。

>[!NOTE]
>
>如需宣告成功者的一般資訊，請參 [閱十種常見的A/B測試陷阱以及如何避免](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md)。

## 識別成功體驗 {#section_24007470CF5B4D30A06610CE8DD23CE3}

使用[!UICONTROL 自動分配]功能時，在活動達到最低轉換次數且有足夠信賴度之前，[!DNL Target] 會在活動頁面頂端顯示徽章，指出「尚未有贏家」。

![無贏家徽章](/help/c-activities/automated-traffic-allocation/assets/no-winner.png)

宣告明確的獲勝者時，[!DNL Target] 會顯示「獲勝者: 體驗 X」。

![](assets/winner.png)

>[!NOTE]
>
>「自動分配」活動旨在所有選項之中找出最佳體驗，而不只與控制項進行成對比較而已。

## Statistical guarantees of Auto-Allocate {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

A/B 活動結束時，「自動分配」會保證決定的獲勝者有 5% 的有效誤判率。這表示在活動的所有體驗之中，只有 5% 的時間，決定的獲勝者實際上不是最佳體驗。如果是 A/A 測試 (使用相同的體驗)，我們發現測試有小於 5% 的時間。A/A 測試 (使用相同的體驗) 的預期行為是無限期執行，所以獲勝者徽章永遠不會出現。

對於「自動分配」，我們不採用 p 值信賴度。

「自動分配」的「信賴度」欄 (如下圖) 顯示體驗是獲勝者的機率，誤差率在 1% 之內 (亦即，在最佳和次佳轉換率之間，演算法採用最低可偵測效應 1%)。請注意，演算法採用 [Bernstein 不等式](https://en.wikipedia.org/wiki/Bernstein_inequalities_(probability_theory))來計算此機率。

一般 A/B 測試會根據 p 值來計算信賴度。「自動分配」不使用 p 值。P 值會「寬鬆」計算所給定體驗與控制項不同的機率。這些 p 值只能用來判斷體驗是否可能與控制不同。這些值只能用來判斷體驗是否與另一個體驗 (非控制) 不同。

>[!IMPORTANT]
>
>Target會在預先定義的最小轉換數後顯示成功者；不過，挑選成功者的最終決定應一律以Adobe Target範例大小計算器 [的結果為準](https://docs.adobe.com/content/target-microsite/testcalculator.html)。 Target不會考慮網站的基本轉換率，以及輸入計算器以決定活動持續時間的其他重要方面。 因此，Target可能會根據最少轉換次數，提前顯示成功者。 如需詳細資訊，請參 [閱範例大小計算器](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)。

## 瞭解自動分配活動中的提升度和可信度報告 {#lift-confidence}

在「自動分配」活動中，第一個體驗（依預設命名為「體驗A」）一律會定義為「報表」標籤上的「控制」體驗。 在用來判斷體驗效能的模型中，此體驗並未被視為真正的統計控制項，但會視為報表中某些圖形的參考或基準。

每個體驗的「提升度」數值和95%界限一律會參照已定義的「控制」體驗來計算。 定義的「控制」體驗不能具有相對於自身的提升度，因此會針對此體驗報告空白的「—」值。 與A/B測試不同，在「自動分配」測試中，如果體驗的表現比定義的控制差，則不會報告負提升度值；而顯示&quot;—&quot;。

顯示的「信賴區間」列代表體驗轉換率的平均估計值周圍95%的信賴區間。 這些也會針對已定義的「控制」體驗進行色彩編碼。 「控制」體驗的列總是呈彩色灰色。 「控制」體驗信賴區間下方的信賴區間部分會以紅色標示，而「控制」體驗上方的信賴區間部分會以綠色標示。

當領先體驗的95%信賴區間與任何其他體驗不重疊時，就會發現贏家。 成功體驗會在體驗名稱左側和「成功者」橫幅中指定綠色星形標章。 當未顯示星號時，橫幅會顯示「尚未找到贏家」，而且尚未找到贏家。

目前領先或成功體驗旁也會報告「信賴」數字。 此數字只會在領先體驗的「信賴度」達到至少60%時才會報告。 如果「自動分配」實驗中正好有兩個體驗，此數字代表體驗的表現優於其他體驗的信賴等級。 如果「自動分配」實驗中有兩個以上的體驗，此數字代表體驗執行成效優於已定義「控制」體驗的信賴等級。 如果「控制」體驗成功，則不會報告「信賴」數字。

## 常見問題 {#section_C8E068512A93458D8C006760B1C0B6A2}

**進入活動已過了幾天。為何所有信賴度仍顯示 0%?**

下列任何原因說明所有活動在報表的[!UICONTROL 「信賴度」]欄中為何顯示 0%:

* 手動 A/B 測試和「自動分配」使用不同的統計量來顯示「信賴度」值。

   手動 A/B 測試採用基於 [Student 的 t 檢定](https://en.wikipedia.org/wiki/Student%27s_t-test)的 p 值。由於實際上並沒有這種差異，P 值是尋找在體驗與控制之間觀察到 (或更極端) 之差異的機率。這些 P 值只能用來判斷觀察到的資料是否與指定體驗一致，並且有相同的控制。這些值只能用來判斷體驗是否與另一個體驗 (非控制) 不同。

   自動分配顯示在活動的所有體驗之中，所給定體驗是真正獲勝者的機率。這表示只有勝出體驗 (很可能就是獲勝者) 才有非零的信賴值。其他很可能全部都是失敗者，將會顯示 0%。

* 只有在勝出體驗收集到 60% 信賴度時，「自動分配」才會開始顯示信賴度。這些信賴等級通常會出現在正常A/B測試完成的約一半時間內（雖然這並不保證）。 To determine how long a normal A/B test would run, please use a [sample size calculator](https://docs.adobe.com/content/target-microsite/testcalculator.html): plug control&#39;s conversion-rate in &quot;Baseline conversion rate,&quot; &quot;5%&quot; for &quot;Lift,&quot; and 95% for &quot;Confidence.&quot; 通常在每一個體驗至少累積每一體驗必要樣本的 50% 之後，才會開始出現信賴度。這樣可讓您大概知道何時會開始出現信賴度。
* 如果報表完全顯示 0%，可能表示太早進入活動。


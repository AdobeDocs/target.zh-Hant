---
keywords: 自動流量分配；鎖定目標；增加計數以及讓使用者留在活動中；流量分配；自動分配
description: 瞭解如何在 [!DNL Adobe Target] 中使用[!UICONTROL Auto-Allocate]活動，該活動可在兩個或多個體驗中識別獲勝者，並自動重新分配更多流量給獲勝者。
title: 什麼是[!UICONTROL Auto-Allocate]活動？
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
source-git-commit: 1b1b2271738d12f8da4e695900b70e280f50d8cf
workflow-type: tm+mt
source-wordcount: '3502'
ht-degree: 35%

---

# [!UICONTROL Auto-Allocate]總覽

[!DNL Adobe Target]中的[!UICONTROL Auto-Allocate]活動會從兩個或多個體驗中識別獲勝者，並自動重新分配更多流量給獲勝者以增加轉換，同時測試會繼續執行和學習。

使用三步驟引導式工作流程[建立A/B活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)時，請在&#x200B;**[!UICONTROL Targeting]**&#x200B;頁面上選擇&#x200B;**[!UICONTROL Auto-Allocate to best experience]**&#x200B;選項（步驟2）。

## 挑戰 {#section_85D5A03637204BACA75E19646162ACFF}

標準 A/B 測試有其固有成本。您必須耗費流量來測量每個體驗的效能，並透過分析來定奪勝出體驗。即使在您認定某些體驗勝過其他體驗之後，流量分布仍然固定。另外，很難決定樣本大小，必須等到活動執行完整個過程，您才能對獲勝者採取動作。此外，已識別的獲勝者仍有可能不是真正的獲勝者。

## 方案： [!UICONTROL Auto-Allocate] {#section_98388996F0584E15BF3A99C57EEB7629}

[!UICONTROL Auto-Allocate]活動可減少決定成功體驗的成本與額外負荷。 [!UICONTROL Auto-Allocate]會監視所有體驗的目標量度績效，並成比例地將更多新加入者傳送至表現優異的體驗。 有足夠的流量保留來探索其他體驗。即使活動仍在執行，您也可以看到測試帶給結果的好處: 最佳化與學習同步進行。

[!UICONTROL Auto-Allocate]會逐步將訪客推向成功體驗，而不是要求您等到活動結束再決定成功者。 您會更快從提升中受益，因為原本安排到較差體驗的活動加入者會看到潛在的勝出體驗。

[!DNL Target]中的一般A/B測試只會顯示挑戰者與控制項的成對比較。 例如，如果活動有體驗：A、B、C和D，其中A是控制項，則正常的[!DNL Target] A/B測試會比較A與B、A與C，以及A與D。

在此類測試中，大部分產品（包括[!DNL Target]）都使用[Welch的t檢定](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}來產生p值信賴度。 接著，此信賴值用來判斷挑戰體驗與控制體驗是否明顯不同。不過，[!DNL Target]不會自動執行尋找「最佳」體驗所需的隱含比較（B對C、B對D、C對D）。 因此，市場行銷人員必須手動分析結果，才能決定「最佳」體驗。

[!UICONTROL Auto-Allocate]會跨體驗執行所有隱含的比較，並產生「真」贏家。 測試中沒有「控制」體驗的概念。

[!UICONTROL Auto-Allocate]會聰明地將新訪客配置給體驗，直到最佳體驗的信賴區間與任何其他體驗的信賴區間不重疊。 這個程式通常會產生誤判，但[!UICONTROL Auto-Allocate]會根據補償重複評估的[Bernstein不等式](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29){target=_blank}來使用信賴區間。 此時，就會有真正的贏家。 當[!UICONTROL Auto-Allocate]停止時，假設對到達頁面的訪客沒有顯著的時間相依性，則至少有95%的機會會[!UICONTROL Auto-Allocate]傳回其真實回應不比成功體驗的真實回應差1% （相對）的體驗。

## 何時使用[!UICONTROL Auto-Allocate]而非[!UICONTROL A/B Test]或[!UICONTROL Automated Personalization]活動 {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* 當您想要從一開始就最佳化您的活動並儘快識別成功體驗時，請使用&#x200B;**[!UICONTROL Auto-Allocate]**。 透過更頻繁地提供高效能體驗，整體活動效能得以提升。
* 如果您想要在最佳化網站之前先表徵所有體驗的效能，請使用標準&#x200B;**[A/B測試](/help/main/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)**。 A/B測試可協助您對所有體驗進行排名，而[!UICONTROL Auto-Allocate]會找出績效最佳的體驗，但無法保證區分績效較低的體驗。
* 當您想要最佳化最複雜演演算法時使用[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)，例如根據個人設定檔屬性建立預測的機器學習模型。 [!UICONTROL Auto-Allocate]會檢視體驗的整體行為（如同標準A/B測試），不會區別訪客。

## [!UICONTROL Auto-Allocate]的主要優點 {#section_0913BF06F73C4794862561388BBDDFF0}

* 保留 A/B 測試的的嚴謹度
* 比手動 A/B 測試更快找出統計意義上的顯著成功者
* 比手動 A/B 測試提供更高的平均促銷活動提升度

## 術語 {#section_670F8785BA894745B43B6D4BFF953188}

討論[!UICONTROL Auto-Allocate]時，下列字詞相當實用：

**多臂吃角子老虎機：**&#x200B;最佳化的[多臂吃角子老虎機](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank}方法可平衡探索學習和該學習的利用。

## 演演算法運作方式 {#section_ADB69A1C7352462D98849F2918D4FF7B}

[!UICONTROL Auto-Allocate]之後的整體邏輯同時包含測量到的效能（例如轉換率）和累積資料的信賴區間。 不像標準A/B測試，流量在體驗之間平均分割，[!UICONTROL Auto-Allocate]會變更跨體驗的流量分配。

* 80% 的訪客是透過下述的智慧型邏輯來分配。
* 20%的訪客會隨機指派到所有體驗，以因應不斷變化的訪客行為。

在利用表現良好的體驗時，多臂吃角子老虎機法會保留一些體驗以供探索。除了將更多的新訪客安排到表現較佳的體驗，仍然能夠隨情況變化而做出反應。這些模型至少每一小時更新一次，以確保模型是對最新資料做出反應。

隨著越多訪客進入活動，有些體驗會開始變得更成功，而更多流量會分配給成功體驗。20% 的流量會持續地隨機供應，以探索所有體驗。如果其中一個表現較差的體驗開始有較好的表現，則會分配更多流量給該體驗。或者，如果表現較佳的活動變得較不成功，則分配給該體驗的流量會變少。例如，若某事件促使訪客在您的媒體網站上尋找不同資訊，或您的零售網站上的週末銷售提供不同的結果。

下圖代表演演算法可能在測試期間對四個體驗（按一下以展開圖）的執行方式：

![自動分配影像](assets/auto-allocate.png){width="600" zoomable="yes"}

圖中顯示分配給每個體驗的流量如何經歷活動期限的幾個回合而增加，直到確定完勝贏家為止。

| 四捨五入 | 說明 |
|--- |--- |
| ![熱身回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png){width="200" zoomable="yes"} | **熱身回合 (0)**: 在熱身回合期間，每個體驗會獲得相等的流量分配，直到活動中的每個體驗至少有 1,000 位訪客和 50 次轉換為止。<ul><li>體驗 A=25%</li><li>體驗 B=25%</li><li>體驗 C=25%</li><li>體驗 D=25%</li></ul>每個體驗獲得1,000位訪客和50次轉換後，[!DNL Target]就會開始自動流量分配。 所有分配皆透過回合輪翻進行，每個回合會挑出兩個體驗。<br>只有兩個體驗會前進到下一個回合： D和C。<br>前進就表示這兩個體驗平均分配80%的流量。 其他兩個體驗會持續參與，但只有在新訪客進入活動時，才會作為20%隨機流量分配的一部分提供。<br>所有分配每小時更新一次 (如沿著上面 x 軸的回合所示)。每個回合之後會比較累積資料。 |
| ![第 1 回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png){width="200" zoomable="yes"} | **第 1 回合**: 在此回合中，80% 的流量分配給體驗 C 和 D (各 40%)。20% 的流量隨機分配給 A、B、C、D (各 5%)。在此回合中，體驗 A 表現良好。<ul><li>演演算法會挑選體驗D來進行下一個循環，因為它有最高的轉換率（如每個活動的垂直比例尺所指示）。</li><li>演算法還會挑選體驗 A 來前進，因為相較於剩餘的體驗，它的 Bernstein 95% 信賴區間上界最高。</li></ul>體驗 D 和 A 會前進。 |
| ![第 2 回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png){width="200" zoomable="yes"} | **第 2 回合**: 在這個回合中，80%的流量會分配給體驗 A 和 D (各 40%)。20% 的流量會隨機分配，因此，這表示 A、B、C 和 D 每個都會獲得 5% 的流量。在此回合中，體驗 B 表現良好。<ul><li>演演算法會挑選體驗D來進行下一個循環，因為它有最高的轉換率（如每個活動的垂直比例尺所指示）。</li><li>演算法還會挑選體驗 B 來前進，因為相較剩餘的體驗，它的 Bernstein 95% 信賴區間上界最高。</li></ul>體驗 D 和 B 會前進。 |
| ![第 3 回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png){width="200" zoomable="yes"} | **第 3 回合**: 在這個回合中，80%的流量會分配給體驗 B 和 D (各 40%)。20% 的流量會隨機分配，因此，這表示 A、B、C 和 D 每個都會獲得 5% 的流量。在此回合中，體驗 D 持續表現良好，體驗 C 也表現良好。<ul><li>演演算法會挑選體驗D來進行下一個循環，因為它有最高的轉換率（如每個活動的垂直比例尺所指示）。</li><li>演算法還會挑選體驗 C 來前進，因為相較於剩餘的體驗，它的 Bernstein 95% 信賴區間上界最高。</li></ul>體驗 D 和 C 會前進。 |
| ![第 4 回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png){width="200" zoomable="yes"} | **第 4 回合**: 在此回合中，80% 的流量分配給體驗 C 和 D (各 40%)。20% 的流量會隨機分配，因此，這表示 A、B、C 和 D 每個都會獲得 5% 的流量。在此回合中，體驗 C 表現良好。<ul><li>演演算法會挑選體驗C來進行下一個循環，因為它有最高的轉換率（如每個活動的垂直刻度所示）。</li><li>演算法還會挑選體驗 D 來前進，因為相較於剩餘的體驗，它的 Bernstein 95% 信賴區間上界最高。</li></ul>體驗 C 和 D 會前進。 |
| ![第 n 回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png){width="200" zoomable="yes"} | **回合&#x200B;*n***：隨著活動進行，表現優異的體驗會開始浮現，過程會持續到出現勝出體驗為止。 當轉換率最高的體驗和任何其他體驗的信賴區間不重疊時，即會標示為獲勝者。 [徽章會顯示在成功活動的頁面](/help/main/c-activities/automated-traffic-allocation/determine-winner.md)和[!UICONTROL Activity]清單中。<ul><li>演算法會挑選體驗 C 成為確定贏家。</li></ul>此時，演算法會將 80% 的流量供應給體驗 C，而 20% 的流量持續地隨機供應給所有體驗 (A、B、C、D)。C 總共獲得 85% 的流量。在很罕見的情況下，萬一獲勝者的信賴區間又開始重疊，演算法會回復到上面回合 4 的行為。<P>**重要**：如果您在過程中太早手動選擇獲勝者，很容易會選出錯誤的體驗。 因此，最好等待演算法決定勝出體驗。 |

>[!NOTE]
>
>如果活動只有兩個體驗，則兩個體驗會獲得相等的流量，直到[!DNL Target]找到具有75%信賴度的成功體驗為止。 到那時，三分之二的流量會分配給成功者，三分之一分配給失敗者。 之後，當體驗達到95%信賴度時，90%的流量會分配給獲勝者，而10%會分配給失敗者。 [!DNL Target]一律會傳送一些流量給「遺失」體驗，以避免最後的誤判（也就是說，維持一些探索）。

在啟動[!UICONTROL Auto-Allocate]活動後，不允許從Target UI執行下列操作：

* 將「流量配置」模式切換為「手動」
* 變更目標量度類型
* 變更「[!UICONTROL Advanced Settings]」面板中的選項

## 瞭解自動分配如何運作

如需詳細資訊，請參閱[自動分配比手動測試提供更快的測試結果和更高的收入](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md)。

## 注意事項 {#section_5C83F89F85C14FD181930AA420435E1D}

使用[!UICONTROL Auto-Allocate]時請考量下列資訊：

### [!UICONTROL Auto-Allocate]功能只適用於一個進階量度設定： [!UICONTROL Increment Count and Keep User in Activity]

不支援下列進階量度設定： [!UICONTROL Increment Count]、[!UICONTROL Release User]、[!UICONTROL Allow Reentry and Increment Count]和[!UICONTROL Release User and Bar from Reentry]。

### 經常再度訪問的訪客會抬高體驗轉換率。

如果一位見到體驗 A 的訪客經常再度訪問且多次轉換，則體驗 A 的轉換率 (CR) 會不自然地提高。將此結果與體驗B進行比較，後者訪客轉換但不常回訪。 因此，體驗A的CR看起來比體驗B的CR更好，因此新訪客更有可能分配至A而不是B。如果您選擇對每個加入者計算一次，A的CR和B的CR可能會相同。

如果再度訪問的訪客隨機分佈，則對轉換率的影響很可能互相抵銷。為了減輕這種效應，請考慮將目標量度的計數方法變更為每一個加入者只算一次。

### 區分高效能者，而非低效者。

[!UICONTROL Auto-Allocate]擅長區分表現優異的體驗（以及尋找獲勝者）。 有時，表現不佳的體驗之間沒有足夠的差異性。

如果您想要在所有體驗之間產生統計上顯著的差異，可以考慮使用手動流量分配模式。

### 時間相關（或隨情境變化）的轉換率可能會扭曲分配量。

在標準A/B測試中因會影響所有體驗而可忽略的某些因素，在[!UICONTROL Auto-Allocate]活動中無法忽略。 演演算法易受觀察轉換率的影響。

可能以不同程度影響體驗效能的因素範例如下:

* 具有不同內容（時間、位置、性別等）相關性的體驗。

  例如：

   * 「感謝上帝，現在是星期五」導致星期五的轉換率較高。
   * 「週一快速啟動」週一的轉換率較高。
   * 「Gear up for an East-coast winter」在東海岸或受冬季影響的位置提供較高的轉換率。

  使用具有不同內容相關性的體驗時，[!UICONTROL Auto-Allocate]測試的結果會比使用A/B測試時扭曲得多，因為A/B測試會花較長的時間分析結果。

* 體驗的延遲轉換時間不同，可能是由於消息的迫切性。

  例如，「七折促銷只到今天」暗示訪客今天應該成交，但「首購五折」就不會讓人感到相同的急迫性。

## 常見問題集 {#section_0E72C1D72DE74F589F965D4B1763E5C3}

在使用[!UICONTROL Auto-Allocate]活動時查詢下列的常見問答集：

### [!UICONTROL Analytics for Target] (A4T)是否支援[!UICONTROL Auto-Allocate]活動？

是.如需詳細資訊，請參閱自動分配和自動鎖定目標活動的[A4T支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

### 再度訪問的訪客會自動重新分配到表現優異的體驗嗎？

無.只會自動重新分配新的訪客。再度訪問的訪客會繼續看見其原始體驗，以保護A/B測試的有效性。

### 演演算法如何處理誤判？

如果您等待到獲勝者徽章出現，演算法可保證 95% 可信度或 5% 誤判率。

### [!UICONTROL Auto-Allocate]何時開始配置流量？

當活動中的所有體驗皆至少有 1,000 位訪客和 50 次轉換之後，演算法就開始運作。

### 演演算法的利用積極性如何？

使用[!UICONTROL Auto-Allocate]提供80%的流量，隨機提供20%的流量。 識別出獲勝者時，80%的流量會流向該獲勝者，而所有體驗仍會隨著20%的流量繼續獲得一些流量，包括獲勝者體驗。

### 到底會不會顯示失敗體驗？

是.多臂吃角子老虎機會確保至少保留 20% 的流量，以供探索所有體驗不斷變化的模式或轉換率。

### 轉換延遲很久的活動會如何？

只要所有要最佳化的體驗皆面臨類似的延遲，行為就同於轉換週期較快的活動。 不過，在流量分配程式開始之前，需要更長的時間才能達到50次轉換臨界值。

### [!UICONTROL Auto-Allocate]與[!UICONTROL Automated Personalization]有何不同？

[!UICONTROL Automated Personalization]會使用每位訪客的設定檔屬性來決定最佳體驗。 這樣做不僅會最佳化，還會將該使用者的活動個人化。

另一方面，[!UICONTROL Auto-Allocate]是A/B測試，可產生彙總獲勝者（最熱門的體驗，但不一定是每位訪客最有效的體驗）。

### 再度訪問的訪客會在我的成功量度上增加轉換率嗎？

目前，邏輯偏好快速轉換或瀏覽較頻繁的訪客，因為這類訪客會暫時誇大其所屬體驗的整體轉換率。 演算法會經常自行調整，因此，轉換率提高每次皆會放大。如果網站獲得大量回訪訪客，其轉換可能會導致其所屬體驗的整體轉換率膨脹。 再度訪問的訪客極可能是隨機分布，在此情況下，集體效應 (提升度增加) 會互相抵銷。為了減輕這種效應，請考慮將成功量度的計數方法變更為每一個加入者只算一次。

### 使用[!UICONTROL Auto-Allocate]時，我可以利用樣本大小電腦來預估活動識別獲勝者所需的時間嗎？

您可以使用現有的[!DNL Adobe Target] [樣本大小電腦](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)來取得測試執行時間的預估值。 （和傳統A/B測試一樣，如果您測試兩個以上的選件或多個轉換量度/假設，請套用Bonferroni校正。） 此計算器專為傳統的固定地平線A/B測試所設計，僅提供預估值。 使用[!UICONTROL Auto-Allocate]活動的計算器是選用的，因為[!UICONTROL Auto-Allocate]會為您宣告獲勝者。 您不需要挑選固定的時間點來檢視測試結果。 提供的值在統計上一律有效。

內部[!DNL Adobe]實驗發現下列專案：

* 當僅測試兩個體驗時，如果體驗之間的效能差異很大，[!UICONTROL Auto-Allocate]會比固定水平線測試（即樣本大小電腦建議的時間範圍）更快地找到獲勝者。 不過，當體驗之間的效能差異很小時，[!UICONTROL Auto-Allocate]可能需要額外的時間來識別獲勝者。 在這些情況下，固定總時程測試通常會在沒有統計上顯著結果的情況下結束。
* 測試兩個以上的體驗時，當單一體驗的表現遠遠勝過所有其他體驗時，[!UICONTROL Auto-Allocate]會比固定總時程測試（也就是樣本大小電腦建議的時間範圍）更快地找到獲勝者。 當兩個或多個體驗都和其他體驗「獲勝」，但彼此非常相符時，[!UICONTROL Auto-Allocate]可能需要額外的時間才能判斷哪個體驗更優秀。 在這些情況下，固定範圍測試通常會以總結「成功」體驗優於表現較差的體驗結束，但未識別出哪個體驗更佳。

### 是否應從[!UICONTROL Auto-Allocate]活動中移除表現缺佳的體驗，以加速決定獲勝者的程式？

沒有必要移除表現缺佳的體驗。 [!UICONTROL Auto-Allocate]會自動增加提供表現優異的體驗的頻率，並減少提供表現不佳的體驗的頻率。 在活動中保留表現缺佳的體驗不會大幅影響決定獲勝者的速度。

20% 的訪客是隨機分配到所有體驗。系統會將提供給表現缺佳的體驗的流量減至最少（20%除以體驗數量）。

### 我可以透過[!UICONTROL Auto-Allocate]活動半途變更目標量度嗎？ {#change-metric}

[!DNL Adobe]不建議您在活動中途變更目標量度。 雖然在活動期間有可能使用 [!DNL Target] UI 變更目標量度，您應該總是開始一個新的活動。[!DNL Adobe]無法保證您在活動執行後變更目標量度會發生什麼情況。

此建議適用於使用[!DNL Target]或[!DNL Analytics] (A4T)作為報告來源的[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]活動。

### 我可以在[!UICONTROL Auto-Allocate]活動中途變更報表來源嗎？ {#change-reporting}

[!DNL Adobe]不建議您在活動中途變更報表來源。 雖然在使用[!DNL Target] UI的活動中可以變更報表來源（從[!DNL Target]變更為A4T，或以相反的方式），您應該一律開始新的活動。 [!DNL Adobe]無法保證您會在活動執行後變更活動中的報告來源時發生什麼情況。

此建議適用於使用[!DNL Target]或[!DNL Analytics] (A4T)作為報告來源的[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]活動。

### 我在執行[!UICONTROL Auto-Allocate]活動時可以使用[!UICONTROL Reset Report Data]選項嗎？

不建議對[!UICONTROL Auto-Allocate]活動使用[!UICONTROL Reset Report Data]選項。 雖然此選項會移除可見的報告資料，但不會移除[!UICONTROL Auto-Allocate]模型中的所有訓練記錄。 不要對[!UICONTROL Auto-Allocate]個活動使用[!UICONTROL Reset Report Data]選項，請建立新活動並停用原始活動。 （此指引也適用於[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]活動。）

### [!UICONTROL Auto-Allocate]如何建立環境相關模型？

[!UICONTROL Auto-Allocate]僅根據預設環境中記錄的流量和轉換行為來建置模型。 依預設，[!UICONTROL Production]是預設環境，但可在[!DNL Target]中變更預設環境（[管理>環境](/help/main/administrating-target/environments.md)）。

如果點選發生在其他（非預設）環境中，流量會根據在預設環境中觀察到的轉換行為分配。 該點選的結果（轉換或非轉換）會記錄下來以用於報表目的，而不會在[!UICONTROL Auto-Allocate]模型中考慮。

選取其他環境時，報表會顯示該環境的流量和轉換。 報表的預設選定環境為已選取的帳戶範圍預設值。 預設環境無法根據每個活動進行設定。

### [!UICONTROL Auto-Allocate]活動能否在測試過程中調整回顧期間以考慮隨時間變更趨勢？

例如，活動是否可考慮12月份來決定如何分配流量，而非檢視9月的訪客資料（測試開始的時間）？

否，[!UICONTROL Auto-Allocate]會考量整個活動的效能。

### 如果成功體驗和訪客在取得活動資格時看到的不同，[!UICONTROL Auto-Allocate]是否會向回訪訪客顯示成功體驗？

[!UICONTROL Auto-Allocate]使用粘性決策的原因與[!UICONTROL A/B Test]活動具有粘性相同。 流量分配僅適用於新訪客。

## 培訓影片 {#section_893E5B36DC4A415C9B1D287F51FCCB83}

以下影片含有本文章探討之概念的詳細資訊。

### 活動工作流程 — 目標定位(2:14) ![教學課程徽章](/help/main/assets/tutorial.png)

此視訊包含有關如何設定流量分配的資訊。

* 指派對象至您的活動
* 向上或向下調節流量
* 選取您的流量分配方法
* 在不同體驗之間分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17385)

### 建立A/B測試(8:36) ![教學課程徽章](/help/main/assets/tutorial.png)

此視訊示範如何使用 Target 三步驟引導式工作流程來建立 A//B 測試。上午 04:45 處開始討論 [!UICONTROL Auto-Allocate]。

* 在[!DNL Adobe Target]中建立A/B活動
* 使用手動分割或自動流量分配來分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)

---
keywords: 自動流量分配；鎖定目標；增加計數以及讓使用者留在活動中；流量分配；自動分配
description: 瞭解如何在[!DNL Adobe Target]中使用[!UICONTROL 自動分配]活動，該活動可在兩個或多個體驗中識別獲勝者，並自動重新分配更多流量給獲勝者。
title: 什麼是[!UICONTROL 自動分配]活動？
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
TQID: 'https://experienceleague.adobe.com/V5ZS2vBGVilH0-4bacB4x7iQi8M6qroLe3R9LNMoVEc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
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
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: de439134b0ee5aa795ae255bba852b9b6f10da12
workflow-type: tm+mt
source-wordcount: '3662'
ht-degree: 15%
---
# 開始使用[!UICONTROL 自動分配] {#auto-allocate-overview}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動如何識別成功體驗並重新分配流量、何時使用、演演算法如何運作，以及在使用之前需要考量哪些事項。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動會從兩個或多個體驗中識別獲勝者，並自動重新分配更多流量給獲勝者以增加轉換，同時測試會繼續執行和學習。

您使用A/B活動的三步驟引導式工作流程來建立&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動：在&#x200B;**[!UICONTROL 鎖定目標]**&#x200B;頁面上選擇&#x200B;**[!UICONTROL 自動分配至最佳體驗]**&#x200B;選項（步驟2）。 如需相關步驟，請參閱[建立自動分配活動](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)。

## 為何使用[!UICONTROL 自動分配] {#why-auto-allocate}

標準 A/B 測試有其固有成本。 您必須花流量來測量每個體驗的效能，即使有些體驗勝過其他體驗，流量的分配仍會維持固定。 樣本大小難以判斷，活動必須先執行其整個課程，然後才能對獲勝者採取行動，而且仍然有可能已識別的獲勝者不是真正的獲勝者。

**[!UICONTROL 自動分配]**&#x200B;活動可降低此成本與額外負荷：

* 它會監視所有體驗的目標量度效能，並以比例將更多的新加入者傳送至表現優異的體驗。 有足夠的流量保留來探索其他體驗。
* 最佳化與學習同時進行，因此您可以在活動仍在執行時檢視結果中的優點。
* 訪客會逐漸邁向成功體驗，因此您不需要等到活動結束。 您可從更快的提升中獲益，因為原本會傳送到不太成功體驗的活動加入者會看到潛在的成功體驗。

主要優點：

* 保留A/B測試的嚴格性。
* 比手動A/B測試更快找到統計上顯著的獲勝者。
* 提供比手動A/B測試更高的平均促銷活動提升度。

### [!UICONTROL 自動分配]如何識別獲勝者 {#true-winner}

在[!DNL Target]中的一般A/B測試只會比較每個挑戰者與控制項。 例如，如果活動有體驗A、B、C和D，其中A是控制項，則測試會比較A與B、A與C，以及A與D。大部分的產品（包括[!DNL Target]）對這些比較使用[Welch的t檢定](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}，以產生以p值為基礎的信賴度。 不過，[!DNL Target]不會自動執行尋找「最佳」體驗所需的隱含比較（B對C、B對D、C對D），因此您必須手動分析結果。

**[!UICONTROL 自動分配]**&#x200B;會移除此手動步驟：

* 它執行所有體驗間的隱含比較，並產生「真」贏家。 測試中沒有「控制」體驗的概念。
* 它會分配新訪客給體驗，直到最佳體驗的信賴區間與任何其他體驗的信賴區間不重疊。
* 它使用以[Bernstein不等式](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29){target=_blank}為基礎的信賴區間，以補償通常會產生誤判的重複評估。
* 當它停止時，假設對到達頁面的訪客沒有顯著的時間相依性，它至少有95%的機會會傳回其真實回應不比成功體驗的真實回應差1% （相對）的體驗。

## 何時使用[!UICONTROL 自動分配] {#when-to-use}

根據您的目標，在&#x200B;**[!UICONTROL 自動分配]**、**[!UICONTROL A/B測試]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動之間選擇：

| 活動 | 使用時機 | 不同之處 |
|---|---|---|
| **[!UICONTROL 自動分配]** | 您想要從一開始就最佳化活動，並儘快找出成功的體驗。 | 透過更頻繁地提供高效能體驗，整體活動效能得以提升。 |
| [**[!UICONTROL A/B 測試]**](/help/main/c-activities/t-test-ab/test-ab.md#test-ab) | 您想要在最佳化網站之前先描述所有體驗的效能。 | A/B測試可協助您對所有體驗進行排名，而&#x200B;**[!UICONTROL 自動分配]**&#x200B;會找出表現最好的專案，但無法保證區分表現較差的專案。 |
| [**[!UICONTROL 自動個人化]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) | 您想要將最複雜的演演算法最佳化，例如根據個人設定檔屬性建立預測的機器學習模型。 | **[!UICONTROL 自動分配]**&#x200B;會檢視體驗的彙總行為（如同標準A/B測試），不會區別訪客。 |

## 演演算法運作方式 {#how-it-works}

**[!UICONTROL 自動分配]**&#x200B;的演演算法是[多臂吃角子老虎機](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank}最佳化方法，可平衡探索學習和該學習的利用。 它包含測量到的效能（例如轉換率）和累計資料的信賴區間。 與標準A/B測試不同，在標準A/B測試中，流量會在體驗之間平均分割，**[!UICONTROL 自動分配]**&#x200B;會變更跨體驗的流量分配：

* 系統會使用本節所述的邏輯來分配80%的訪客。
* 20%的訪客會隨機指派到所有體驗，以因應不斷變化的訪客行為。

多臂吃角子老虎機方法可讓部分流量自由探索，同時利用表現良好的體驗。 會將更多新訪客安排到表現更好的體驗中，同時保留對不斷變化的狀況做出反應的能力。 模型每小時至少更新一次，以確保對最新資料做出反應。

隨著更多訪客進入活動，有些體驗會變得更成功，並接收更多流量。 20% 的流量會持續地隨機供應，以探索所有體驗。 如果其中一個表現較差的體驗開始有較好的表現，則會分配更多流量給該體驗。 如果較佳表現體驗的成功率降低，則分配給它的流量會減少。 例如，當事件導致訪客在您的媒體網站上尋找不同資訊，或當您的零售網站上的週末銷售提供不同結果時，就可能發生這種情況。

下圖代表演演算法可能在測試期間對四個體驗（按一下以展開圖）的執行方式：

![自動分配影像](assets/auto-allocate.png){width="600" zoomable="yes"}

圖中顯示分配給每個體驗的流量如何經歷活動期限的幾個回合而增加，直到確定完勝贏家為止。

| 四捨五入 | 說明 |
|--- |--- |
| ![熱身回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png){width="200" zoomable="yes"} | **熱身回合(0)**：每個體驗會獲得相等的流量，直到活動中的每個體驗至少有1,000位訪客和50次轉換為止。<ul><li>體驗 A=25%</li><li>體驗 B=25%</li><li>體驗 C=25%</li><li>體驗 D=25%</li></ul>每個體驗達到1,000位訪客和50次轉換後，[!DNL Target]就會開始自動流量分配。 所有配置都會以輪次進行，而且每個輪次會挑選兩個體驗。 只有兩個體驗會前進到下一個回合: D 和 C。<ul><li>往後移動表示這兩個體驗平均分配80%的流量。</li><li>其他兩個體驗會持續參與，但只有在新訪客進入活動時，才會作為20%隨機流量分配的一部分提供。</li><li>所有分配每小時更新一次（如沿著上面x軸的回合所示）。 每個回合之後會比較累積資料。</li></ul> |
| ![第 1 回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png){width="200" zoomable="yes"} | **第1**&#x200B;回合： 80%的流量分配給體驗C和D （各40%）。 20% 的流量隨機分配給 A、B、C、D (各 5%)。 在此回合中，體驗 A 表現良好。<ul><li>演演算法會挑選體驗D來進行下一個循環，因為它有最高的轉換率（如每個活動的垂直比例尺所指示）。</li><li>演算法還會挑選體驗 A 來前進，因為相較於剩餘的體驗，它的 Bernstein 95% 信賴區間上界最高。</li></ul>體驗 D 和 A 會前進。 |
| ![第 2 回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png){width="200" zoomable="yes"} | **第2**&#x200B;回合： 80%的流量已分配給體驗A和D （各40%）。 20%的流量是隨機分配的，因此體驗A、B、C和D各會獲得5%的流量。 在此回合中，體驗 B 表現良好。<ul><li>演演算法會挑選體驗D來進行下一個循環，因為它有最高的轉換率（如每個活動的垂直比例尺所指示）。</li><li>演算法還會挑選體驗 B 來前進，因為相較剩餘的體驗，它的 Bernstein 95% 信賴區間上界最高。</li></ul>體驗 D 和 B 會前進。 |
| ![第 3 回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png){width="200" zoomable="yes"} | **第3**&#x200B;回合： 80%的流量已分配給體驗B和D （各40%）。 20%的流量是隨機分配的，因此體驗A、B、C和D各會獲得5%的流量。 在此回合中，體驗 D 持續表現良好，體驗 C 也表現良好。<ul><li>演演算法會挑選體驗D來進行下一個循環，因為它有最高的轉換率（如每個活動的垂直比例尺所指示）。</li><li>演算法還會挑選體驗 C 來前進，因為相較於剩餘的體驗，它的 Bernstein 95% 信賴區間上界最高。</li></ul>體驗 D 和 C 會前進。 |
| ![第 4 回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png){width="200" zoomable="yes"} | **第4**&#x200B;回合： 80%的流量分配給體驗C和D （各40%）。 20%的流量是隨機分配的，因此體驗A、B、C和D各會獲得5%的流量。 在此回合中，體驗 C 表現良好。<ul><li>演演算法會挑選體驗C來進行下一個循環，因為它有最高的轉換率（如每個活動的垂直刻度所示）。</li><li>演算法還會挑選體驗 D 來前進，因為相較於剩餘的體驗，它的 Bernstein 95% 信賴區間上界最高。</li></ul>體驗 C 和 D 會前進。 |
| ![第 n 回合](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png){width="200" zoomable="yes"} | **回合&#x200B;*n***：隨著活動進行，表現優異的體驗會開始浮現，過程會持續到出現勝出體驗為止。 當轉換率最高的體驗和任何其他體驗的信賴區間不重疊時，即會標示為獲勝者。 [徽章會顯示在成功活動的頁面](/help/main/c-activities/automated-traffic-allocation/determine-winner.md)和**[!UICONTROL &#x200B;活動&#x200B;]**清單中。<ul><li>演算法會挑選體驗 C 成為確定贏家。</li></ul>此時，演演算法會將80%的流量提供給體驗C，繼續將20%的流量隨機提供給所有體驗（A、B、C和D）。 C 總共獲得 85% 的流量。 萬一獲勝者的信賴區間再次開始重疊，演演算法會回復到第4回合。<br>**重要**：如果您在程式期間較早手動選擇獲勝者，很容易會選擇錯誤的體驗。 因此，最好等待演算法決定勝出體驗。 |

>[!NOTE]
>
>如果活動只有兩個體驗，則兩個體驗會獲得相等的流量，直到[!DNL Target]找到具有75%信賴度的成功體驗為止。 到那時，三分之二的流量會分配給成功者，三分之一分配給失敗者。 之後，當體驗達到95%信賴度時，90%的流量會分配給獲勝者，10%分配給失敗者。 [!DNL Target]一律會傳送一些流量給「遺失」體驗，以避免最後的誤判（亦即維持某些探索）。

在啟動&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動後，[!DNL Target] UI中不允許下列操作：

* 正在將&#x200B;**[!UICONTROL 流量分配]**&#x200B;模式切換為&#x200B;**[!UICONTROL 手動]**。
* 變更目標量度型別。
* 正在變更&#x200B;**[!UICONTROL 進階設定]**&#x200B;面板中的選項。

如需詳細資訊，請參閱[自動分配如何勝過手動測試](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md)。

## 注意事項 {#caveats}

使用&#x200B;**[!UICONTROL 自動分配]**&#x200B;時，請考慮下列資訊。

### 僅支援一個進階量度設定

**[!UICONTROL 自動分配]**&#x200B;功能只適用於一個進階量度設定： **[!UICONTROL 遞增計數以及讓使用者留在活動中]**。 不支援下列進階量度設定： **[!UICONTROL 增加計數]**、**[!UICONTROL 釋出使用者]**、**[!UICONTROL 允許重新進入和增加計數]**&#x200B;以及&#x200B;**[!UICONTROL 釋出使用者並禁止重新進入]**。

### 經常再度訪問的訪客會抬高轉換率 {#return-visitors}

如果看到體驗A的訪客頻繁回訪並轉換多次，則會人為增加體驗A的轉換率(CR)。 將此結果與體驗B進行比較，後者訪客轉換但不常回訪。 因此，體驗A的CR看起來比體驗B的CR更好，因此新訪客更有可能分配至A而不是B。如果您選擇對每個加入者計算一次，A的CR和B的CR可能會相同。

邏輯偏好快速轉換或經常造訪的訪客，因為這類訪客會暫時誇大其所屬體驗的整體轉換率。 演算法會經常自行調整，因此，轉換率提高每次皆會放大。

如果再度訪問的訪客隨機分佈，則對轉換率的影響很可能互相抵銷。 為了減輕這種效應，請考慮將目標量度的計數方法變更為每一個加入者只算一次。

### 區別在於績效高者，而非績效低者

**[!UICONTROL 自動分配]**&#x200B;擅長區分表現優異的體驗（以及尋找成功者）。 有時候，您對於表現缺佳的體驗沒有足夠的差異。

如果您想要在所有體驗之間產生統計上顯著的差異，請考慮使用手動流量分配模式。

### 時間相關的轉換率可能扭曲配置

標準A/B測試期間可以忽略的某些因素，因為它們平等地影響所有體驗，在&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動中無法忽略。 演算法易受觀察的轉換率所影響。 下列因素可能會對體驗效能造成不平均的影響：

* 具有不同內容（時間、位置、性別等）相關性的體驗。

  例如：

  * 「感謝上帝，今天是星期五」導致星期五的轉換率較高。
  * 「週一快速啟動」週一的轉換率較高。
  * 「Gear up for an East-coast winter」在東海岸或受冬季影響的位置提供較高的轉換率。

  使用具有不同內容相關性的體驗時，**[!UICONTROL 自動分配]**&#x200B;測試的結果會比使用A/B測試時偏斜，因為A/B測試會分析較長期間的結果。

* 體驗的延遲轉換時間不同，可能是由於消息的迫切性。

  例如，「30%銷售今天結束」代表訪客今天要轉換，但「首次購買優惠50%」不會產生相同的緊迫感。

## 常見問題集 {#faq}

使用&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動時，請查詢下列問題和答案。

+++ [!UICONTROL Analytics for Target] (A4T)支援[!UICONTROL 自動分配]活動嗎？

是. 如需詳細資訊，請參閱自動分配和自動鎖定目標活動的[A4T支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

+++

+++ 再度訪問的訪客會自動重新分配到表現優異的體驗嗎？

無. 只會自動重新分配新的訪客。 再度訪問的訪客會繼續看見其原始體驗，以保護A/B測試的有效性。

+++

+++ 演演算法如何處理誤判？

如果您等到獲勝者徽章出現，演演算法可保證95%可信度或5%誤判率。

+++

+++ [!UICONTROL 自動分配]何時開始分配流量？

當活動中的所有體驗皆至少有 1,000 位訪客和 50 次轉換之後，演算法就開始運作。

+++

+++ 演演算法的利用積極性如何？

使用&#x200B;**[!UICONTROL 自動分配]**&#x200B;提供80%的流量，隨機提供20%的流量。 識別出獲勝者時，80%的流量會流向該獲勝者，而所有體驗仍會隨著20%的流量繼續獲得一些流量，包括獲勝者體驗。

+++

+++ 到底會不會顯示失敗體驗？

是. 多臂吃角子老虎機會確保至少保留 20% 的流量，以供探索所有體驗不斷變化的模式或轉換率。

+++

+++ 轉換延遲很久的活動會如何？

只要所有要最佳化的體驗皆面臨類似的延遲，行為就會與轉換週期較快的活動相同。 不過，在流量分配程式開始之前，需要更長的時間才能達到50次轉換臨界值。

+++

+++ [!UICONTROL 自動分配]與[!UICONTROL Automated Personalization]有何不同？

**[!UICONTROL Automated Personalization]**&#x200B;會使用每位訪客的設定檔屬性來決定最佳體驗。 如此一來，不僅會最佳化訪客的活動，還會將其個人化。

另一方面，**[!UICONTROL 自動分配]**&#x200B;是A/B測試，可產生彙總獲勝者（最熱門的體驗，但不一定是每位訪客最有效的體驗）。

+++

+++ 再度訪問的訪客是否會誇大成功量度的轉換率？

是的，可以。 請參閱[經常回訪的訪客可能會誇大轉換率](#return-visitors)，以取得說明及減輕這種影響的方式。

+++

+++ 我可以搭配[!UICONTROL 自動分配]使用樣本大小電腦來預估活動識別獲勝者所需的時間嗎？

您可以使用現有的[!DNL Adobe Target] [樣本大小電腦](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)來取得測試執行時間的預估值。 和傳統A/B測試一樣，如果您測試兩個以上的選件或多個轉換量度或假設，請套用Bonferroni校正。 此計算器專為傳統的固定地平線A/B測試所設計，僅提供預估值。 使用&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動的計算器是選用的，因為&#x200B;**[!UICONTROL 自動分配]**&#x200B;會為您宣告獲勝者。 您不需要挑選固定的時間點來檢視測試結果。 提供的值在統計上一律有效。

內部[!DNL Adobe]實驗發現下列專案：

* 當僅測試兩個體驗時，當體驗之間的效能差異很大時，**[!UICONTROL 自動分配]**&#x200B;會比固定水平線測試（即樣本大小計算器建議的時間範圍）更快地找到獲勝者。 不過，當體驗之間的效能差異很小時，**[!UICONTROL 自動分配]**&#x200B;可能需要額外的時間來識別獲勝者。 在這些情況下，固定總時程測試通常會在沒有統計上顯著結果的情況下結束。
* 測試兩個以上的體驗時，當單一體驗的表現遠遠優於所有其他體驗時，**[!UICONTROL 自動分配]**&#x200B;會比固定水平線測試（即樣本大小電腦建議的時間範圍）更快地找到獲勝者。 當兩個或多個體驗都和其他體驗「獲勝」，但彼此非常相符時，**[!UICONTROL 自動分配]**&#x200B;可能需要額外的時間來判斷哪一個體驗更優秀。 在這些情況下，固定視域測試通常會以結論「成功」體驗優於表現較差的體驗結束，但不會識別出哪個體驗更優秀。

+++

+++ 是否應從[!UICONTROL 自動分配]活動中移除表現缺佳的體驗，以加速決定獲勝者的程式？

沒有移除表現缺佳的體驗的真正理由。 **[!UICONTROL 自動分配]**&#x200B;會自動更頻繁地提供表現優異的體驗，而較少地提供表現不佳的體驗。 在活動中保留表現缺佳的體驗不會大幅影響決定獲勝者的速度。

20% 的訪客是隨機分配到所有體驗。 系統會將提供給表現缺佳的體驗的流量減至最少（20%除以體驗數量）。

+++

+++ 我可以在[!UICONTROL 自動分配]活動中途變更目標量度嗎？

[!DNL Adobe]不建議您在活動中途變更目標量度。 雖然在[!DNL Target] UI中的活動期間可以變更目標量度，您應該總是開始一個新的活動。 [!DNL Adobe]無法保證您在活動執行後變更目標量度會發生什麼情況。

此建議適用於使用[!DNL Target]或[!DNL Analytics] (A4T)作為報告來源的&#x200B;**[!UICONTROL 自動分配]**、**[!UICONTROL 自動鎖定目標]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動。

+++

+++ 我可以在[!UICONTROL 自動分配]活動中途變更報表來源嗎？

[!DNL Adobe]不建議您在活動中途變更報表來源。 雖然在[!DNL Target] UI中的活動期間可能會變更報表來源（從[!DNL Target]變更為A4T或反之），您應該一律開始新的活動。 [!DNL Adobe]無法保證您會在活動執行後變更活動中的報告來源時發生什麼情況。

此建議適用於使用[!DNL Target]或[!DNL Analytics] (A4T)作為報告來源的&#x200B;**[!UICONTROL 自動分配]**、**[!UICONTROL 自動鎖定目標]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動。

+++

+++ 我在執行[!UICONTROL 自動分配]活動時可以使用[!UICONTROL 重設報告資料]選項嗎？

不建議對&#x200B;**[!UICONTROL 自動分配]**&#x200B;活動使用&#x200B;**[!UICONTROL 重設報表資料]**&#x200B;選項。 雖然此選項會移除可見的報告資料，但不會移除&#x200B;**[!UICONTROL 自動分配]**&#x200B;模型中的所有訓練記錄。 不要使用&#x200B;**[!UICONTROL 重設報告資料]**&#x200B;選項，請建立新活動並停用原始活動。 此指引也適用於&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動。

+++

+++ [!UICONTROL 自動分配]如何建立環境相關模型？

**[!UICONTROL 自動分配]**&#x200B;僅根據預設環境中記錄的流量和轉換行為來建置模型。 依預設，**[!UICONTROL 生產]**&#x200B;是預設環境，但可在[!DNL Target]中變更預設環境（[管理>環境](/help/main/administrating-target/environments.md)）。

如果點選發生在其他（非預設）環境中，流量會根據在預設環境中觀察到的轉換行為分配。 該點選的結果（轉換或未轉換）會記錄下來以用於報表用途，但在&#x200B;**[!UICONTROL 自動分配]**&#x200B;模型中不會考慮。

當您選取其他環境時，報表會顯示該環境的流量和轉換。 報表的預設選定環境為全帳戶預設值。 預設環境無法根據每個活動進行設定。

+++

+++ [!UICONTROL 自動分配]活動能否在測試過程中調整回顧期間以考慮隨時間變更趨勢？

例如，活動是否可考慮12月份來決定如何分配流量，而非檢視9月的訪客資料（測試開始的時間）？

無. **[!UICONTROL 自動分配]**&#x200B;會考量整個活動的效能。

+++

+++ 如果成功體驗和訪客在取得活動資格時看到的不同，[!UICONTROL 自動分配]是否會向回訪訪客顯示成功體驗？

**[!UICONTROL 自動分配]**&#x200B;使用粘性決定，其原因與&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動具有粘性相同。 流量分配僅適用於新訪客。

+++

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

此視訊示範如何使用 Target 三步驟引導式工作流程來建立 A//B 測試。 從4:45開始討論&#x200B;**[!UICONTROL 自動分配]**。

* 在[!DNL Adobe Target]中建立A/B活動
* 使用手動分割或自動流量分配來分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)

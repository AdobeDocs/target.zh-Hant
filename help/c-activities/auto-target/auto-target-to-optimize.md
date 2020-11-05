---
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble shooting
description: Adobe Target中的Auto-Target使用進階的機器學習功能，從多個高效能行銷人員定義的體驗中選擇，以個人化內容並推動轉化。 自動鎖定目標會根據訪客的個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供每位訪客量身打造的最佳體驗。
title: 自動定位概觀
feature: auto-target
topic: Standard
uuid: fce769d2-9e7f-4064-add7-76e1fc394b4f
translation-type: tm+mt
source-git-commit: 7284a37dde0d89e1c81ef3813f98d936a4eced3b
workflow-type: tm+mt
source-wordcount: '2014'
ht-degree: 86%

---


# ![PREMIUM](/help/assets/premium.png) Auto-Target總覽

[!UICONTROL 自動鎖定目標]使用進階機器學習來從多個高效能之市場行銷人員定義的體驗中加以選取，以便個人化內容並促進轉換。自動鎖定目標會根據訪客的個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供每位訪客量身打造的最佳體驗。

>[!NOTE]
>
>[!UICONTROL 自動鎖定目標]是 [!DNL Target Premium] 解決方案內建的功能。若無 [!DNL Target Standard] 授權，[!DNL Target Premium] 不提供此功能。如需此授權提供之進階功能的詳細資訊，請參閱 [Target Premium](/help/c-intro/intro.md)。
>
>[!UICONTROL Analytics for Target] (A4T)支援 [!UICONTROL Auto-Target活動] 。 如需詳細資訊，請 [參閱建立使用Analytics作為報告來源的活動](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)。

## 使用Auto-Target的實際成功案例 {#success}

一家主要服裝零售商最近使用 [!UICONTROL Auto-Target] 活動搭配十種產品類別型體驗（加上隨機控制），為每位訪客提供正確的內容。 「[!UICONTROL 新增至購物車]」被選為主要最佳化度量。 目標體驗平均提升29.09%。 建立 [!UICONTROL Auto-Target模型後] ，活動設定為90%的個人化體驗。

短短10天，就實現了170多萬美元的提升。

繼續閱讀，瞭解如何使用 [!UICONTROL Auto-Target] ，為您的組織增加營收和提升度。

## 概述 {#section_972257739A2648AFA7E7556B693079C9}

[使用三步驟引導式工作流程建立 A/B 活動](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)時，您可以選擇使用[!UICONTROL 「針對個人化體驗自動鎖定目標」]選項來分配流量:

![個人化體驗選項的自動鎖定目標](/help/c-activities/assets/auto-target-ui-new.png)

A/B 活動流量內的[!UICONTROL 「自動鎖定目標」]選項可讓您只要按一下即可駕馭機器學習，以根據市場行銷人員定義的一組體驗進行個人化。[!UICONTROL 相較於傳統的 A/B 測試或自動分配，「自動鎖定目標」旨在決定要顯示給每個訪客的體驗，讓最佳化發揮到極致。]不同於 A/B 活動的目標是找出單一獲勝者，[!UICONTROL 自動鎖定目標]會自動為特定訪客決定最佳體驗 (根據其設定檔及其他情境資訊)，以實現高度個人化的體驗。

類似於自動個人化，[!UICONTROL 自動鎖定目標]也採用隨機森林演算法 (頂尖的資料科學整體方法)，以判斷要顯示給訪客的最佳體驗。因為[!UICONTROL 自動鎖定目標]可以適應訪客行為的變化，所以可不斷地執行以帶來提升度。這有時稱為「隨時待命」模式。

不同於 A/B 活動對特定訪客採用固定的體驗分配，[!UICONTROL 自動鎖定目標]會隨著每次造訪來最佳化指定的業務目標。如同在[!UICONTROL 自動個人化]中，依預設，[!UICONTROL 自動鎖定目標]也會保留一部分活動流量作為控制組以測量提升度。在活動中會提供隨機體驗給控制組中的訪客。

## 考量事項

There are a few important considerations to keep in mind when using [!UICONTROL Auto-Target]:

* 您無法將特定活動從[!UICONTROL 自動鎖定目標]切換到自動個人化，反之亦然。
* 在活動上線之後，您無法從手動流量分配 (傳統 A/B 測試) 切換到[!UICONTROL 自動鎖定目標]，反之亦然。
* 建立一個模型，用以識別個人化策略的效能與隨機提供的流量，以及將所有流量傳送至整體成功體驗。 此模型僅會在預設環境中考慮點擊和轉換。

   來自第二組模型的流量會針對每個模型群組(AP)或體驗(AT)建立。 對於這些模型，會考慮所有環境的點擊和轉換。

   因此，無論環境如何，請求都會以相同的模型提供，但是，多個流量應來自預設環境，以確保所識別的整體成功體驗與實際行為一致。

* 您必須使用至少兩個體驗。

## 術語 {#section_A309B7E0B258467789A5CACDC1D923F3}

討論[!UICONTROL 自動鎖定目標]時，下列詞語相當實用:

| 術語 | 定義 |
|---|---|
| 多臂吃角子老虎機 | 最佳化的多臂吃角子老虎機方法可平衡探索學習和該學習的利用。 |
| 隨機森林 | 隨機森林是先進的機器學習方法。以資料科學的行話來說，這是一種系綜法分類法 (或迴歸方法)，作法是根據訪客和造訪屬性來建構大量決策樹。在 Target 內，隨機森林可用來針對每個特定訪客，決定何種體驗預期轉換的可能性最高 (或每次造訪帶來的收入最高)。如需關於 Target 中隨機森林的資訊，請參閱[隨機森林演算法](/help/c-activities/t-automated-personalization/algo-random-forest.md)。 |
| Thompson 取樣 | Thompson 取樣的目標是要判斷哪個體驗是整體最佳 (非個人化)，同時將找到該體驗的「成本」降至最低。即便兩個體驗之間沒有統計上的差異，Thompson 取樣仍一律會挑選獲勝者。如需詳細資訊，請參閱 [Thompson 取樣](https://en.wikipedia.org/wiki/Thompson_sampling)。 |

## [!UICONTROL 自動鎖定目標]如何運作 {#section_77240E2DEB7D4CD89F52BE0A85E20136}

請前往下列連結，以進一步瞭解[!UICONTROL 自動鎖定目標]和自動個人化所根據的資料和演算法:

| 術語 | 詳細資料 |
|--- |--- |
| [隨機森林演算法](/help/c-activities/t-automated-personalization/algo-random-forest.md) | Target 在[!UICONTROL 自動鎖定目標]和自動個人化中採用的主要個人化演算法是「隨機森林」。隨機森林之類的整體方法會使用多個學習演算法，相較於任何建構式學習演算法可獲得更好的預測性效能。自動個人化系統中的隨機森林演算法為一種分類或迴歸方法，其運作方式是在訓練時建構許多決策。 |
| [上傳資料供 Target 的個人化演算法使用](/help/c-activities/t-automated-personalization/algo-random-forest.md) | 有幾種方式可輸入資料供[!UICONTROL 自動鎖定目標]和自動個人化模型使用。 |
| [Target 個人化演算法的資料收集](/help/c-activities/t-automated-personalization/ap-data.md) | Target 的個人化演算法會自動收集各種資料。 |

## 決定流量分配 {#section_AB3656F71D2D4C67A55A24B38092958F}

視活動的目標而定，您可能在控制體驗與個人化體驗之間選擇不同的流量分配。最佳作法是在活動上線之前就決定此目標。

[!UICONTROL 「自訂分配」]下拉式清單可讓您從下列選項中選擇:

* 評估個人化演算法
* 將個人化流量最大化
* 自訂分配

![分配目標下拉式清單](/help/c-activities/assets/split-new.png)

| 活動目標 | 建議的流量分配 | 取捨 |
|--- |--- |--- |
| **評估個人化演算法 (50/50)**: 如果您的目標是要測試演算法，請在控制與鎖定的演算法之間使用訪客的 50/50 百分比分割。此分割可提供提升度更準確的預估。建議「隨機體驗」搭配使用以作為控制。 | 50% 控制/ 50% 個人化體驗分割 | <ul><li>使控制與個人化之間的提升度達到最高準確性</li><li>相對較少的訪客將有個人化體驗</li></ul> |
| **最大化個人化流量 (90/10)**: 如果您的目標是要建立「一律開啟」的活動，請將 10% 的訪客放入控制，以確保有足夠的資料供演算法隨著時間繼續學習。請注意，這裡的取捨是以更大比例的流量交換個人化，因此在確切的提升度方面較不精確。無論您的目標為何，這是使用特定體驗作為控制時的建議流量分割。 | 最佳作法是採用 10% - 30% 控制/ 70% - 90% 個人化體驗分割 | <ul><li>將具有個人化體驗的訪客人數最大化</li><li>將提升度最大化</li><li>活動的提升度較不準確</li></ul> |
| **自訂分配** | 視需要手動分割百分比。 | <ul><li>您可能未達到理想的結果。如果不確定，請採用前述任一選項的建議。</li></ul> |

若要調整控制百分比，請按一下分配欄中的圖示。您無法將控制組降到 10% 以下。

![變更自動鎖定目標流量分配](/help/c-activities/assets/auto-target-control.png)

您可以[選取特定體驗以用來作為控制](/help/c-activities/t-automated-personalization/experience-as-control.md)，或者也可以使用隨機體驗選項。

## 何時應選擇[!UICONTROL 自動鎖定目標]而放棄自動個人化? {#section_BBC4871C87944DD7A8B925811A30C633}

在幾種情況下，您可能偏好使用[!UICONTROL 自動鎖定目標]，而不選擇自動個人化:

* 如果您想定義整個體驗，而非將會自動合併而形成體驗的個別選件。
* 如果您想利用[!UICONTROL 自動個人化]不支援的整套可視化體驗撰寫器 (VEC) 功能: 自訂程式碼編輯器、多個體驗對象及其他。
* 如果您想對不同體驗中的頁面進行結構性變更。例如，如果您想重新安排首面上的元素順序，則使用[!UICONTROL 自動鎖定目標]會比自動個人化更適合。

## [!UICONTROL 自動鎖定目標]與自動個人化有何共同點? {#section_2A601F482F9A44E38D4B694668711319}

**演算法會針對每次造訪的有利結果而最佳化。**

* 演算法會預測訪客的轉換傾向 (或預估來自轉換的收入)，以提供最佳體驗。
* 現有工作階段結束時，訪客即有資格獲得新的體驗 (除非訪客在控制組，在此情況下，最初造訪時指派給訪客的體驗在後續造訪時仍然相同)。
* 在工作階段內，預測不變，以維持視覺一致性。

**演算法會適應訪客行為的變化。**

* 多臂吃角子老虎機可確保模型一律會「消費」一小部分的流量以繼續在整個活動學習期間中學習，並且防止過度利用先前學習的趨勢。
* 每 24 小時會根據最新的訪客行為資料來重建基礎模型，以確保 Target 永遠採用不斷改變的訪客偏好設定。
* 如果演算法無法為個人決定勝出體驗，則會自動切換為顯示整體表現最佳的體驗，同時仍繼續尋找個人化獲勝者。採用 [Thompson 取樣](https://en.wikipedia.org/wiki/Thompson_sampling)可找出表現最佳的體驗。

**演算法會持續針對單一目標量度而最佳化。**

* 此量度可以是以轉換為基礎，或以收入為基礎 (具體而言，即「每次造訪帶來的收入」)。

**Target 會自動收集關於訪客的資訊以建置個人化模型。**

* 如需[!UICONTROL 自動鎖定目標]和自動個人化中使用的參數的詳細資訊，請參閱[自動個人化資料收集](/help/c-activities/t-automated-personalization/ap-data.md)。

**Target 會自動使用所有 Experience Cloud 的共用對象來建置個人化模型。**

* 您不需要做任何特定的動作將對象新增至模型。如需關於使用 Experience Cloud 對象搭配 Target 的資訊，請參閱 [Experience Cloud 受眾](/help/c-integrating-target-with-mac/mmp.md)

**市場行銷人員可以上傳離線資料、傾向分數或其他自訂資料，以建立個人化模型。**

* 進一步瞭解[上傳資料供自動鎖定目標和自動個人化使用](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

## [!UICONTROL 自動鎖定目標]與自動個人化有何不同? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**建立個人化模型時，自動鎖定目標所需的流量通常比自動個人化還少。**

雖然建立自動鎖定目標或自動個人化模型所需的&#x200B;*個別體驗*&#x200B;流量相同，但自動個人化活動中的體驗通常比自動鎖定目標活動更多。例如，如果您的[!UICONTROL 自動個人化]活動中有兩個位置，且已為各個位置建立兩個選件，則活動中總共會包含四個 (2 = 4) 體驗 (沒有排除項目)。使用[!UICONTROL 自動鎖定目標]時，您可以將體驗 1 設為包含位置 1 的選件 1 和位置 2 的選件 2，將體驗 2 設為包含位置 1 的選件 1 和位置 2 的選件 2。由於[!UICONTROL 自動鎖定目標]允許一個體驗內有多項變更，因此您可以減少活動中的體驗總數。

針對[!UICONTROL 自動鎖定目標]，可以使用簡易的經驗法則來瞭解流量需求:

* **當轉換是成功量度時:**&#x200B;每個體驗每日有 1,000 次造訪和至少 50 次轉換，此外，活動至少必須有 7,000 次造訪和 350 次轉換。
* **當每次造訪帶來的收入為您的成功量度時:**&#x200B;每個體驗每天 1,000 次造訪和至少 50 次轉換，此外，活動必須每個體驗至少 1,000 次轉換。RPV 通常需要更多資料才能建置模型，原因是造訪收入相較於轉換率一般會存在較高的資料變數。

**自動鎖定目標具有完整的設定功能。**

* 因為[!UICONTROL 自動鎖定目標]內嵌於 A/B 活動工作流程中，所以[!UICONTROL 自動鎖定目標]可享用更成熟且完整的可視化體驗撰寫器 (VEC)。您也可以搭配 [QA 連結](/help/c-activities/c-activity-qa/activity-qa.md)與[!UICONTROL 自動鎖定目標]一起使用。

**自動鎖定目標提供廣闊的線上測試架構。**

* 多臂吃角子老虎機屬於更大線上測試架構的一部分，可讓我們的資料科學家和研究人員瞭解在實際情況中持續改進的好處。
* 在未來，此測試可讓我們將機器學習平台開放給精通資料的客戶，讓他們引進自己的模型來擴大 Target 的模型。

## 報表和[!UICONTROL 自動鎖定目標] {#section_42EE7F5E65E84F89A872FE9921917F76}

如需詳細資訊，請參閱[報表](/help/c-reports/reports.md)一節中的[自動鎖定目標摘要報表](/help/c-reports/auto-target-summary-report.md)。

## 訓練影片：瞭解自動定位活動 ![概述徽章](/help/assets/overview.png)

本影片說明如何設定[!UICONTROL 自動鎖定目標] A/B 活動。

完成此訓練之後，您應該能夠:

* 定義[!UICONTROL 自動鎖定目標]測試
* 比較和對照[!UICONTROL 自動鎖定目標]與自動個人化
* 建立[!UICONTROL 自動鎖定目標]活動

>[!VIDEO](https://video.tv.adobe.com/v/18558)
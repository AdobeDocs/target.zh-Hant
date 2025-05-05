---
keywords: 自動鎖定目標；鎖定目標；流量分配；常見問題；faq；疑難排解；疑難排解
description: 瞭解[!UICONTROL Auto-Target]活動如何根據客戶設定檔和類似訪客的行為，提供每位訪客量身打造的最佳體驗。
title: 什麼是[!UICONTROL Auto-Target]活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 18%

---

# [!UICONTROL Auto-Target]總覽

[!DNL Adobe Target]中的[!UICONTROL Auto-Target]個活動使用進階機器學習來從多個高效能、行銷人員定義的體驗中加以選取，以個人化內容並促進轉換。 [!UICONTROL Auto-Target]會根據個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供每位訪客量身打造的最佳體驗。

>[!NOTE]
>
>* [!UICONTROL Auto-Target]是[!DNL Target Premium]解決方案的一部分。 若無 [!DNL Target Standard] 授權，[!DNL Target Premium] 不提供此功能。如需此授權提供之進階功能的詳細資訊，請參閱 [Target Premium](/help/main/c-intro/intro.md)。
>
>* [!UICONTROL Analytics for Target] (A4T)支援[!UICONTROL Auto-Target]個活動。 如需詳細資訊，請參閱自動分配和自動鎖定目標活動的[A4T支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

## 使用自動鎖定目標的真實成功案例 {#success}

一家主要服裝零售商最近使用具有十個產品類別型體驗（加上隨機控制項）的[!UICONTROL Auto-Target]活動為每位訪客提供正確內容。 &quot;[!UICONTROL Add to Cart]&quot;已選為主要最佳化量度。 目標體驗的平均提升度為29.09%。 建立[!UICONTROL Auto-Target]模型後，活動已設為90%個人化體驗。

在短短十天內，就實現了超過$1,700,000的提升度。

請繼續閱讀，瞭解如何使用[!UICONTROL Auto-Target]來提高組織的提升度和收入。

## 總覽 {#section_972257739A2648AFA7E7556B693079C9}

使用三步驟引導式工作流程[建立A/B活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)時，請在&#x200B;**[!UICONTROL Targeting]**&#x200B;頁面上選擇&#x200B;**[!UICONTROL Auto-Target for personalized experiences]**&#x200B;選項（步驟2）。

![流量分配方法設定](/help/main/c-activities/automated-traffic-allocation/assets/auto-target.png)

A/B活動流程中的[!UICONTROL Auto-Target]選項可讓您只要按一下即可駕馭機器學習，以根據市場行銷人員定義的一組體驗進行個人化。 相較於傳統的A/B測試或[!UICONTROL Auto Allocate]，[!UICONTROL Auto-Target]旨在決定要顯示給每個訪客的體驗，讓最佳化發揮到極致。 不同於A/B活動的目標是找出單一獲勝者，[!UICONTROL Auto-Target]會自動為特定訪客決定最佳體驗。 最佳體驗是根據訪客的設定檔和其他內容相關資訊，以提供高度個人化的體驗。

類似於[!UICONTROL Automated Personalization]，[!UICONTROL Auto-Target]使用[隨機森林演演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) （一種主流的資料科學整體方法）來決定要顯示給訪客的最佳體驗。 因為[!UICONTROL Auto-Target]可以適應訪客行為的變化，所以它可以持續執行以提供提升度。 此方法有時稱為「隨時待命」模式。

不同於A/B活動對特定訪客採用固定的體驗配置，[!UICONTROL Auto-Target]會隨著每次造訪來最佳化指定的業務目標。 如同在[!UICONTROL Auto Personalization]中，[!UICONTROL Auto-Target]預設會保留一部分活動流量作為控制組以測量提升度。 在活動中會提供隨機體驗給控制組中的訪客。

## 考量事項

使用[!UICONTROL Auto-Target]時，請謹記以下重要考量：

* 您無法將特定活動從[!UICONTROL Auto-Target]切換至[!UICONTROL Automated Personalization]，反之亦然。
* 您無法從[!UICONTROL Manual]流量分配（傳統[!UICONTROL A/B Test]）切換至[!UICONTROL Auto-Target]，反之亦然，因為活動已儲存為草稿。
* 我們建立了一個模型，用來識別個人化策略相對於隨機提供流量的效能，以及將所有流量傳送至整體成功體驗的效能。 此模型僅考量預設環境中的點選和轉換。

  系統會為每個模型群組(AP)或體驗(AT)建立第二組模型的流量。 對於這些模型中的每一個，都會考量所有環境的點選和轉換。

  無論環境為何，請求都是以相同的模式提供。 不過，多個流量應來自預設環境，以確保識別的整體成功體驗與真實世界行為一致。

* 使用最少兩個體驗。

## 術語 {#section_A309B7E0B258467789A5CACDC1D923F3}

討論[!UICONTROL Auto-Target]時，下列字詞相當實用：

| 術語 | 定義 |
|---|---|
| [多臂吃角子老虎機](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | 最佳化的多臂吃角子老虎機方法可平衡探索學習和該學習的利用。 |
| [隨機森林](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | 隨機森林是先進的機器學習方法。在資料科學方面，這是一種整體分類或回歸方法，會根據訪客和造訪屬性建構許多決策樹。 在[!DNL Target]內，隨機森林用於決定每個特定訪客的預期轉換可能性最高（或每次造訪收入最高）的體驗。 |
| [Thompson取樣](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | Thompson取樣的目標是決定哪些體驗是最佳的整體（非個人化），同時儘量減少尋找該體驗的「成本」。 Thompson取樣一律會挑選獲勝者，即使兩個體驗之間沒有統計差異。 |

## [!UICONTROL Auto-Target]的運作方式 {#section_77240E2DEB7D4CD89F52BE0A85E20136}

請前往下列連結，以進一步瞭解[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]的資料與演演算法：

| 術語 | 詳細資料 |
|--- |--- |
| [隨機森林演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | [!DNL Target]在[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]中使用的主要個人化演演算法是隨機森林。 整體方法（例如隨機森林）會使用多種學習演演算法，以獲得比從任何組成學習演演算法都更好的預測效能。 [!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]活動中的隨機森林演演算法是一種分類或回歸方法，可在訓練時建構許多決策樹來運作。 |
| [正在上傳 [!DNL Target]的Personalization演演算法的資料](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | 有幾種方式可以輸入[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]模型的資料。 |
| [ [!DNL Target]的Personalization演演算法的資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md) | [!DNL Target]的個人化演演算法會自動收集各種資料。 |

## 決定流量分配 {#section_AB3656F71D2D4C67A55A24B38092958F}

視活動的目標而定，您可能在控制體驗與個人化體驗之間選擇不同的流量分配。最佳作法是在活動上線之前就決定此目標。

[!UICONTROL Custom Allocation]下拉式清單可讓您從下列選項中選擇：

* [!UICONTROL Evaluate Personalization Algorithm (50/50)]
* [!UICONTROL Maximize Personalization Traffic (90/10)]
* [!UICONTROL Custom Allocation]

![分配目標下拉式清單](/help/main/c-activities/assets/split-new-ui.png)

下表說明三個選項：

| 活動目標 | 建議的流量分配 | 取捨 |
|--- |--- |--- |
| **[!UICONTROL Evaluate Personalization Algorithm (50/50)]**：如果您的目標是要測試演演算法，請在控制與鎖定的演演算法之間使用訪客的50/50百分比分割。 此分割可提供提升度更準確的預估。建議搭配使用「隨機體驗」作為控制。 | 50% 控制/ 50% 個人化體驗分割 | <ul><li>使控制與個人化之間的提升度達到最高準確性</li><li>擁有個人化體驗的訪客相對較少</li></ul> |
| **[!UICONTROL Maximize Personalization Traffic (90/10)]**：如果您的目標是要建立「一律開啟」的活動，請將10%的訪客放入控制，以確保有足夠的資料供演演算法隨著時間繼續學習。 這裡的取捨是以更大比例的流量交換個人化，因此在確切的提升度方面較不精確。 無論您的目標為何，這是使用特定體驗作為控制時的建議流量分割。 | 最佳作法是採用 10% - 30% 控制/ 70% - 90% 個人化體驗分割 | <ul><li>將擁有個人化體驗的訪客數量最大化</li><li>將提升度最大化</li><li>活動的提升度較不準確</li></ul> |
| **自訂分配** | 視需要手動分割百分比。 | <ul><li>您可能未達到理想的結果。如果不確定，請採用前述任一選項的建議。</li></ul> |

若要調整[!UICONTROL Control]百分比，請按一下[!UICONTROL Traffic Allocation]窗格中的[!UICONTROL Experiences]，然後視需要調整百分比。 您無法將控制組降到 10% 以下。

您可以[選取特定體驗以用來作為控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)，或者也可以使用隨機體驗選項。

## 何時應選擇[!UICONTROL Auto-Target]而非[!UICONTROL Automated Personalization]？{#section_BBC4871C87944DD7A8B925811A30C633}

在幾種情況下，您可能會偏好使用[!UICONTROL Auto-Target]而非[!UICONTROL Automated Personalization]：

* 如果您想要定義整個體驗，而非自動合併以形成體驗的個別選件。
* 如果您想使用[!UICONTROL Auto Personalization]不支援的完整[!UICONTROL Visual Experience Composer] (VEC)功能集：自訂程式碼編輯器、多個體驗對象等等。
* 如果您想對不同體驗中的頁面進行結構性變更。例如，如果您想重新排列首頁上的元素，[!UICONTROL Auto-Target]比[!UICONTROL Automated Personalization]更適合使用。

## [!UICONTROL Auto-Target]與[!UICONTROL Automated Personalization]有何共同點？{#section_2A601F482F9A44E38D4B694668711319}

### 演演算法會針對每次造訪的有利結果最佳化。

* 演演算法會預測訪客的轉換傾向（或轉換的估計收入），以提供最佳體驗。
* 訪客符合在現有工作階段結束後使用新體驗的資格（除非訪客是在控制組中，在這種情況下，訪客在第一次造訪時指派的體驗在後續造訪中維持不變）。
* 在工作階段中，預測不會變更，以維持視覺一致性。

### 演演算法會因應訪客行為的變化而改變。

* 多臂吃角子老虎機可確保模型一律「花費」少量流量，在整個活動學習期間持續學習，並防止過度利用先前學習的趨勢。
* 基礎模型每24小時會使用最新的訪客行為資料重建一次，以確保[!DNL Target]一律會利用訪客偏好設定的不斷變化進行探索。
* 如果演算法無法為個人決定勝出體驗，則會自動切換為顯示整體表現最佳的體驗，同時仍繼續尋找個人化獲勝者。採用 [Thompson 取樣](https://en.wikipedia.org/wiki/Thompson_sampling)可找出表現最佳的體驗。

### 演演算法會持續針對單一目標量度最佳化。

* 此量度可以是轉換型或收入型（更具體地說[!UICONTROL Revenue per Visit]）。

### [!DNL Target]會自動收集關於訪客的資訊以建置個人化模型。

* 如需[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]中所使用引數的詳細資訊，請參閱[Automated Personalization資料彙集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

### [!DNL Target]會自動使用所有[!DNL Adobe Experience Cloud]個共用對象來建置個人化模型。

* 您不需要做任何特定的動作將對象新增至模型。如需將 [!DNL Experience Cloud Audiences] 用於 [!DNL Target] 的相關資訊，請參閱 [Experience Cloud 客群](/help/main/c-integrating-target-with-mac/mmp.md)。

### 行銷人員可以上傳離線資料、傾向分數或其他自訂資料，以建立個人化模型。

* 深入瞭解[上傳[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)的資料。

## [!UICONTROL Auto-Target]與[!UICONTROL Automated Personalization]有何不同？{#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### [!UICONTROL Auto-Target]建立個人化模型所需的流量通常少於[!UICONTROL Automated Personalization]。

雖然[!UICONTROL Auto-Target]或[!UICONTROL Auto Personalization]模型建置所需的每個體驗&#x200B;*流量*&#x200B;相同，但[!UICONTROL Automated Personalization]活動中的體驗通常比[!UICONTROL Auto-Target]活動中的體驗更多。

例如，如果您的[!UICONTROL Auto Personalization]活動中有兩個位置，且已為各個位置建立兩個選件，則活動中總共會包含四個(2 = 4)體驗（沒有排除專案）。 使用[!UICONTROL Auto-Target]，您可以將體驗1設為包含位置1的選件1和位置2的選件2，將體驗2設為包含位置1的選件1和位置2的選件2。 因為[!UICONTROL Auto-Target]可讓您選擇在一個體驗中進行多次變更，所以您可以減少活動中的體驗總數。

對於[!UICONTROL Auto-Target]，可以使用簡易的經驗法則來瞭解流量需求：

* **當[!UICONTROL Conversion]是您的成功量度時：** 1,000次造訪，每個體驗每天至少有50次轉換，此外，活動必須至少有7,000次造訪和350次轉換。
* **當[!UICONTROL Revenue per Visit]是您的成功量度時：** 1,000次造訪，每個體驗每天至少有50次轉換，此外，每個體驗必須有至少1,000次轉換。 RPV 通常需要更多資料才能建置模型，原因是造訪收入相較於轉換率一般會存在較高的資料變數。

### [!UICONTROL Auto-Target]具有完整的設定功能。

* 因為[!UICONTROL Auto-Target]內嵌於A/B活動工作流程中，[!UICONTROL Auto-Target]可享用更成熟且完整的[!UICONTROL Visual Experience Composer] (VEC)。 您也可以將[QA連結](/help/main/c-activities/c-activity-qa/activity-qa.md)與[!UICONTROL Auto-Target]搭配使用。

### [!UICONTROL Auto-Target]提供廣泛的線上測試架構。

* 多臂吃角子是大型線上測試架構的一部分，可讓[!DNL Adobe]位資料科學家和研究人員瞭解其在真實世界狀況中持續改善的好處。
* 未來，此測試平台將允許我們向熟悉資料的使用者端開啟[!DNL Adobe]機器學習平台，以便他們能夠引進自己的模型來擴充[!DNL Target]模型。

## 報告與[!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

如需詳細資訊，請參閱[報告和自動鎖定目標](/help/main/c-activities/auto-target/reporting-and-auto-target.md)。

---
keywords: 自動鎖定目標;鎖定目標;流量分配;常見問題集;faq;疑難排解
description: 瞭解中的自動目標活動 [!DNL Target] 根據客戶資料和類似訪客的行為，為每位訪客提供量身定製的體驗。
title: 什麼是自動目標活動？
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1991'
ht-degree: 70%

---

# ![高級](/help/main/assets/premium.png) 自動目標概述

[!UICONTROL 自動目標] 活動 [!DNL Adobe Target] 使用高級機器學習從多個高效能的商家定義體驗中進行選擇，以個性化內容和驅動器轉換。 Auto-Target根據單個客戶配置檔案以及具有類似配置檔案的先前訪問者的行為，為每位訪問者提供最為定製的體驗。

>[!NOTE]
>
>[!UICONTROL 自動鎖定目標]是 [!DNL Target Premium] 解決方案內建的功能。若無 [!DNL Target Standard] 授權，[!DNL Target Premium] 不提供此功能。如需此授權提供之進階功能的詳細資訊，請參閱 [Target Premium](/help/main/c-intro/intro.md)。
>
>[!UICONTROL 目標分析] (A4T)支援 [!UICONTROL 自動目標] 活動。 如需詳細資訊，請參閱[「自動分配」和「自動鎖定目標」活動的 A4T 支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

## 使用Auto-Target的真實成功案例 {#success}

一家主要服裝零售商最近使用 [!UICONTROL 自動目標] 活動，包括十種基於產品類別的體驗（加上隨機控制），為每位訪問者提供適當的內容。 &quot;[!UICONTROL 添加到購物車]&quot;被選作主要優化度量。 目標體驗平均提升29.09%。 在 [!UICONTROL 自動目標] 模型，活動設定為90%的個性化體驗。

短短10天，就實現了170多萬美元的升降。

繼續閱讀以瞭解如何使用 [!UICONTROL 自動目標] 增加組織的收入和收入。

## 總覽 {#section_972257739A2648AFA7E7556B693079C9}

[使用三步驟引導式工作流程建立 A/B 活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)時，您可以選擇使用[!UICONTROL 「針對個人化體驗自動鎖定目標」]選項來分配流量:

![個人化體驗選項的自動鎖定目標](/help/main/c-activities/assets/auto-target-ui-new.png)

A/B 活動流量內的[!UICONTROL 「自動鎖定目標」]選項可讓您只要按一下即可駕馭機器學習，以根據市場行銷人員定義的一組體驗進行個人化。[!UICONTROL 相較於傳統的 A/B 測試或自動分配，「自動鎖定目標」旨在決定要顯示給每個訪客的體驗，讓最佳化發揮到極致。]不同於 A/B 活動的目標是找出單一獲勝者，[!UICONTROL 自動鎖定目標]會自動為特定訪客決定最佳體驗 (根據其設定檔及其他情境資訊)，以實現高度個人化的體驗。

類似於自動個人化，[!UICONTROL 自動鎖定目標]也採用隨機森林演算法 (頂尖的資料科學整體方法)，以判斷要顯示給訪客的最佳體驗。因為[!UICONTROL 自動鎖定目標]可以適應訪客行為的變化，所以可不斷地執行以帶來提升度。這有時稱為「隨時待命」模式。

不同於 A/B 活動對特定訪客採用固定的體驗分配，[!UICONTROL 自動鎖定目標]會隨著每次造訪來最佳化指定的業務目標。如同在[!UICONTROL 自動個人化]中，依預設，[!UICONTROL 自動鎖定目標]也會保留一部分活動流量作為控制組以測量提升度。在活動中會提供隨機體驗給控制組中的訪客。

## 考量事項

使用時需要考慮幾個重要的考慮因素 [!UICONTROL 自動目標]:

* 您無法從 [!UICONTROL 自動目標] Automated Personalization，反之亦然。
* 您不能從手動流量分配(傳統A/BTest)切換到 [!UICONTROL 自動目標]，在活動進行後，反之亦然。
* 建立了一個模型來識別個性化策略與隨機服務流量的效能，以及將所有流量發送到總體獲勝體驗。 此模型僅考慮預設環境中的命中和轉換。

   來自第二組模型的流量是針對每個建模組(AP)或經驗(AT)構建的。 對於這些模型中的每一個，都考慮了所有環境的命中和轉換。

   請求使用相同的模型（不管環境如何）提供服務，但多個通信量應來自預設環境，以確保所識別的整體贏取體驗與真實世界行為相一致。

* 至少使用兩個體驗。

## 術語 {#section_A309B7E0B258467789A5CACDC1D923F3}

討論[!UICONTROL 自動鎖定目標]時，下列詞語相當實用:

| 術語 | 定義 |
|---|---|
| 多臂吃角子老虎機 | 最佳化的多臂吃角子老虎機方法可平衡探索學習和該學習的利用。 |
| 隨機森林 | 隨機森林是先進的機器學習方法。在資料科學中，它是一種整合分類或回歸方法，通過基於訪問者和訪問屬性構建多個決策樹來工作。 在 Target 內，隨機森林可用來針對每個特定訪客，決定何種體驗預期轉換的可能性最高 (或每次造訪帶來的收入最高)。如需關於 Target 中隨機森林的資訊，請參閱[隨機森林演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。 |
| Thompson 取樣 | Thompson 取樣的目標是要判斷哪個體驗是整體最佳 (非個人化)，同時將找到該體驗的「成本」降至最低。即便兩個體驗之間沒有統計上的差異，Thompson 取樣仍一律會挑選獲勝者。如需詳細資訊，請參閱 [Thompson 取樣](https://en.wikipedia.org/wiki/Thompson_sampling)。 |

## [!UICONTROL 自動鎖定目標]如何運作 {#section_77240E2DEB7D4CD89F52BE0A85E20136}

請前往下列連結，以進一步瞭解[!UICONTROL 自動鎖定目標]和自動個人化所根據的資料和演算法:

| 術語 | 詳細資料 |
|--- |--- |
| [隨機森林演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Target 在[!UICONTROL 自動鎖定目標]和自動個人化中採用的主要個人化演算法是「隨機森林」。隨機森林之類的整體方法會使用多個學習演算法，相較於任何建構式學習演算法可獲得更好的預測性效能。Automated Personalization系統中的隨機森林算法是一種分類或回歸方法，它通過在訓練時間構造多個決策樹來操作。 |
| [上傳資料供 Target 的個人化演算法使用](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | 有幾種方式可輸入資料供[!UICONTROL 自動鎖定目標]和自動個人化模型使用。 |
| [Target 個人化演算法的資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md) | 目標的個性化算法自動收集各種資料。 |

## 決定流量分配 {#section_AB3656F71D2D4C67A55A24B38092958F}

視活動的目標而定，您可能在控制體驗與個人化體驗之間選擇不同的流量分配。最佳作法是在活動上線之前就決定此目標。

[!UICONTROL 「自訂分配」]下拉式清單可讓您從下列選項中選擇:

* 評估個人化演算法
* 將個人化流量最大化
* 自訂分配

![分配目標下拉式清單](/help/main/c-activities/assets/split-new.png)

| 活動目標 | 建議的流量分配 | 取捨 |
|--- |--- |--- |
| **評估個人化演算法 (50/50)**: 如果您的目標是要測試演算法，請在控制與鎖定的演算法之間使用訪客的 50/50 百分比分割。此分割可提供提升度更準確的預估。建議「隨機體驗」搭配使用以作為控制。 | 50% 控制/ 50% 個人化體驗分割 | <ul><li>使控制與個人化之間的提升度達到最高準確性</li><li>擁有個性化體驗的訪客相對較少</li></ul> |
| **最大化個人化流量 (90/10)**: 如果您的目標是要建立「一律開啟」的活動，請將 10% 的訪客放入控制，以確保有足夠的資料供演算法隨著時間繼續學習。請注意，這裡的折衷是，為了將流量的較大比例個性化，您對電梯的準確程度要求較低。 無論您的目標為何，這是使用特定體驗作為控制時的建議流量分割。 | 最佳作法是採用 10% - 30% 控制/ 70% - 90% 個人化體驗分割 | <ul><li>將具有個人化體驗的訪客人數最大化</li><li>將提升度最大化</li><li>活動的提升度較不準確</li></ul> |
| **自訂分配** | 視需要手動分割百分比。 | <ul><li>您可能未達到理想的結果。如果不確定，請採用前述任一選項的建議。</li></ul> |

若要調整控制百分比，請按一下分配欄中的圖示。您無法將控制組降到 10% 以下。

![變更自動鎖定目標流量分配](/help/main/c-activities/assets/auto-target-control.png)

您可以[選取特定體驗以用來作為控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)，或者也可以使用隨機體驗選項。

## 何時應選擇[!UICONTROL 自動鎖定目標]而放棄自動個人化? {#section_BBC4871C87944DD7A8B925811A30C633}

在幾種情況下，您可能偏好使用[!UICONTROL 自動鎖定目標][!UICONTROL ，而不選擇自動個人化]:

* 如果您想定義整個體驗，而非將會自動合併而形成體驗的個別選件。
* 如果要使用Visual Experience Composer(VEC)功能的完整集，則不受支援 [!UICONTROL 自動個性化]:自定義代碼編輯器、多個體驗對象等。
* 如果您想對不同體驗中的頁面進行結構性變更。例如，如果要重新排列首頁上的元素， [!UICONTROL 自動目標] 比Automated Personalization更合適。

## [!UICONTROL 自動鎖定目標]與自動個人化有何共同點? {#section_2A601F482F9A44E38D4B694668711319}

**演算法會針對每次造訪的有利結果而最佳化。**

* 演算法會預測訪客的轉換傾向 (或預估來自轉換的收入)，以提供最佳體驗。
* 在現有會期結束後，訪問者有資格獲得新的體驗（除非訪問者在控制組內，在這種情況下，首次訪問時分配給訪問者的體驗在隨後的訪問中保持不變）。
* 在工作階段內，預測不變，以維持視覺一致性。

**演算法會適應訪客行為的變化。**

* 多臂強盜確保該模型始終&quot;花費&quot;少量流量，以在活動學習的整個生命週期中繼續學習，並防止過度利用以前學習的趨勢。
* 每24小時使用最新訪問者行為資料重建基礎模型，以確保Target始終在利用更改的訪問者首選項。
* 如果演算法無法為個人決定勝出體驗，則會自動切換為顯示整體表現最佳的體驗，同時仍繼續尋找個人化獲勝者。採用 [Thompson 取樣](https://en.wikipedia.org/wiki/Thompson_sampling)可找出表現最佳的體驗。

**演算法會持續針對單一目標量度而最佳化。**

* 此量度可以是以轉換為基礎，或以收入為基礎 (具體而言，即「每次造訪帶來的收入」)。

**Target 會自動收集關於訪客的資訊以建置個人化模型。**

* 如需[!UICONTROL 自動鎖定目標]和自動個人化中使用的參數的詳細資訊，請參閱[自動個人化資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

**Target 會自動使用所有 Experience Cloud 的共用對象來建置個人化模型。**

* 您不需要做任何特定的動作將對象新增至模型。如需關於使用 Experience Cloud 對象搭配 Target 的資訊，請參閱 [Experience Cloud 受眾](/help/main/c-integrating-target-with-mac/mmp.md)

**市場行銷人員可以上傳離線資料、傾向分數或其他自訂資料，以建立個人化模型。**

* 進一步瞭解[上傳資料供自動鎖定目標和自動個人化使用](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

## [!UICONTROL 自動鎖定目標]與自動個人化有何不同? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**建立個人化模型時，自動鎖定目標所需的流量通常比自動個人化還少。**

雖然建立自動鎖定目標或自動個人化模型所需的&#x200B;*個別體驗*&#x200B;流量相同，但自動個人化活動中的體驗通常比自動鎖定目標活動更多。例如，如果您的[!UICONTROL 自動個人化]活動中有兩個位置，且已為各個位置建立兩個選件，則活動中總共會包含四個 (2 = 4) 體驗 (沒有排除項目)。使用[!UICONTROL 自動鎖定目標]時，您可以將體驗 1 設為包含位置 1 的選件 1 和位置 2 的選件 2，將體驗 2 設為包含位置 1 的選件 1 和位置 2 的選件 2。由於[!UICONTROL 自動鎖定目標]允許一個體驗內有多項變更，因此您可以減少活動中的體驗總數。

針對[!UICONTROL 自動鎖定目標]，可以使用簡易的經驗法則來瞭解流量需求:

* **當轉換是成功量度時:**&#x200B;每個體驗每日有 1,000 次造訪和至少 50 次轉換，此外，活動至少必須有 7,000 次造訪和 350 次轉換。
* **當每次造訪帶來的收入為您的成功量度時:**&#x200B;每個體驗每天 1,000 次造訪和至少 50 次轉換，此外，活動必須每個體驗至少 1,000 次轉換。RPV 通常需要更多資料才能建置模型，原因是造訪收入相較於轉換率一般會存在較高的資料變數。

**自動鎖定目標具有完整的設定功能。**

* 因為[!UICONTROL 自動鎖定目標]內嵌於 A/B 活動工作流程中，所以[!UICONTROL 自動鎖定目標]可享用更成熟且完整的可視化體驗撰寫器 (VEC)。您也可以搭配 [QA 連結](/help/main/c-activities/c-activity-qa/activity-qa.md)與[!UICONTROL 自動鎖定目標]一起使用。

**自動鎖定目標提供廣闊的線上測試架構。**

* 多臂吃角子老虎機屬於更大線上測試架構的一部分，可讓我們的資料科學家和研究人員瞭解在實際情況中持續改進的好處。
* 在未來，此測試可讓我們將機器學習平台開放給精通資料的客戶，讓他們引進自己的模型來擴大 Target 的模型。

## 報表和[!UICONTROL 自動鎖定目標] {#section_42EE7F5E65E84F89A872FE9921917F76}

如需詳細資訊，請參閱[報表](/help/main/c-reports/reports.md)一節中的[自動鎖定目標摘要報表](/help/main/c-reports/auto-target-summary-report.md)。

## 培訓視頻：瞭解自動目標活動 ![概述徽章](/help/main/assets/overview.png)

本影片說明如何設定[!UICONTROL 自動鎖定目標] A/B 活動。

完成此訓練之後，您應該能夠:

* 定義[!UICONTROL 自動鎖定目標]測試
* 比較和對照[!UICONTROL 自動鎖定目標]與自動個人化
* 建立[!UICONTROL 自動鎖定目標]活動

>[!VIDEO](https://video.tv.adobe.com/v/18558)

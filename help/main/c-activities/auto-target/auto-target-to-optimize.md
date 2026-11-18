---
keywords: 自動鎖定目標；鎖定目標；流量分配；常見問題；faq；疑難排解；疑難排解
description: 瞭解[!UICONTROL 自動鎖定目標]活動如何根據客戶設定檔和類似訪客的行為，提供每位訪客量身打造的最佳體驗。
title: 什麼是[!UICONTROL 自動鎖定目標]活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
TQID: 'https://experienceleague.adobe.com/uKmfIlOcT-tZgOjuvERXuif-Y5-2Jw3prtPbuBjv1is'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: de439134b0ee5aa795ae255bba852b9b6f10da12
workflow-type: tm+mt
source-wordcount: '2072'
ht-degree: 12%
---
# 開始使用[!UICONTROL 自動鎖定目標] {#auto-target-overview}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動如何為每位訪客提供最自訂的體驗、其運作方式、如何選擇流量分配，以及它與&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;的比較方式。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動會使用進階機器學習，從多個高效能、行銷人員定義的體驗中加以選取，以個人化內容並促進轉換。 **[!UICONTROL 自動鎖定目標]**&#x200B;會根據個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供每位訪客量身打造的最佳體驗。

>[!NOTE]
>
>* **[!UICONTROL 自動鎖定目標]**&#x200B;屬於[!DNL Target Premium]方案的一部分。 若無 [!DNL Target Standard] 授權，[!DNL Target Premium] 不提供此功能。 如需此授權提供之進階功能的詳細資訊，請參閱 [Target Premium](/help/main/c-intro/intro.md)。
>
>* **[!UICONTROL Analytics for Target]** (A4T)支援&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動。 如需詳細資訊，請參閱自動分配和自動鎖定目標活動的[A4T支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。

使用三步驟引導式工作流程[建立A/B活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)時，請在&#x200B;**[!UICONTROL 鎖定目標]**&#x200B;頁面上選擇&#x200B;**[!UICONTROL 針對個人化體驗自動鎖定目標]**&#x200B;選項（步驟2）。 如需相關步驟，請參閱[建立自動鎖定目標活動](/help/main/c-activities/auto-target/create-auto-target.md)。

![流量分配方法設定](/help/main/c-activities/automated-traffic-allocation/assets/auto-target.png)

A/B活動流程中的此選項可讓您使用機器學習，根據市場行銷人員定義的一組體驗，按一下即可個人化內容。 **[!UICONTROL 自動鎖定目標]**&#x200B;的設計目的，是藉由決定要顯示給每個訪客的體驗，來達到最佳化，而不是像傳統的A/B測試或&#x200B;**[!UICONTROL 自動分配]**&#x200B;那樣最佳化。 不同於A/B活動的目標是找出單一獲勝者，**[!UICONTROL 自動鎖定目標]**&#x200B;會自動為特定訪客決定最佳體驗。 最佳體驗取決於訪客個人資料和其他內容相關資訊。

類似於&#x200B;**[!UICONTROL Automated Personalization]**，**[!UICONTROL 自動鎖定目標]**&#x200B;使用[隨機森林演演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) （一種主流的資料科學整體方法）來決定要向訪客顯示的最佳體驗。 **[!UICONTROL 自動鎖定目標]**&#x200B;可以適應訪客行為的變化，因此可以持續執行以提供提升度。 此方法有時稱為「隨時待命」模式。

不同於A/B活動對特定訪客採用固定的體驗分配，**[!UICONTROL 自動鎖定目標]**&#x200B;會隨著每次造訪來最佳化指定的業務目標。 如同&#x200B;**[!UICONTROL Automated Personalization]**，**[!UICONTROL 自動鎖定目標]**&#x200B;預設會將部分活動流量保留為控制組，以測量提升度。 在活動中會提供隨機體驗給控制組中的訪客。

## 考量事項 {#considerations}

使用&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;時，請記住下列要點：

* 請留意活動圖形。 相較於原始體驗計數，效能更多地取決於位置×選件的數量。 大型笛卡爾組合可能會減慢&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;的載入和編輯速度，即使低於記錄的體驗限制也是如此。

  最佳做法是將&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動保留到4-6位置，每個位置有4-6個選件。 不建議使用較大的設定。 這些活動是直接在&#x200B;**[!UICONTROL 體驗]**&#x200B;步驟中建置，因此[!DNL Target] UI在組態超過支援的臨界值時，可能會顯示內嵌警告或封鎖儲存。

* 您無法將特定活動從&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;切換至&#x200B;**[!UICONTROL Automated Personalization]**，反之亦然。
* 將活動儲存為草稿後，您無法從&#x200B;**[!UICONTROL 手動]**&#x200B;流量分配（傳統&#x200B;**[!UICONTROL A/B測試]**）切換為&#x200B;**[!UICONTROL 自動鎖定目標]**，反之亦然。
* 我們建立了一個模型，用來識別個人化策略相對於隨機提供流量的效能，以及將所有流量傳送至整體成功體驗的效能。 此模型僅考量預設環境中的點選和轉換。

  系統會為每個模型群組(AP)或體驗(AT)建立第二組模型。 對於這些模型中的每一個，都會考量所有環境的點選和轉換。

  無論環境為何，請求都是以相同的模式提供。 不過，多個流量應來自預設環境，以確保識別的整體成功體驗與真實世界行為一致。

* 使用最少兩個體驗。

## 術語 {#section_A309B7E0B258467789A5CACDC1D923F3}

討論&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;時，下列字詞相當實用：

| 術語 | 定義 |
|---|---|
| [多臂吃角子老虎機](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | 最佳化的多臂吃角子老虎機方法可平衡探索學習和該學習的利用。 |
| [隨機森林](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | 隨機森林是先進的機器學習方法。 在資料科學術語中，這是一種整體分類或回歸方法，會根據訪客和造訪屬性建構許多決策樹。 在[!DNL Target]內，隨機森林用於決定每個特定訪客的預期轉換可能性最高（或每次造訪收入最高）的體驗。 |
| [Thompson取樣](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | Thompson取樣的目標是決定哪些體驗是最佳的整體（非個人化），同時儘量減少尋找該體驗的「成本」。 Thompson取樣一律會挑選獲勝者，即使兩個體驗之間沒有統計差異。 |

## [!UICONTROL 自動鎖定目標]的運作方式 {#section_77240E2DEB7D4CD89F52BE0A85E20136}

下列頁面說明&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;的資料與演演算法：

| 主題 | 詳細資料 |
|--- |--- |
| [隨機森林演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | [!DNL Target]的主要個人化演演算法（用於&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**）是隨機森林。 整體方法（例如隨機森林）會使用多種學習演演算法，以獲得比從任何組成學習演演算法都更好的預測效能。 **[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動中的隨機森林演演算法是一種分類或回歸方法，可在訓練時建構許多決策樹來運作。 |
| [正在上傳 [!DNL Target] Personalization演演算法的資料](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md) | 有幾種方式可輸入&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;模型的資料。 |
|  [!DNL Target] Personalization演演算法的[資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md) | [!DNL Target]的個人化演演算法會自動收集各種資料。 |

## 決定流量分配 {#section_AB3656F71D2D4C67A55A24B38092958F}

根據活動的目標，您可以在控制與個人化體驗之間選擇不同的流量分配。 最佳作法是在活動上線之前就決定此目標。

**[!UICONTROL 「自訂分配」]**&#x200B;下拉式清單可讓您從下列選項中選擇:

* **[!UICONTROL 評估Personalization演演算法(50/50)]**
* **[!UICONTROL 最大化Personalization流量(90/10)]**
* **[!UICONTROL 自訂分配]**

![分配目標下拉式清單](/help/main/c-activities/assets/split-new-ui.png)

下表說明三個選項：

| 活動目標 | 建議的流量分配 | 取捨 |
|--- |--- |--- |
| **[!UICONTROL 評估個人化演算法 (50/50)]**: 如果您的目標是要測試演算法，請在控制與鎖定的演算法之間使用訪客的 50/50 百分比分割。 此分割可提供提升度更準確的預估。 建議搭配使用「隨機體驗」作為控制。 | 50% 控制/ 50% 個人化體驗分割 | <ul><li>使控制與個人化之間的提升度達到最高準確性</li><li>擁有個人化體驗的訪客相對較少</li></ul> |
| **[!UICONTROL 最大化Personalization流量(90/10)]**：如果您的目標是要建立「一律開啟」的活動，請將10%的訪客放入控制，以確保有足夠的資料供演演算法隨著時間繼續學習。 這裡的取捨是以更大比例的流量交換個人化，因此在確切的提升度方面較不精確。 無論您的目標為何，這是使用特定體驗作為控制時的建議流量分割。 | 最佳作法是採用 10% - 30% 控制/ 70% - 90% 個人化體驗分割 | <ul><li>將擁有個人化體驗的訪客數量最大化</li><li>將提升度最大化</li><li>活動的提升度較不準確</li></ul> |
| **[!UICONTROL 自訂分配]** | 視需要手動分割百分比。 | <ul><li>您可能未達到理想的結果。 如果不確定，請採用前述任一選項的建議。</li></ul> |

若要調整&#x200B;**[!UICONTROL 控制]**&#x200B;百分比，請按一下&#x200B;**[!UICONTROL 流量分配]**&#x200B;窗格中的&#x200B;**[!UICONTROL 體驗]**，然後視需要調整百分比。 您無法將控制組降到 10% 以下。

您可以[選取要用來作為控制的特定體驗](/help/main/c-activities/t-automated-personalization/experience-as-control.md)，或者您可以使用&#x200B;**[!UICONTROL 隨機體驗]**&#x200B;選項。

## 比較[!UICONTROL 自動鎖定目標]與[!UICONTROL Automated Personalization] {#compare-at-ap}

**[!UICONTROL 自動鎖定目標]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;共用相同的演演算法和資料，但它們在建立體驗的方式以及模型所需的流量方面有所不同。

### 這兩種活動型別的共同之處 {#section_2A601F482F9A44E38D4B694668711319}

* 每次造訪的&#x200B;**最佳化。** 演演算法會預測訪客轉換的傾向（或轉換的估計收入），以提供最佳體驗。 訪客符合在現有工作階段結束時取得新體驗的資格。 控制組中的訪客則為例外，他們會保留在第一次造訪時指派的體驗。 在工作階段中，預測不會變更，以維持視覺一致性。
* **適應訪客行為的變化。** 多臂吃角子老虎機一律會「花費」一小部分的流量，在整個活動期間繼續學習，並防止過度利用先前學習到的趨勢。 基礎模型會使用最新的訪客行為資料每24小時重建一次。 如果演演算法無法判斷個人的成功體驗，它會自動切換為顯示整體表現最佳的體驗（使用[Thompson取樣](https://en.wikipedia.org/wiki/Thompson_sampling)找到），同時繼續尋找個人化的成功者。
* **單一目標量度。** 演演算法會持續對一個量度進行最佳化，該量度可以是轉換型或收入型（具體而言，每次造訪帶來&#x200B;**[!UICONTROL 收入]**）。
* **自動資料收集。** [!DNL Target]會自動收集關於訪客的資訊以建置個人化模型。 如需使用之引數的詳細資訊，請參閱[Automated Personalization資料彙集](/help/main/c-activities/t-automated-personalization/ap-data.md)。
* **共用對象。** [!DNL Target]會自動使用所有[!DNL Adobe Experience Cloud]個共用對象來建置個人化模型。 您不需要執行任何特定動作，即可將對象新增至模型。 如需將 [!DNL Experience Cloud Audiences] 用於 [!DNL Target] 的相關資訊，請參閱 [Experience Cloud 客群](/help/main/c-integrating-target-with-mac/mmp.md)。
* **自訂資料。** 行銷人員可以上傳離線資料、傾向分數或其他自訂資料，以建立個人化模型。 深入瞭解[上傳資料供自動鎖定目標和Automated Personalization](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)使用。

### 這兩種活動型別的差異 {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

當您想要定義整個體驗、使用整套&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)功能，或對您的頁面進行結構性變更時，請考慮&#x200B;**[!UICONTROL 自動鎖定目標]**，而非&#x200B;**[!UICONTROL Automated Personalization]**。

| | [!UICONTROL 自動鎖定目標] | [!UICONTROL 自動個人化] |
|---|---|---|
| **體驗定義** | 您可以定義包含多項變更的整個體驗。 | 個別選件會自動結合以形成體驗。 |
| **[!UICONTROL 視覺化體驗撰寫器]功能** | **[!UICONTROL 自動鎖定目標]**&#x200B;內嵌於A/B活動工作流程中，因此可享用更成熟且完整的VEC。 您也可以使用[QA連結](/help/main/c-activities/c-activity-qa/activity-qa.md)。 | 不支援自訂程式碼編輯器、多個體驗對象和其他功能。 |
| **頁面的結構變更** | 更合適。 例如，您可以重新排列首頁上的元素。 | 不太合適。 |
| **體驗數目** | 通常較少，因為一個體驗可以包含多項變更。 | 通常會更多，因為體驗是選件和位置的所有組合。 |
| **建立模型所需的流量** | 總數通常較少。 | 通常比較總計。 |

建立模型所需的每個體驗&#x200B;*流量*&#x200B;在兩個活動型別中都相同。 **[!UICONTROL 自動鎖定目標]**&#x200B;通常所需的總流量較少，因為它通常只有較少的體驗。

例如，在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中，每個位置有兩個選件，且有兩個位置，則該活動總共有四個(2 × 2 = 4)體驗（沒有排除專案）。 在&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;中，您可以將體驗1設為包含位置1的選件1和位置2的選件2，將體驗2設為包含位置1的選件2和位置2的選件1。 **[!UICONTROL 自動鎖定目標]**&#x200B;允許一個體驗中的多項變更，因此您可以減少活動中的體驗總數。

### [!UICONTROL 自動鎖定目標]的流量需求 {#traffic-requirements}

下列經驗法則有助於瞭解流量需求：

* **當[!UICONTROL 轉換]是您的成功量度時：** 1,000次造訪，每個體驗每天至少有50次轉換。 此外，活動必須有至少7,000次造訪和350次轉換。
* **當[!UICONTROL 每次造訪帶來的收入]是您的成功量度時：** 1,000次造訪，每個體驗每天至少有50次轉換。 此外，每個體驗至少必須有1,000次轉換。 **[!UICONTROL 每次造訪帶來的收入]**&#x200B;通常需要更多資料才能建立模型，因為造訪帶來的收入差異通常會高於轉換率。

**[!UICONTROL 自動鎖定目標]**&#x200B;也提供廣泛的線上測試架構。 多臂吃角子老虎機是大型線上測試架構的一部分，可讓[!DNL Adobe]位資料科學家和研究人員瞭解其在真實世界狀況中持續改善的好處。 未來，此測試台將允許[!DNL Adobe]向精通資料的使用者端開啟其機器學習平台，以便他們能夠引進自己的模型來擴充[!DNL Target]模型。

如需有關報告的詳細資訊，請參閱[報告和自動鎖定目標](/help/main/c-activities/auto-target/reporting-and-auto-target.md)。

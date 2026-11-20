---
keywords: 隨機森林；決策樹；ap；Automated Personalization
description: 瞭解[!DNL Adobe Target]如何在[!UICONTROL Automated Personalization] (AP)和[!UICONTROL 自動鎖定目標]活動中使用隨機森林演演算法。
title: '[!DNL Target]如何使用隨機森林演演算法？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: 07a89525-4071-4434-ac96-c59a4f4422ad
TQID: 'https://experienceleague.adobe.com/Ui8E8CkiiJSdqim9fzIgPDdsKG1MMtuu3EUuAqgmm0M'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 7eede3484d524e87127de9147aa786484fc87c7d
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 6%
---
# 隨機森林演算法 {#random-forest-algorithm}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解[!DNL Target]如何使用隨機森林演演算法來建置&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動的個人化模型。

>[!ENDSHADEBOX]

在&#x200B;**[!UICONTROL Automated Personalization]** (AP)和&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動中使用的主要個人化演演算法是隨機森林。 這是一種分類或回歸方法，在訓練時透過建構許多決策樹來運作。

隨機森林是一種組合方法。 在思考統計學時，您可能會想到使用單一迴歸模型來預測結果。 最新的資料科學研究表明，「整體方法」（即從相同的資料集建立多個模型，然後以智慧化方式結合）產生的結果會比僅根據單一模型預測更好，或比從任何組成部分的學習演演算法都好。

## 什麼是決策樹？ {#section_7F5865D8064447F4856FED426243FDAC}

決策樹將系統可學習的所有造訪資料劃分到不同的群組中。 在目標量度（例如轉換率）方面，每個群組內的造訪儘可能相似，而跨群組的造訪儘可能不同。 為了執行此操作，樹狀結構會檢視訓練集中的變數，並以互斥共同窮盡(MECE)方式將資料分割成群組（或「葉」），以最大化此目標。

在以下簡單範例中，目標量度為轉換，且有兩個輸入變數：

* 性別 (兩個可能值: 男或女)
* 郵遞區號（小型資料集中可能有五個值：11111、22222、33333、44444或55555）

### 第一次分割 {#first-split}

樹狀結構會先決定兩個變數中的哪一個可解釋造訪資料轉換率的最大變數。 假設郵遞區號是最具預測性的。 此變數會形成樹狀結構的第一個「分支」。 然後樹狀結構會將造訪資料分割成群組，如上所述。 假設11111、22222和33333為一次分割，而44444和55555為第二次分割。

![決策樹的第一層](assets/decsion_tree_1.png){width="440" align="center"}

### 在每個分支內分割 {#second-split}

樹狀結構會提出問題，「最能預測的變數為何？」 再次進行，並完成類似的練習，在每個分支&#x200B;*中分割資料*。 現在只保留性別，所以這就是答案。 在11111、22222和33333分支中，假設男性和女性之間的轉換存在差異。 然後有兩個葉子（男性和女性），此分支完成。 在44444和55555分支中，假設女性和男性的轉換方式沒有統計上的差異。 在這種情況下，第一個分割是最終分割。

![完成決策樹](assets/decsion_tree_2.png){width="480" align="center"}

## 隨機森林如何使用決策樹？ {#section_536C105EF9F540C096D60450CAC6F627}

決策樹是一種有用的統計工具。 但有一些缺點。 最關鍵的是，它們可能「過度調整」資料，使得個別樹狀結構無法正確預測未來不用於建置初始樹狀結構的資料。 在統計學習中，此難題稱為[偏誤及變數之權衡](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff)

隨機森林有助於克服這個挑戰。 隨機森林是數百個決策樹的集合，這些決策樹是根據相同資料集以稍微不同的方式建置，而且這些「投票」一起產生比個別樹更好的模型。 這些樹狀結構是透過隨機選取具有取代的造訪記錄子集（稱為標籤）並隨機選取屬性子集來建置，因此樹狀結構是由稍微不同的決策樹組成。 此方法會將小變數引進樹狀結構中。 新增此受控量的變異數有助於改善演演算法的預測準確度。

## [!DNL Target]個人化演演算法如何使用隨機森林？ {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

### 如何建立模型

[!DNL Target]會使用自動收集的資料，以及您提供的自訂資料，來建置其個人化演演算法。 下列圖表總結如何建立&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動的模型：

![概述如何建立隨機森林模型的流量](assets/random_forest_flow.png){width="850" zoomable="yes"}

1. [!DNL Target]會收集訪客的資料，同時隨機提供體驗或選件。
1. 在[!DNL Target]點選關鍵數量的資料後，[!DNL Target]會執行功能工程。
1. [!DNL Target]會為每個體驗或選件建置隨機森林模型。
1. [!DNL Target]會檢查模型是否符合臨界值品質分數，以驗證模型。
1. [!DNL Target]將模型推送至生產環境，以便個人化未來的流量。

這些模型會預測最佳體驗或產品建議來顯示給訪客。 一般而言，每個體驗（在&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動中）或每個選件（在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中）都會建立一個模型。 [!DNL Target]接著會顯示產生最高預測成功量度（例如轉換率）的體驗或選件。 模型必須先接受隨機提供造訪的訓練，才能用於預測。 因此，在活動首次啟動時，即使個人化群組中的訪客也會隨機顯示不同的體驗或選件，直到個人化演演算法就緒為止。

模型會根據曲線下方的區域(AUC)進行驗證，以確保每個模型都能在活動中使用之前很好地預測訪客的行為。 模型開始提供個人化體驗的確切時間取決於資料的詳細資訊，因為必須先驗證模型。 在實務上及流量規劃用途上，每個模型通常要超過最低轉換次數才有效。

當模型變得對體驗或選件有效時，體驗或選件名稱左側的時鐘圖示會變更為綠色核取方塊。 當有至少兩種體驗或選件的有效模型時，部分造訪會開始變成個人化。

### 特徵轉換

在資料通過個人化演演算法之前，它會進行功能轉換，這可以視為準備在訓練記錄中收集的資料以供個人化模型使用。 轉換取決於屬性型別（或資料科學家有時會描述的「特徵」）：

| 功能類型 | 說明 | 轉換 |
|---|---|---|
| **類別** | 無法計數，但可分類為不同群組，例如國家/地區、性別或郵遞區號。 | 會維護一組所有可能的功能，並使用可能性轉換來減少資料大小。 |
| **數值** | 可以測量或計數，例如年齡或收入。 | 重新縮放可確保這些特徵在整體上可互相比較。 |

### 採用多臂吃角子老虎機來平衡學習與個人化

在[!DNL Target]建立個人化模型後，您未來需要權衡活動的訪客。 您可以根據目前模型來個人化所有流量，或是透過隨機提供選件繼續向新訪客學習。 個人化演演算法永遠都應該瞭解訪客的新趨勢，同時將大部分的流量個人化。 多臂吃角子老虎機是[!DNL Target]達成此目標的方式：它可確保模型一律「花費」一小部分的流量，在整個活動期間繼續學習，並防止過度利用先前學習到的趨勢。

在資料科學世界中，多臂強盜問題是探索與開發困境的經典範例，在此範例中，一組單臂強盜各自具有未知的獎勵概率。 關鍵想法是開發一種策略，使得成功機率最高的手臂得到播放，從而使獲得的總獎勵最大化。 在建立線上模型後，系統中會使用多臂吃角子老虎機進行線上評分。 此程式有助於在探索期間進行線上學習。 目前的多臂演演算法是epsilon (ε)貪婪演演算法。 在這個演演算法中，如果機率為1 - ε，則選擇最佳手臂。 在機率ε的情況下，會隨機選擇任何其他手臂。

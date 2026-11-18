---
keywords: 多變數測試；mvt；全階乘；mvt或a/b；多變數a/b；流量估算；何時使用mvt；mvt考量；多變數；部分階乘；部分階乘；全階乘
description: 瞭解如何在[!DNL Adobe Target]中使用[!UICONTROL 多變數測試] (MVT)來比較頁面上元素中的選件組合，以判斷哪個組合表現最好。
title: 什麼是[!UICONTROL 多變數測試]？
feature: Multivariate Tests
exl-id: c8b60011-cb3a-4e28-b84f-06910687b14b
TQID: 'https://experienceleague.adobe.com/JKmjIHJuRxAXlhvUOrrmLMVLnJFhA3T4xkahgH-ozHE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '1382'
ht-degree: 24%
---
# 開始使用[!UICONTROL 多變數測試] {#get-started-mvt}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解&#x200B;**[!UICONTROL 多變數測試]**&#x200B;如何運作、哪些辭彙[!DNL Target]使用它、何時使用它而非A/B測試，以及部分階乘測試如何減少流量需求。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的&#x200B;**[!UICONTROL 多變數測試]** (MVT)活動會比較頁面上元素中選件的組合，以判斷哪個組合對特定對象執行時效果最佳。 它還有助於識別哪個元素最能影響活動的成功。 多變數測試可協助您發現特定元素與頁面上的其他元素相比，對轉換的相對影響，並可協助您調整已證明有效的元素組合。

與A/B測試相比，**[!UICONTROL 多變數測試]**&#x200B;有兩個優點：

* 它會顯示頁面上的哪些元素對轉換有最大影響，也稱為「主要效果」。 例如，這項資訊可協助您決定要將內容放在何處以獲得最多關注。
* 它有助於您在頁面上找到兩個或多個元素之間的複合效果，也稱為「互動效果」。 例如，特定廣告結合特定橫幅或主圖時，可能產生更多轉換。

[!DNL Target] 採用全階乘多變數測試，協助您將內容最佳化。 全階乘多變數測試會以相同機率檢查所有可能的內容組合。 例如，假設您的兩個頁面元素各有三個產品建議，總共有九種可能的組合 (3x3)。 在三個元素中，有兩個包含三個可能的產品建議，有一個有兩個產品建議，總共有 18 種選項 (3x3x2)。

在[!DNL Target]中，每個組合都是一個體驗。 **[!UICONTROL 多變數測試]**&#x200B;會比較每個體驗，讓您瞭解哪些組合最成功。 同時，[!DNL Target]會收集和分析資料，以瞭解每個位置和選件如何影響成功量度。

![多變數測試組合](assets/multivariate.png)

由於可產生的組合數目，**[!UICONTROL 多變數測試]**&#x200B;比A/B測試需要更多時間和流量。 頁面必須接收足夠的流量，才能為每一個體驗產生統計顯著的結果。 若要獲得有用的結果，請瞭解您的頁面收到的流量量，並測試適當時間量的最佳組合數量。

[流量估算程式](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#traffic-estimator)可協助您設計適用於流量的測試。 使用前，您應先具備良好的統計資料，顯示網站一般會收到的曝光次數和轉換次數，並考量您每日的流量層級。 活動擁有的體驗越多，活動必須包含的流量就越多，或必須執行的時間越長。 如果您的流量量不高，請測試幾個組合。 否則，產生有意義的測試結果所需的時間可能太長，以致於沒有用處。

## MVT術語 {#mvt-terminology}

業界以不同方式使用數個術語。 下表定義當您設定多變數測試時，[!DNL Target]使用的術語。

| 術語 | 定義 |
|--- |--- |
| 組合 | 在多個位置中測試多個內容選項時所建立的內容變異。 例如，如果您要測試三個位置，每個都有三個內容選項，則有27個可能的組合(3x3x3)。 您的網站訪客看到一個組合，也稱為體驗。 |
| 內容 | 構成某個位置內測試變數的文字或影像。 在多變數測試中，會比較多個位置中的數個內容選項。 在 MVT 方法中，有時會將內容稱為&#x200B;*等級*。 |
| 元素 | 包含要在MVT測試中測試之內容變異的DOM元素。 另請參閱&#x200B;*位置*。 |
| 位置 | 頁面上的特定內容區域，經常包含單一 DOM 元素。 在 MVT 方法中，有時會將位置稱為&#x200B;*係數*。 全階乘多變數測試會比較您的位置中所有可能的產品建議組合。 |

## 何時使用[!UICONTROL 多變數測試]與A/B {#when-to-use-mvt}

下表顯示何時使用&#x200B;**[!UICONTROL 多變數測試]**、A/B測試，或兩者搭配使用來最佳化您的頁面。

| 情況 | 該做什麼 | 詳細資料 |
|--- |--- |--- |
| 您要測試的元素少於三個。 | 執行一系列A/B測試。 | 在至少有三個元素要測試時，才使用 MVT 測試。 |
| 您想要同時最佳化頁面的版面和內容。 | 使用A/B測試來最佳化您的頁面配置，接著使用MVT測試來決定頁面上每個元素中的最佳內容。 | A/B測試可以提供版面配置方面的重要意見，而MVT測試擅長於測試頁面設計中元素內的內容。 在測試多個內容選項之前對版面配置執行A/B測試可協助您決定最佳版面配置和最具影響力的內容。 |
| 不同體驗的數量超過五個，並跨越兩個或更多元素。 | 使用 MVT 測試來判斷最重要的元素，接著對該元素進行更聚焦的 A/B 測試。 | MVT 測試會顯示頁面上的哪些區域最可能改善轉換。 這些是市場行銷人員應該專注的元素。 例如，MVT 測試可能指出呼叫動作是達成目標最重要的元素。 您可以接著執行A/B測試來進一步調整結果，例如測試兩個特定影像之間的差異，或比較call to action的用語或顏色。 透過遵循包含一或多個A/B測試的MVT測試，您可以為想要的結果決定最佳內容。 |

如需更多考量事項，例如要包含多少元素以及如何規劃測試，請參閱[多變數測試最佳作法](/help/main/c-activities/c-multivariate-testing/best-practices.md)。

## 部分因子測試 {#partial-factorial}

[!DNL Target] 提供全階乘多變數測試當作內建活動選項。 在統計資料中，「實驗設計」提供許多方法（或設計）來判斷會影響結果的因素。 其中一種方法是用於部分因子測試的[田口方法](https://en.wikipedia.org/wiki/Taguchi_methods)。 「田口方法」可讓行銷人員建立一組假設，以減少必須測試的體驗排列，進而減少多變數測試的流量需求。 您可以使用此[離線試算表](/help/main/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx)，在[!DNL Target]中套用此方法。

如果您的團隊使用其他實驗設計方式，您可以將試算表作為自訂實驗設計的參考實作。

使用離線計算試算表時，請考量下列訣竅:

* 挑選您要變更的元素和每個元素的版本編號（3x2、4x3等）。
* 保持編號一致。 例如，假設按鈕是元素 1，選項為藍色、綠色和黃色，則藍色按鈕為 1-1、綠色按鈕為 1-2、黃色按鈕為 1-3。
* 離線試算表可提供適合所需的體驗數目 (3x2 四個、4x3 九個...等等)。
* 使用[可視化體驗撰寫器 (VEC)](/help/main/c-experiences/experiences.md) 在 A/B 工作流程中建立體驗。 您可以使用自訂程式碼、編輯 HTML、WYSIWYG 或任何組合。
* 活動結束後（根據樣本大小電腦），透過試算表執行結果以取得其他詳細資訊。

## 培訓影片 {#training-videos}

以下影片包含有關本頁探討之概念的詳細資訊。

### 活動型別(9:03) ![Overview badge](/help/main/assets/overview.png)

此概觀影片說明[!DNL Target]中可用的活動型別。 4:20 開始討論多變數測試。 在本影片中，您將瞭解如何：

* 說明[!DNL Adobe Target]中包含的活動型別。
* 選取適當的活動型別以實現您的目標。
* 說明適用於所有活動型別的三步驟引導式工作流程。

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### 正在建立多變數測試(9:25) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片說明如何使用[!DNL Target]三步驟引導式工作流程來瞭解、規劃和建立多變數測試。 在本影片中，您將瞭解如何：

* 定義及設計多變數測試。
* 建立多變數測試。

>[!VIDEO](https://video.tv.adobe.com/v/17395)

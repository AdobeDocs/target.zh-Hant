---
keywords: 報表;下載報表;csv;成功量度;訂單詳細資料
description: 瞭解如何以CVS格式從Adobe [!DNL Target] 活動下載資料，以快速匯入至Excel、Access或其他資料分析程式。
title: 如何下載CSV檔案的報表資料？
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: c0342f51d998d27eef9af189c7ebb364095699ed
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 30%

---

# 將資料下載為 CSV 檔案

下載.csv格式的資料，以快速匯入至[!DNL Excel]、[!DNL Access]或其他資料分析程式。

若要下載 CSV 檔案中的資料:

1. 按一下 **[!UICONTROL Activities]**，然後從清單按一下需要的活動。

   如果您有許多活動，請按一下篩選器（ ![篩選器圖示](/help/main/assets/icons/Filter.svg) ）圖示，以從[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]和[!UICONTROL Activity Source]下拉式清單中選取選項來篩選清單。

1. 按一下「**[!UICONTROL Reports]**」標籤。
1. 按一下「**[!UICONTROL Download]**」（「![下載」圖示](/help/main/assets/icons/Download.svg)）圖示，然後選取要下載到Excel和其他工具中分析的報表型別。

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

## [!UICONTROL Export Report to CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

[!UICONTROL Success Metrics]報表顯示成功量度的相關資訊，以及[!DNL Target] UI中未提供的下列量度：

* 平均轉換時間以小時計，這樣您就可以看到一般訪客到達轉換點所花的時間
* 離線統計信賴計算的收入總和平方

活動結束時才會儲存資料。

>[!NOTE]
>
>CSV報表只包含原始資料，不含計算量度，例如每次造訪帶來的收入、提升度或用於A/B測試的信賴度。 若要計算這些計算的量度，請下載[!DNL Target] [完整可信度電腦](/help/main/assets/complete_confidence_calculator.xlsx) Excel檔案以輸入活動的值，或檢閱A/Bn測試中的[統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)。

## [!UICONTROL Export Order Details to CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

[!UICONTROL Order Details]報表顯示訂單的相關資訊，包括：

* 訂單日期與時間
* 訂單金額 (若您插入「下單」mbox)

  [!UICONTROL Order Details]報表只有在您有訂單時才有作用。

* 訂單標幟 (重複或巨量訂購)

  如果訂單與平均訂單值之間的標準差超過+/- 3個標準差，則會將訂單標籤為極端。 此計算使用資料的最後一個月（截至計算的時間點）。 一旦活動執行超過一小時或直到 15 筆訂單之後 (以先到者為準)，活動便會排除其極端訂單。如需詳細資訊，請參閱[排除極端訂單](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)。

* 產品 ID

  產品ID的總長度若以逗號串連，不應超過255個字元，或ID未在報表中正確顯示。 例如，如果您的訂單中的產品 ID 為「aa, bb」，則總長度為「aa,bb」= 5。

* 體驗

  在[!UICONTROL Order Details]、[!UICONTROL A/B Test] (XT)和[!UICONTROL Experience Targeting] (MVT)活動的[!UICONTROL Multivariate Test]報表中，[!UICONTROL Experience]欄包含體驗`localId`。 這是從產品建議 Token 中的 `$campaign.recipe.id` 輸出的值。

  [!UICONTROL Experience] (AP)活動沒有[!UICONTROL Automated Personalization]欄。 目前的[!UICONTROL Algorithm Name]欄已取代為「控制」與「已鎖定目標」術語，如[!DNL Target]的其他部分所示。

  對[!UICONTROL Recommendations]活動沒有影響。

>[!NOTE]
>
>* 對於預設環境 (主機群組)，訂單報表資料包含四週的資料，而對於所有非預設環境，則包含兩週的資料。
>* 針對相同訪客下第一個訂單，將收入量度設為&quot;[!UICONTROL Increment count and keep the user in the activity]&quot;記錄訂單詳細資料。 所有後續訂單都會增加轉換計數，但不會將收入新增至RPV/AOV/銷售，並且不會包含在[!UICONTROL Order Details]報表中。

## 熱門程度的CSV下載格式和基於金鑰的演演算法 {#format}

CSV下載檔案會一致地反映後端條件執行後產生的結果。

**若是熱門演演算法（非金鑰型），檔案包含：**

* 前置詞為*的備份建議列
* 根據演演算法設定列出建議的獨立列

**對於金鑰式演演算法，檔案包含：**

* 與熱門程度演演算法類似的備份列
* 鍵值格式的多列，其中第一個專案是鍵的產品ID，後面是代表建議候選人的逗號分隔產品ID

## 最佳實務

* 若要記錄訂單記錄，必須傳遞`orderTotal`引數。
* 透過`ProductPurchasedId` mbox引數傳遞的值列在[!UICONTROL Order Details]報表中。
* 最佳作法是包含`orderID`和`orderTotal`。 這樣可以自動忽略重複的訂單。

## 注意事項 {#section_49B9590904A645B18E694B4EFFFC1DEF}

下列資訊適用於[!UICONTROL Download]選項：

* 您可以下載[!UICONTROL A/B Test]、[!UICONTROL Automated Personalization]、[!UICONTROL Experience Targeting]和[!UICONTROL Multivariate]活動的兩個報告。 您無法下載[!UICONTROL Success Metrics]活動的[!UICONTROL Recommendations]報告。
* [!UICONTROL Download]選項不適用於[!UICONTROL A/B Test]版本15.7.1 （2015年7月）之前建立的[!UICONTROL Experience Targeting]和[!DNL Target]活動。
* 下載的報表中不會記錄沒有相關聯資料的體驗。
* 在[!DNL Target]報表UI中套用的對象不會繼續存在於下載報表中。
* 如果活動使用多個量度，則為下載所產生的 .csv 報告會不一致。可下載的報表只會根據報表設定產生，且會針對使用的任何其他量度考慮相同的值。 真相來源永遠是在 [!DNL Target] UI 中顯示的報告。

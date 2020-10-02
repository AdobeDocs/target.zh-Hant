---
keywords: Target;reports;report settings;environment;lift;lift bound;variance;confidence;control
description: 報表包含數個資料點和視覺化呈現，可協助您瞭解與Adobe Target活動相關的提升度界限和信賴等級，以協助您更精確地判斷成功者。
title: 平均提升度、提升度界限和信賴區間
feature: report settings
uuid: 2899503a-d81e-4dc3-b258-a5ecafd1d1a4
translation-type: tm+mt
source-git-commit: 1433de7270f400ec21c4f506cdc6dee8bcaa550f
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 73%

---


# 平均提升度、提升度界限和信賴區間

報表包含數個資料點和視覺化表示，可協助您瞭解與活動相關的提升度界限和信賴等級， [!DNL Adobe Target] 以協助您更精確地判斷成功者。

>[!NOTE]
>
>This feature is available only when viewing reports in [!UICONTROL Table] View. 此功能無法供以[ Analytics 作為報表來源 (A4T)](../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) 的活動使用。

## 解譯資料 {#section_62C0D7E76F3D49A7B3C371C82AEF27D5}

The following illustration shows [!UICONTROL Lift Bounds and Confidence Level] information:

![平均提升度和可信度等級報表](/help/c-reports/c-report-settings/assets/lift-screenshot-new.png)

The lift and confidence information in the [!DNL Target] reporting UI includes:

### 提升度

大的數字和箭頭反映提升度的期望值。此數字是提升度界限範圍的中點。期望的提升度箭頭以灰色顯示，直到可信度超過 95% 為止。超過此臨界值之後，箭頭會顯示為紅色或綠色，分別根據負提升或正提升而定。

### 提升度範圍

這是提升度的 95% 信賴區間。顯示成一個低於平均提升度的範圍。See [Example calculation](#example) below for an example of how these lift bounds are calculated.

### 包裝盒圖

The boxplot graph in the [!DNL Target] interface represents the expected value and 95% confidence interval of the success metric in question. 可視為以圖形來檢視提升度和提升度界限資訊。

There are a few key ways [!DNL Target] helps you interpret the confidence information, one of which is color. 圖形以灰色顯示特定體驗與控制體驗的信賴區間中的任何重疊，特定體驗的信賴區間若有任何範圍高於或低於控制信賴區的範圍，則分別以綠色或紅色顯示。

盒形圖長度以簡單明瞭的方式表示信賴區間的大小。隨著您在活動中收集越多資料，直條會位移動和變更。信賴區間衍生自變數和樣本大小 (訪客數)。變數越小和樣本大小越大，信賴間區就越窄。

### 可信度

體驗或選件的可信度代表相關聯體驗/選件在控制體驗/選件上的提升度為「真實」(不是隨機造成) 的機率。通常，建議達到 95% 的信賴水準，才將提升度視為顯著。

## How are lift bounds calculated? {#section_1D360781D972483693680BE0F07AEAD1}

提升度界限代表特定體驗或選件的提升度超過控制體驗或選件的 95% 信賴區間。籠統來說，即實際提升度大約有 95% 的機會落在這些界限之間。

提升度界限是利用下列公式計算:

![](assets/lift_diagram.png)

輸入我們的提升度界限時還會做一些其他計算:

* **t 值:** 95% 信賴水準的臨界統計量是 1.96。您可以在[此處](https://en.wikipedia.org/wiki/T-statistic)進一步瞭解 t 值。
* **提升度變異數:**&#x200B;需要體驗 N 成功量度的標準誤差和控制體驗成功量度的標準誤差，才能判斷使用下列公式計算的提升度變異數 (圖例中的成功量度為轉換)。

   ![](assets/lift_variance.png)

* **轉換率/成功量度標準誤差:**&#x200B;體驗 N 和控制體驗以相同方式計算標準誤差，採用下列公式 (圖例中的成功 度是轉換)。您可以在[此處](https://en.wikipedia.org/wiki/Standard_error)進一步瞭解標準誤差。

   ![](assets/standard_error.png)

   >[!NOTE]
   >
   >收入成功量度活動的條件誤差是根據收入的樣本變數。

## Example calculation {#example}

假設範例活動有兩個體驗和下列結果:

| 體驗 | 訪客 | 轉換 | 轉換率 |
|--- |--- |--- |--- |
| 體驗 A (控制) | 219, 328 | 2,466 | 1.12% |
| 體驗 B | 218, 362 | 3,040 | 1.39% |

根據公式，我們可以計算提升度界限所需的輸入。

**體驗 A (控制) 的標準誤差**

![](assets/standard_error_A.png)

**體驗 B 的標準誤差**

![](assets/standard_error_B.png)

**體驗 B 的提升度變數**

![](assets/lift_variance_B.png)

**體驗 B 的提升度界限**

體驗 B 的期望提升度:

![](assets/lift_bounds_B.png)

因此，體驗 B 的提升度界限是:

![](assets/lift_bounds_B2.png)

>[!NOTE]
>
>若使用上述報表中顯示的公式與數字進行手動計算，可能會出現些微差異。此差異可歸因於手動計算中使用的頁面檢視數字為四捨五入。The lift shown in the [!DNL Target] report is based on the exact numbers obtained from the total engagement and the engagement count. 此參與數字可透過效能報表 API 取得。

## When Are lift bounds not displayed? {#section_C5622E1E94684DAD937249B51A9E42CC}

In certain cases, [!DNL Target] does not display lift bounds:

* 在任何活動中，當造訪或訪客總數少於 30 時。
* For [!UICONTROL Auto-Allocate] activities, no lift bounds are displayed until one experience has attained 60% confidence.

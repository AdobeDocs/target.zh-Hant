---
keywords: Target;報表;報表設定;環境;提升度;提升度界限;變異數;可信度;控制
description: 了解如何解讀Adobe [!DNL Target] 報表，包括資料點和視覺效果表示，協助您了解活動的提升度界限和信賴等級。
title: 如何檢視平均提升度、提升度界限和信賴區間？
feature: Reports
exl-id: 0453aec1-cca5-462c-8eed-0d40bb4cf323
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 60%

---

# 平均提升度、提升度界限和信賴區間

報表包含數個資料點和視覺效果表示法，可協助您了解與您的 [!DNL Adobe Target] 活動可協助您更精確地判斷獲勝者。

>[!NOTE]
>
>此功能僅在 [!UICONTROL 表格] 檢視。 此功能無法供以[ Analytics 作為報表來源 (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) 的活動使用。

## 解譯資料 {#section_62C0D7E76F3D49A7B3C371C82AEF27D5}

下圖顯示 [!UICONTROL 提升度界限和信賴等級] 資訊：

![平均提升度和可信度等級報表](/help/main/c-reports/c-report-settings/assets/lift-screenshot-new.png)

中的提升度和信賴資訊 [!DNL Target] 報表UI包括：

### 提升度

大的數字和箭頭反映提升度的期望值。此數字是提升度界限範圍的中點。期望的提升度箭頭以灰色顯示，直到可信度超過 95% 為止。超過此臨界值之後，箭頭會顯示為紅色或綠色，分別根據負提升或正提升而定。

### 提升度界限

這是提升度的 95% 信賴區間。顯示成一個低於平均提升度的範圍。請參閱 [計算範例](#example) 以下是如何計算這些提升度界限的範例。

### 盒形圖

中的盒形圖 [!DNL Target] 介面代表相關成功量度的預期值和95%信賴區間。 可視為以圖形來檢視提升度和提升度界限資訊。

有幾種關鍵方法 [!DNL Target] 可協助您解讀可信度資訊，其中一項是顏色。 圖形以灰色顯示特定體驗與控制體驗的信賴區間中的任何重疊，特定體驗的信賴區間若有任何範圍高於或低於控制信賴區的範圍，則分別以綠色或紅色顯示。

盒形圖長度以簡單明瞭的方式表示信賴區間的大小。隨著您在活動中收集越多資料，直條會位移動和變更。信賴區間衍生自變數和樣本大小 (訪客數)。變數越小和樣本大小越大，信賴間區就越窄。

### 可信度

顯示的體驗或選件的信賴度是取得結果的機率（以百分比表示） _極端_ 比被觀察到的要多， _如果null假設為true_，即該體驗或選件與控制體驗/選件之間的轉換率沒有差異。 就p值而言，顯示的信賴度為 `1 - p-value`. 更簡單地說，信賴度較高表示資料與控制項和非控制項選件/體驗具有相同轉換率的假設不一致。

## 了解如何判斷提升度的信賴區間 {#pdf}

下載 [提升度pdf檔案的信賴區間](/help/main/assets/confidence_interval_lift.pdf) 以取得更多資訊。

## 如何計算提升度界限？ {#section_1D360781D972483693680BE0F07AEAD1}

提升度界限代表特定體驗或選件的提升度超過控制體驗或選件的 95% 信賴區間。籠統來說，即實際提升度大約有 95% 的機會落在這些界限之間。

提升度界限是利用下列公式計算:

![lift_diagram影像](assets/lift_diagram.png)

輸入我們的提升度界限時還會做一些其他計算:

* **t 值:** 95% 信賴水準的臨界統計量是 1.96。您可以在[此處](https://en.wikipedia.org/wiki/T-statistic)進一步瞭解 t 值。
* **提升度變異數:**&#x200B;需要體驗 N 成功量度的標準誤差和控制體驗成功量度的標準誤差，才能判斷使用下列公式計算的提升度變異數 (圖例中的成功量度為轉換)。

   ![lift_variance影像](assets/lift_variance.png)

* **轉換率/成功量度標準誤差:**&#x200B;體驗 N 和控制體驗以相同方式計算標準誤差，採用下列公式 (圖例中的成功 度是轉換)。您可以在[此處](https://en.wikipedia.org/wiki/Standard_error)進一步瞭解標準誤差。

   ![standard_error影像](assets/standard_error.png)

   >[!NOTE]
   >
   >收入成功量度活動的條件誤差是根據收入的樣本變數。

## 計算範例 {#example}

假設範例活動有兩個體驗和下列結果:

| 體驗 | 訪客 | 轉換 | 轉換率 |
|--- |--- |--- |--- |
| 體驗 A (控制) | 219, 328 | 2,466 | 1.12% |
| 體驗 B | 218, 362 | 3,040 | 1.39% |

根據公式，我們可以計算提升度界限所需的輸入。

**體驗 A (控制) 的標準誤差**

![standard_error_A影像](assets/standard_error_A.png)

**體驗 B 的標準誤差**

![standard_error_B影像](assets/standard_error_B.png)

**體驗 B 的提升度變數**

![lift_variance_B影像](assets/lift_variance_B.png)

**體驗 B 的提升度界限**

體驗 B 的期望提升度:

![lift_bounds_B影像](assets/lift_bounds_B.png)

因此，體驗 B 的提升度界限是:

![lift_bounds_B2影像](assets/lift_bounds_B2.png)

>[!NOTE]
>
>若使用上述報表中顯示的公式與數字進行手動計算，可能會出現些微差異。此差異可歸因於手動計算中使用的頁面檢視數字為四捨五入。顯示於 [!DNL Target] 報表是根據從參與總計和參與計數中取得的確切數字。 此參與數字可透過效能報表 API 取得。

## 何時不顯示提升度界限？ {#section_C5622E1E94684DAD937249B51A9E42CC}

在某些情況下， [!DNL Target] 不顯示提升度界限：

* 在任何活動中，當造訪或訪客總數少於 30 時。
* 針對 [!UICONTROL 自動分配] 活動中，只有在某個體驗達到60%信賴度時，才會顯示提升度界限。

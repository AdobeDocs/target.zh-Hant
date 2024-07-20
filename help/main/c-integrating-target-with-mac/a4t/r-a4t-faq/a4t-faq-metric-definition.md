---
keywords: faq;常見問題集;analytics for target;a4T;量度;量度定義
description: 尋找關於量度定義和對 [!DNL Target] (A4T)使用Analytics問題的解答。 A4T可讓您將Analytics報表用於Adobe [!DNL Target] 活動。
title: 我可以在哪裡找到有關A4T量度定義的資訊？
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 31%

---

# 量度定義 - A4T 常見問題集

此主題包含經常詢問關於量度定義和使用[!DNL Adobe Analytics]做為[!DNL Adobe Target] (A4T)報表來源問題的回答。

## 活動成員資格多久到期? 訪客進入活動後，如果不再看此活動，則其動作經過多久會計入此活動中？ {#section_41B4958F33534E4B96DEE0C981227A79}

+++回答
活動的預設有效期為訪客上次與活動互動後的90天。 如有需要，ClientCare可調整此設定。 不過，此設定全域適用所有活動，因此不應針對一個案例進行調整。

+++

## 在設定目標量度時，為何無法存取進階設定選項？ {#adv-settings}

+++回答
[!UICONTROL Advanced Settings]選項不適用於使用[!DNL Analytics]做為報告來源(A4T)的活動。

對於使用A4T的活動，目標量度一律使用&quot;[!UICONTROL Increment Count & Keep User in Activity]&quot;和&quot;[!UICONTROL On Every Impression]&quot;設定。 這些設定是&#x200B;*不可設定的*。

對於非A4T活動，您可以使用[進階設定選項](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B)來管理您測量成功的方式。 選項包括新增相依性、選擇讓使用者留在活動還是移除活動，以及是否對每個加入者或每次曝光都計算一次量度。 您可以按一下垂直的點> [!UICONTROL Advanced Settings]，存取非A4T活動中的[!UICONTROL Advanced Settings]選項，如下所示：

![進階設定](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## 什麼是計算量度，它們如何取代我過去常用的 SiteCatalyst:Event Mbox? {#section_D59F4719E6B94758A2187427C17F8EF3}

+++回答
計算量度可讓您建立衍生自區段或數學計算的自訂量度。 您過去可能已使用 `SiteCatlayst:Event` mbox (其中 `evar27=shoes` 且事件為 `purchase`)，而現在您要建立 `evar27=shoes` 的區段，然後建立事件為 `purchase` 並套用該區段的計算量度。這些量度可隨時建立，即便活動正在進行中也一樣。 然後可用於 Analytics 中的任何報表。

+++

## A4T 會將轉換歸因於多個行銷活動嗎? {#section_7F15C727206440CD86B3A8CE77087DF9}

+++回答
是，使用「完整配置」設定。

+++
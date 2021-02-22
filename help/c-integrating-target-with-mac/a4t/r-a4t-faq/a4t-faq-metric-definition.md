---
keywords: faq;常見問題集;analytics for target;a4T;量度;量度定義
description: 尋找有關量度定義和使用Analytics for Target(A4T)的問題解答。 A4T可讓您將Analytics報表與Adobe Target活動搭配使用。
title: 我可以在哪裡找到有關A4T量度定義的資訊？
feature: 目標分析 (A4T)
translation-type: tm+mt
source-git-commit: 418a178aea06e29a1886cf77cb32fde2b8dcb9df
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 58%

---


# 量度定義 - A4T 常見問題集

此主題包含經常詢問關於量度定義和使用 Analytics 做為 Target 報表來源 (A4T) 問題的回答。

## 活動成員資格多久到期? 訪客進入活動後，如果不再看此活動，則其動作經過多久會計入此活動中? {#section_41B4958F33534E4B96DEE0C981227A79}

活動的預設到期是在訪客最後一次與活動互動的 90 天之後。必要時可由 ClientCare 調整。不過，此設定全域適用所有活動，因此不應針對一個案例進行調整。

## 在設定目標量度時，為什麼無法存取「進階設定」選項？{#adv-settings}

[!UICONTROL 進階設定]選項不適用於使用[!DNL Analytics]作為報告來源(A4T)的活動。

對於使用A4T的活動，目標量度一律會使用「[!UICONTROL 活動中增量計數與保留使用者」和「每次曝光時]」設定。 ][!UICONTROL 這是&#x200B;*not*&#x200B;可配置的。

對於非A4T活動，您可使用[進階設定選項](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B)來管理測量成功的方式。 選項包括新增相依性、選擇是否讓使用者留在活動中或移除它們，以及是否對每個參與者或每個曝光計算一次量度。 通過按一下垂直橢圓狀圖> [!UICONTROL 高級設定]來訪問非A4T活動中的[!UICONTROL 高級設定]選項，如下所示：

![進階設定](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## 什麼是計算量度，它們如何取代我過去常用的 SiteCatalyst:Event Mbox?  {#section_D59F4719E6B94758A2187427C17F8EF3}

計算量度可讓您建立衍生自區段或數學計算的自訂量度。您過去可能已使用 `SiteCatlayst:Event` mbox (其中 `evar27=shoes` 且事件為 `purchase`)，而現在您要建立 `evar27=shoes` 的區段，然後建立事件為 `purchase` 並套用該區段的計算量度。好處是即使活動在進行中，仍可隨時建立這些量度。然後可用於 Analytics 中的任何報表。

## A4T 會將轉換歸因於多個行銷活動嗎?  {#section_7F15C727206440CD86B3A8CE77087DF9}

是。這是利用「完整分配」設定來完成。

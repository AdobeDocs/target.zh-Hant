---
keywords: faq;常見問題集;analytics for target;a4T;量度;量度定義
description: 尋找有關量度定義和使用Analytics處理 [!DNL Target] (A4T). A4T lets you use Analytics reporting with Adobe [!DNL Target] 活動的問題解答。
title: 我可以在哪裡找到有關A4T量度定義的資訊？
feature: 目標分析 (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 40%

---

# 量度定義 - A4T 常見問題集

本主題包含有關量度定義的常見問題解答，並使用[!DNL Adobe Analytics]作為[!DNL Adobe Target](A4T)的報表來源。

## 活動成員資格多久到期? 訪客進入活動後，如果再未看見活動，其動作會計入活動多久？{#section_41B4958F33534E4B96DEE0C981227A79}

活動的預設到期是在訪客最後一次與活動互動的 90 天之後。如有需要，ClientCare可調整此設定。 不過，此設定全域適用所有活動，因此不應針對一個案例進行調整。

## 在設定目標量度時，為什麼無法存取「進階設定」選項？{#adv-settings}

[!UICONTROL 進階設定]選項不適用於使用[!DNL Analytics]作為報告來源(A4T)的活動。

對於使用A4T的活動，目標量度一律會使用「[!UICONTROL 在活動中增加計數並保留使用者」和「[!UICONTROL 在每次曝光時]」設定。 ]這些設定是&#x200B;*not*&#x200B;可設定的。

對於非A4T活動，您可使用[進階設定選項](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B)來管理測量成功的方式。 選項包括新增相依性、選擇是否讓使用者留在活動中或移除它們，以及是否對每個參與者或每個曝光計算一次量度。 通過按一下垂直橢圓狀圖> [!UICONTROL 高級設定]來訪問非A4T活動中的[!UICONTROL 高級設定]選項，如下所示：

![進階設定](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## 什麼是計算量度，它們如何取代我過去常用的 SiteCatalyst:Event Mbox?  {#section_D59F4719E6B94758A2187427C17F8EF3}

計算量度可讓您建立衍生自區段或數學計算的自訂量度。您過去可能已使用 `SiteCatlayst:Event` mbox (其中 `evar27=shoes` 且事件為 `purchase`)，而現在您要建立 `evar27=shoes` 的區段，然後建立事件為 `purchase` 並套用該區段的計算量度。這些量度可隨時建立，即使在活動進行後亦然。 然後可用於 Analytics 中的任何報表。

## A4T 會將轉換歸因於多個行銷活動嗎?  {#section_7F15C727206440CD86B3A8CE77087DF9}

是，使用「完整配置」設定。

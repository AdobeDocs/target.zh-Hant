---
keywords: faq;常見問題集;analytics for target;a4T;量度;量度定義
description: 查找有關度量定義和使用Analytics的問題的答案 [!DNL Target] (A4T)。 A4T允許您將分析報告與Adobe [!DNL Target] 活動。
title: 在哪裡可以找到有關A4T度量定義的資訊？
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 38%

---

# 量度定義 - A4T 常見問題集

本主題包含有關度量定義和使用的常見問題的答案 [!DNL Adobe Analytics] 作為 [!DNL Adobe Target] (A4T)。

## 活動成員資格多久到期? 訪問者進入活動後多久，如果他們不再看到活動，則活動將計入活動中？ {#section_41B4958F33534E4B96DEE0C981227A79}

活動的預設到期是在訪客最後一次與活動互動的 90 天之後。如果需要，ClientCare可以調整此設定。 不過，此設定全域適用所有活動，因此不應針對一個案例進行調整。

## 配置我的目標度量時，為什麼無法訪問「高級設定」選項？ {#adv-settings}

的 [!UICONTROL 高級設定] 選項不可用於使用 [!DNL Analytics] 作為報告源(A4T)。

對於使用A4T的活動，目標度量始終使用「[!UICONTROL 增量計數和保留活動中的用戶]&quot;和&quot;[!UICONTROL 論每個印象]。 這些設定是 *不* 可配置。

對於非A4T活動，可以使用 [高級設定選項](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) 來管理衡量成功的方式。 選項包括添加依賴項、選擇是將用戶保留在活動中還是刪除它們，以及是對每個參與者或每個印象計數一次度量。 訪問 [!UICONTROL 高級設定] 通過按一下垂直橢圓> [!UICONTROL 高級設定]，如下所示：

![進階設定](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

## 什麼是計算量度，它們如何取代我過去常用的 SiteCatalyst:Event Mbox? {#section_D59F4719E6B94758A2187427C17F8EF3}

計算量度可讓您建立衍生自區段或數學計算的自訂量度。您過去可能已使用 `SiteCatlayst:Event` mbox (其中 `evar27=shoes` 且事件為 `purchase`)，而現在您要建立 `evar27=shoes` 的區段，然後建立事件為 `purchase` 並套用該區段的計算量度。可以隨時建立這些指標，即使在活動開始後也是如此。 然後可用於 Analytics 中的任何報表。

## A4T 會將轉換歸因於多個行銷活動嗎? {#section_7F15C727206440CD86B3A8CE77087DF9}

是，使用「完全分配」設定。

---
keywords: faq;frequently asked questions;analytics for target;a4T;metric;metric definitions
description: 此主題包含經常詢問關於量度定義和使用 Analytics 做為 Target 報表來源 (A4T) 問題的回答。
title: 量度定義 - A4T 常見問題集
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 100%

---


# 量度定義 - A4T 常見問題集{#metric-definitions-a-t-faq}

此主題包含經常詢問關於量度定義和使用 Analytics 做為 Target 報表來源 (A4T) 問題的回答。

## 活動成員資格多久到期? 訪客進入活動後，如果不再看此活動，則其動作經過多久會計入此活動中? {#section_41B4958F33534E4B96DEE0C981227A79}

活動的預設到期是在訪客最後一次與活動互動的 90 天之後。必要時可由 ClientCare 調整。不過，此設定全域適用所有活動，因此不應針對一個案例進行調整。

## Target 中成功量度的進階選項適用於 A4T 嗎? {#section_F060E3438F4144258BB95813EDEABDAA}

這些選項目前不適用 A4T。

## 什麼是計算量度，它們如何取代我過去常用的 SiteCatalyst:Event Mbox? {#section_D59F4719E6B94758A2187427C17F8EF3}

計算量度可讓您建立衍生自區段或數學計算的自訂量度。您過去可能已使用 `SiteCatlayst:Event` mbox (其中 `evar27=shoes` 且事件為 `purchase`)，而現在您要建立 `evar27=shoes` 的區段，然後建立事件為 `purchase` 並套用該區段的計算量度。好處是即使活動在進行中，仍可隨時建立這些量度。然後可用於 Analytics 中的任何報表。

## A4T 會將轉換歸因於多個行銷活動嗎? {#section_7F15C727206440CD86B3A8CE77087DF9}

是。這是利用「完整分配」設定來完成。

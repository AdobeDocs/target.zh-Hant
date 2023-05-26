---
keywords: faq;常見問題集;analytics for target;a4T;量度;量度定義
description: 尋找有關量度定義和使用Analytics的相關問題解答 [!DNL Target] (A4T)。 A4T可讓您將Analytics報表與Adobe搭配使用 [!DNL Target] 活動。
title: 哪裡可以找到有關A4T量度定義的資訊？
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 29%

---

# 量度定義 - A4T 常見問題集

此主題包含經常詢問關於量度定義和使用的問題的回答 [!DNL Adobe Analytics] 作為的報表來源 [!DNL Adobe Target] (A4T)。

## 活動成員資格多久到期? 訪客進入活動後，如果不再看該活動，則其動作經過多久會計入活動中？ {#section_41B4958F33534E4B96DEE0C981227A79}

+++回答活動的預設到期日為訪客上次與活動互動後90天。 如有需要，ClientCare可調整此設定。 不過，此設定全域適用所有活動，因此不應針對一個案例進行調整。

+++

## 設定目標量度時，為何無法存取進階設定選項？ {#adv-settings}

+++回答 [!UICONTROL 進階設定] 選項不可用於使用的活動 [!DNL Analytics] 作為報表來源(A4T)。

對於使用A4T的活動，目標量度一律使用&quot;[!UICONTROL 增加計數並讓使用者留在活動中]「和」[!UICONTROL 每次曝光時]」設定。 這些設定為 *not* 可設定。

對於非A4T活動，您可以使用 [進階設定選項](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) 以管理您測量成功的方式。 選項包括新增相依性、選擇讓使用者留在活動還是移除活動，以及是否對每個加入者或每次曝光都計算一次量度。 您可存取 [!UICONTROL 進階設定] 非A4T活動中的選項，方法是按一下垂直的點> [!UICONTROL 進階設定]，如下所示：

![進階設定](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## 什麼是計算量度，它們如何取代我過去常用的 SiteCatalyst:Event Mbox? {#section_D59F4719E6B94758A2187427C17F8EF3}

+++回答計算量度可讓您建立衍生自區段或數學計算的自訂量度。 您過去可能已使用 `SiteCatlayst:Event` mbox (其中 `evar27=shoes` 且事件為 `purchase`)，而現在您要建立 `evar27=shoes` 的區段，然後建立事件為 `purchase` 並套用該區段的計算量度。這些量度可隨時建立，即便活動正在進行中也一樣。 然後可用於 Analytics 中的任何報表。

+++

## A4T 會將轉換歸因於多個行銷活動嗎? {#section_7F15C727206440CD86B3A8CE77087DF9}

+++回答「是」，使用「完整配置」設定。

+++
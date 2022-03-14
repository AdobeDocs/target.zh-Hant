---
keywords: 包含規則；包含條件；建議；促銷；動態過濾；動態屬性匹配
description: 瞭解如何在Adobe中動態篩選 [!DNL Target] Recommendations通過將潛在項目池與用戶交互過的特定項目進行比較。
title: 如何按實體屬性匹配篩選Recommendations活動？
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# ![高級](/help/main/assets/premium.png) 實體屬性匹配

動態篩選 [!DNL Adobe Target] [!DNL Recommendations] 通過將潛在建議項的池與用戶已交互的特定項進行比較。

>[!NOTE]
>
>的 [建立和使用包含規則的流程](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) 標準和促銷與使用案例和示例相似。

例如，僅建議與當前項目的品牌匹配的項目，如下例所示：

如果品牌登錄頁上的框返回 `entity.brand=brandA`，則只返回並顯示該頁面上的品牌A產品。 同樣，在品牌B的品牌登錄頁上，只返回品牌B產品。 使用這種類型的動態包含規則，用戶只需指定一條建議規則，該規則將返回所有品牌頁上的相關品牌結果，而不必指定集合或靜態篩選器來匹配每個品牌名稱。

請注意，您必須 `entity.brand` 在登錄頁的框中。

## 實體屬性匹配示例

[!UICONTROL 實體屬性匹配] 允許您僅推薦匹配的項目，例如：

* 用戶當前查看的項中的屬性
* 用戶最近查看的項
* 用戶最近購買的物料
* 用戶最常查看的項目
* 儲存在訪問者配置檔案中的自定義屬性中的項

### 根據品牌推薦項目

構建實體屬性規則後，它們將篩選所有具有與頁面上傳遞的實體值不匹配的屬性的建議。

以下示例顯示與頁面上顯示的產品品牌匹配的建議：

當您訪問具有A品牌產品的頁面時，該頁面將設定 `entity.brand` 「品牌A」的參數。

![目標調用示例](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

在該頁上的建議中，您將只看到A品牌產品。

![品牌A建議](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

如果您隨後查看B品牌產品頁， `entity.brand` 值將重置為「BrandB」，您將看到B品牌產品頁面上推薦的B品牌產品。

![B品牌建議](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### 追加銷售到更昂貴的產品

假設您是一家服裝零售商，希望鼓勵用戶考慮價格更高、因此更有利可圖的商品。 您可以使用「等號」和「介於」運算子來推廣來自同一類別和同一品牌的更昂貴產品。 例如，鞋類零售商可以推廣更貴的跑鞋，以便向看跑鞋的訪客追加銷售，如下例所示：

![追加銷售](/help/main/c-recommendations/c-algorithms/assets/upsell.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### 推廣私有標籤產品

您可以混合使用動態和靜態篩選器來升級專用標籤產品。 例如，辦公室供應公司可以推廣公司家用品牌的碳粉盒，以便讓查看碳粉的訪問者能夠進行更有利可圖的銷售，並推廣公司家用品牌的鋼筆，以便讓查看鋼筆的訪問者能夠進行更有利可圖的銷售，如下例所示：

![品牌](/help/main/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

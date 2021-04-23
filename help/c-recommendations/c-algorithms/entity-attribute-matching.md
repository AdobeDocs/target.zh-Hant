---
keywords: 包含規則；包含條件；建議；促銷；動態過濾；動態；實體屬性匹配
description: 瞭解如何透過比較潛在項目群組與使用者已互動的特定項目，在RecommendationsAdobe [!DNL Target] 中動態篩選。
title: 如何依據Recommendations活動中的實體屬性匹配進行篩選？
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# ![PREMIUMEntity屬](/help/assets/premium.png) 性匹配

將潛在建議項目的群組與使用者已互動的特定項目進行比較，以動態篩選[!DNL Adobe Target] [!DNL Recommendations]。

>[!NOTE]
>
>建立和使用包含規則](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)以取得標準和促銷的[程式與使用案例和範例類似。

例如，建議只使用符合目前項目品牌的項目，如下列範例所示：

如果品牌著陸頁面上的mbox傳回`entity.brand=brandA`，則僅傳回品牌A產品並顯示在該頁面上。 同樣地，在品牌B的品牌著陸頁面上，只會傳回品牌B產品。 使用這種類型的動態包含規則時，使用者只需指定一個建議規則，即可在所有品牌頁面傳回相關品牌結果，而不需指定系列或靜態篩選來符合每個品牌名稱。

請注意，您必須在這些著陸頁面的mbox中傳送`entity.brand`，才能運作。

## 實體屬性符合範例

[!UICONTROL 「實體屬] 性匹配」可讓您僅建議符合的項目，例如：

* 用戶當前查看的項目中的屬性
* 使用者最近檢視的項目
* 使用者最近購買的項目
* 使用者最常檢視的項目
* 儲存在訪客描述檔中自訂屬性的項目

### 根據品牌推薦項目

建立實體屬性規則後，這些規則會篩選出所有具有與頁面上所傳遞之實體值不相符屬性的建議。

下列範例顯示與頁面上顯示的產品品牌相符的建議：

當您造訪具有品牌A產品的頁面時，頁面會將`entity.brand`參數的值設為&quot;BrandA&quot;。

![Target呼叫範例](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

在頁面上的建議中，您只會看到品牌A產品。

![品牌A建議](/help/c-recommendations/c-algorithms/assets/brandA.png)

如果您接著檢視品牌B產品頁面，`entity.brand`值將重設為「品牌B」，您會看到品牌B產品頁面上建議的品牌B產品。

![品牌B建議](/help/c-recommendations/c-algorithms/assets/brandB.png)

### 升級銷售更昂貴的產品

假設您是服裝零售商，並想鼓勵使用者考慮更高的價格，因此獲利更多的商品。 您可以使用「等於」和「介於」運算子來促銷來自相同類別和相同品牌的更昂貴項目。 例如，鞋類零售商可促銷更貴的跑鞋，以向上銷售看跑鞋的訪客，如下列範例：

![追加銷售](/help/c-recommendations/c-algorithms/assets/upsell.png)

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

您可以混合動態和靜態篩選來促銷私用標籤產品。 例如，辦公室供應公司可以推廣公司房屋品牌的碳粉盒，以促使查看碳粉的訪客獲利更多，並推廣公司房屋品牌的鋼筆，以促使查看鋼筆的訪客獲利更多，如以下範例：

![House Brand](/help/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

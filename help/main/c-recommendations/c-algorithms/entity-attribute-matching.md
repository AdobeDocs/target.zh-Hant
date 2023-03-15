---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；動態；實體屬性比對
description: 了解如何在Adobe中動態篩選 [!DNL Target] Recommendations，比較一批潛在項目與使用者已互動的特定項目。
title: 如何在Recommendations活動中依實體屬性比對來篩選？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---

# 實體屬性比對

動態篩選 [!DNL Adobe Target] [!DNL Recommendations] 比較一批潛在的建議項目與使用者已互動的特定項目。

>[!NOTE]
>
>此 [建立和使用包含規則的程式](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) 條件和促銷活動的使用案例和範例也類似。

例如，僅建議符合目前項目品牌的項目，如下列範例所示：

如果品牌登陸頁面上的mbox傳回 `entity.brand=brandA`，則只會傳回品牌A產品並在該頁面上顯示。 同樣地，在品牌B的品牌登陸頁面上，只會傳回品牌B產品。 使用這種類型的動態包含規則時，使用者只需指定一個建議規則，可傳回所有品牌頁面上的相關品牌結果，而不需指定集合或靜態篩選來比對每個品牌名稱。

請注意，您必須傳送 `entity.brand` 在這些登錄頁面上的mbox中，以便運作。

## 實體屬性比對範例

[!UICONTROL 實體屬性比對] 僅可讓您建議符合的項目，例如：

* 用戶當前查看的項的屬性
* 使用者最近檢視的項目
* 使用者最近購買的項目
* 使用者最常檢視的項目
* 儲存在訪客設定檔中自訂屬性中的項目

### 根據品牌推薦項目

建立實體屬性規則後，這些規則會篩選出所有具有與頁面上傳遞的實體值不相符屬性的建議。

下列範例顯示頁面上顯示的符合產品品牌的建議：

當您造訪的頁面具有品牌A產品時，頁面會設定 `entity.brand` 參數至「BrandA」。

![範例Target呼叫](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

在頁面上的建議中，您只會看到品牌A產品。

![品牌A建議](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

如果您接著檢視品牌B產品頁面，則 `entity.brand` 值會重設為「BrandB」，而您會看到Brand B產品頁面上建議的Brand B產品。

![品牌B建議](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### 向更貴的產品追加銷售

假設您是服裝零售商，並想鼓勵使用者考慮價格較高，因此獲利較豐厚的項目。 您可以使用「等於」和「介於」運算子，以促銷相同類別和相同品牌中較貴的項目。 例如，鞋類零售商可促銷較貴的跑鞋，以向上銷售看跑鞋的訪客，如下列範例所示：

![向上銷售](/help/main/c-recommendations/c-algorithms/assets/upsell.png)

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

您可以混合動態和靜態篩選以促銷私人標籤產品。 例如，辦公室供應公司可以推廣公司自有品牌的碳粉盒，以便讓查看碳粉的訪客獲得更有利可圖的銷售，並推廣公司自有品牌的鋼筆，以便讓查看鋼筆的訪客獲得更有利可圖的銷售，如以下示例所示：

![品牌](/help/main/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

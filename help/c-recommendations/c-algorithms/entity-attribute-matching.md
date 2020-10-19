---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;entity attribute matching
description: 在Adobe Target Recommendations中動態篩選，將潛在建議項目的群組與使用者已互動的特定項目進行比較。
title: Adobe Target Recommendations中動態包含規則中依實體屬性比對篩選
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Entity Attribute Matching

Filter dynamically in [!DNL Adobe Target] [!DNL Recommendations] by comparing a pool of potential recommendations items to a specific item that the user has interacted with.

例如，只建議符合目前項目品牌的項目，如下列範例所示：

如果「品牌著陸頁面」上的mbox傳 `entity.brand=Nike`回，則僅會傳回Nike產品並顯示在該頁面上。 同樣地，在阿迪達斯的品牌登陸頁面上，只會傳回阿迪達斯產品。 使用這種類型的動態包含規則時，使用者只需指定一個建議規則，即可在所有品牌頁面傳回相關品牌結果，而不需指定系列或靜態篩選以符合每個品牌名稱。

## 實體屬性匹配示例

[!UICONTROL 「實體屬性符合] 」可讓您僅建議符合的項目，例如：

* 用戶當前查看的項目中的屬性
* 使用者最近檢視的項目
* 使用者最近購買的項目
* 使用者最常檢視的項目
* 儲存在訪客描述檔中自訂屬性的項目

### 升級銷售更昂貴的產品

假設您是服裝零售商，並想鼓勵使用者考慮更高的價格，因此獲利更多的商品。 您可以使用「等於」和「介於」運算子來促銷來自相同類別和相同品牌的更昂貴項目。 例如，鞋類零售商可促銷更貴的跑鞋，以向上銷售看跑鞋的訪客，如下列程式碼範例：

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

您可以混合動態和靜態篩選來促銷私用標籤產品。 例如，辦公室供應公司可以推廣公司房屋品牌的碳粉盒，以促使查看碳粉的訪客獲利更多，並推廣公司房屋品牌的鋼筆，以促使查看鋼筆的訪客獲利更多，如下列程式碼範例：

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

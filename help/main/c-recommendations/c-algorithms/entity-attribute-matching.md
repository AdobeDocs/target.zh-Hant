---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；動態；實體屬性比對
description: 瞭解如何在Adobe中動態篩選 [!DNL Target] 將潛在專案集區與使用者已互動的特定專案做比較，即可使用Recommendations。
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

動態篩選 [!DNL Adobe Target] [!DNL Recommendations] 比較一批潛在的建議專案與使用者已互動的特定專案。

>[!NOTE]
>
>此 [建立及使用包含規則的程式](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) 對於條件和促銷活動，其使用案例和範例相當類似。

例如，僅建議符合目前專案品牌的專案，如下列範例所示：

如果品牌登陸頁面上的mbox傳回 `entity.brand=brandA`，則只有品牌A產品會傳回並顯示在該頁面上。 同樣地，在品牌B的品牌登陸頁面上，僅傳回品牌B產品。 使用這類動態包含規則，使用者只需指定一個建議規則，即可傳回所有品牌頁面上的相關品牌結果，無需指定系列或靜態篩選器以符合每個品牌名稱。

請注意，您必須傳遞 `entity.brand` （位於這些登陸頁面上的mbox中），如此才能運作。

## 實體屬性比對範例

[!UICONTROL 實體屬性比對] 可讓您僅建議相符的專案，例如：

* 使用者目前正在檢視的專案中的屬性
* 使用者最近檢視的專案
* 使用者最近購買的專案
* 使用者最常檢視的專案
* 儲存在訪客設定檔之自訂屬性中的專案

### 根據品牌推薦專案

建置實體屬性規則後，系統會篩選掉屬性與頁面上傳遞之實體值不符的所有建議。

以下範例顯示與頁面上顯示的產品品牌相符的建議：

當您造訪具有Brand A產品的頁面時，該頁面會設定 `entity.brand` 「BrandA」的引數。

![Target呼叫範例](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

在頁面上的建議中，您只會看到Brand A產品。

![品牌A建議](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

如果您接著檢視品牌B產品頁面，請 `entity.brand` 值將會重設為「BrandB」，而您會在Brand B產品頁面上看到建議的Brand B產品。

![品牌B建議](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### 追加銷售至較貴的產品

假設您是服裝零售商，並且想要鼓勵使用者考慮價格較高，進而獲利更高的商品。 您可以使用「等於」和「介於」運運算元，促銷相同類別和相同品牌中較貴的專案。 例如，鞋類零售商可以促銷較貴的跑鞋，以向上銷售看過跑鞋的訪客，如下列範例所示：

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

### 推廣私人標籤產品

您可以混合動態和靜態篩選器，以促銷私密標籤產品。 例如，一家辦公室供應公司可以宣傳公司自有品牌的碳粉匣，以針對檢視碳粉匣的訪客推動利潤更高的銷售，並宣傳公司自有品牌的筆，以針對檢視筆的訪客推動利潤更高的銷售，如以下範例所示：

![自家品牌](/help/main/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

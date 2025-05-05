---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；動態；實體屬性比對
description: 瞭解如何透過將潛在專案集區與使用者已互動的特定專案進行比較，以動態篩選 [!DNL Target Recommendations] 。
title: 如何在Recommendations活動中依實體屬性比對來篩選？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# 實體屬性比對

比較一批可能的建議專案與使用者已互動的特定專案，以在[!DNL Adobe Target Recommendations]中動態篩選。

>[!NOTE]
>
>建立和使用條件與促銷活動包含規則[&#128279;](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)的程式相似，使用案例和範例也類似。

例如，僅建議符合目前專案品牌的專案，如下列範例所示：

如果品牌登陸頁面上的mbox傳回`entity.brand=brandA`，則只會傳回品牌A產品並顯示在該頁面上。 同樣地，在品牌B的品牌登陸頁面上，僅傳回品牌B產品。 使用這類動態包含規則時，使用者只需指定一個建議規則，即可傳回所有品牌頁面上的相關品牌結果，而非指定系列或靜態篩選器以符合每個品牌名稱。

請注意，您必須在這些登陸頁面上的mbox中傳遞`entity.brand`，此程式才能運作。

## 實體屬性比對範例

[!UICONTROL Entity Attribute Matching]可讓您僅建議符合的專案，例如：

* 使用者目前正在檢視的專案中的屬性
* 使用者最近檢視的專案
* 使用者最近購買的專案
* 使用者最常檢視的專案
* 儲存在訪客設定檔之自訂屬性中的專案

### 根據品牌推薦專案

建置實體屬性規則後，系統會篩選掉屬性不符合頁面所傳遞實體值的所有建議。

下列範例顯示與頁面上顯示之產品品牌相符的建議：

當您造訪具有品牌A產品的頁面時，該頁面會將`entity.brand`引數的值設為「品牌A」。

![目標呼叫範例](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

在頁面上的建議中，您只會看到Brand A產品。

![品牌A建議](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

如果您接著檢視品牌B產品頁面，則`entity.brand`值將會重設為「品牌B」，且您會看到品牌B產品頁面上建議的品牌B產品。

![品牌B建議](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### 追加銷售至更昂貴的產品

假設您是服裝零售商，並且想要鼓勵使用者考慮價格較高，進而獲得較高利潤的專案。 您可以使用「等於」和「介於」運運算元，促銷相同類別和相同品牌中較貴的專案。 例如，鞋類零售商可促銷較貴的跑鞋，以向上銷售看過跑鞋的訪客，如下列範例所示：

![追加銷售](/help/main/c-recommendations/c-algorithms/assets/upsell-new.png)

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

您可以混合動態和靜態篩選器，以促銷私密標籤產品。 例如，一家辦公室供應公司可以促銷公司自有品牌的碳粉匣，以針對檢視碳粉匣的訪客推動更有利可圖的銷售，並促銷公司自有品牌的筆，以針對檢視筆的訪客推動更有利可圖的銷售，如下列範例所示：

![自家品牌](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)
)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

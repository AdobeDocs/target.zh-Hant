---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；動態；實體屬性比對
description: 瞭解如何比較潛在專案集區與使用者已互動的特定專案，以在[!DNL Target Recommendations]中動態篩選。
title: 實體屬性比對
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
TQID: 'https://experienceleague.adobe.com/2cBSfWXS96u7iumehPd7enxPjQcebkQCdSBSHWOUcJg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 5%
---
# 實體屬性比對 {#entity-attribute-matching}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在[!DNL Adobe Target Recommendations]中比較潛在建議專案集區與訪客已互動的特定專案，以動態篩選建議。

>[!ENDSHADEBOX]

**[!UICONTROL 實體屬性比對]**&#x200B;只建議符合訪客已互動之專案屬性的專案。 對於條件和促銷活動，建立和使用包含規則的過程很相似，就如同使用案例和範例很相似一樣。 如需詳細資訊，請參閱[使用動態和靜態包含規則](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)。

## 實體屬性比對範例

**[!UICONTROL 實體屬性比對]**&#x200B;只能建議符合的專案，例如：

* 訪客目前正在檢視的專案屬性
* 訪客最近檢視的專案
* 訪客最近購買的專案
* 訪客最常檢視的專案
* 儲存在訪客設定檔的自訂屬性中的專案

### 根據品牌推薦專案

建立實體屬性規則後，系統會篩選掉屬性不符合頁面所傳遞實體值的所有建議。 `entity.brand`值必須在頁面上的mbox中傳遞，此程式才能運作。

使用這類動態包含規則時，只需指定一個建議規則即可傳回所有品牌頁面上的相關品牌結果，而非每個品牌名稱的集合或靜態篩選器。

例如，當顯示具有品牌A產品的頁面時，該頁面會將`entity.brand`引數的值設定為「品牌A」。 在品牌登陸頁面上，mbox傳回`entity.brand=brandA`。

![目標呼叫範例](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

然後，頁面上的建議將僅包含品牌A產品。

![品牌A建議](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

顯示品牌B產品頁面時，`entity.brand`值會重設為「品牌B」，僅建議使用品牌B產品。 同樣地，在品牌B的品牌登陸頁面上，僅傳回品牌B產品。

![品牌B建議](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### 追加銷售至更昂貴的產品

為了鼓勵訪客考慮價格較高、因此較有利可圖的專案，「等於」和「介於」運運算元可促銷相同類別和相同品牌中較貴的專案。 例如，鞋子retailer可以促銷較貴的跑鞋，以便向正在檢視跑鞋的訪客追加銷售，如以下範例所示：

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

動態和靜態篩選器可混合使用，以促銷私密標籤產品。 例如，一家辦公室供應公司可以促銷公司自家品牌的碳粉匣，以針對正在檢視碳粉匣的訪客推動更具利潤的銷售，而針對正在檢視筆的訪客推動公司自家品牌的筆，如下列範例所示：

![自家品牌](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

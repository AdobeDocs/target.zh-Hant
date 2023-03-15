---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；動態；設定檔屬性比對
description: 了解如何在Adobe中動態篩選 [!DNL Target] Recommendations，比較項目（實體）與使用者設定檔中的值。
title: 如何在Recommendations活動中依設定檔屬性比對篩選？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 7%

---

# 設定檔屬性比對

動態篩選 [!DNL Adobe Target] [!DNL Recommendations] 比較項目（實體）與使用者設定檔中的值。

使用 [!UICONTROL 設定檔屬性比對] 當您想要顯示符合訪客設定檔中儲存之值的建議時，例如大小或最喜愛的品牌。

>[!NOTE]
>
>此 [建立和使用包含規則的程式](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) 條件和促銷活動的使用案例和範例也類似。

下列案例顯示如何使用 [!UICONTROL 設定檔屬性比對]:

* 一家銷售眼鏡的公司將訪客最喜愛的邊框顏色儲存為「核桃」。 針對該特定訪客，建議設定為只傳回符合顏色「核桃」的眼鏡框。
* 可在訪客瀏覽您公司網站時，針對其服裝大小（例如小、中或大）定義設定檔參數。 可以設定建議以符合該設定檔參數，並傳回僅限使用者偏好服裝大小的特定產品。

## 設定檔屬性比對範例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 設定檔屬性比對] 可讓您僅建議符合訪客設定檔中屬性的項目，如下列範例所示。

### 從使用者最喜愛的品牌推薦項目

例如，您可以使用 [!UICONTROL 設定檔屬性比對] 選項，建立僅在品牌等於中儲存的值或文字時才建議項目的規則 `profile.favoritebrand`. 透過此規則，如果訪客在查看特定品牌的慢跑短褲，則只有符合使用者最喜愛品牌 (訪客設定檔中 `profile.favoritebrand` 內儲存的值) 的建議才會出現。

![最喜愛的品牌](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 將工作與求職者匹配

假設你想把工作和求職者匹配起來。 您只想建議與求職者位於相同城市的工作。

您可以使用包含規則來將求職者的位置從其訪客的設定檔匹配至工作清單，如下列範例所示：

![使用者的城市](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根據大小推薦項目

如需設定檔屬性比對如何影響建議的視覺範例，請考慮銷售電風扇的網站。

當訪客點按此網站上的粉絲各種影像時，每個頁面會設定 `entity.size` 參數，根據影像中的風扇大小是否小。

假設您已建立設定檔指令碼來追蹤及計算 `entity.size` 設為小而大。

如果訪客接著返回首頁，則會根據訪客是否點按了更多小粉絲或大粉絲，而看到經過篩選的建議。

Recommendations的基礎是在網站上檢視更多小型粉絲：

![小型粉絲建議](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations的基礎是在網站上檢視更多大型粉絲：

![大粉絲建議](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)

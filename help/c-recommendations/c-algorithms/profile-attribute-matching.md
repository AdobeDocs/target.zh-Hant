---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: 透過比較項目（實體）與使用者設定檔中的值，在Adobe Target Recommendations中動態篩選。
title: 在Adobe Target Recommendations中動態包含規則中依描述檔屬性比對篩選
feature: criteria
translation-type: tm+mt
source-git-commit: 60b71c426b61bb16a23976da9a03926f8e73cf6c
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 7%

---


# ![PREMIUM](/help/assets/premium.png) Profile屬性匹配

透過比較 [!DNL Adobe Target] 項目(實 [!DNL Recommendations] 體)與使用者設定檔中的值，動態篩選。

當您  想要顯示符合訪客描述檔中儲存之值（例如大小或我的最愛品牌）的建議時，請使用描述檔屬性符合。

>[!NOTE]
>
>The [process for creating and using inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) for criteria and promotions is similar, as are the use cases and examples.

下列案例說明如何使用描述檔 [!UICONTROL 屬性符合]:

* 一家銷售眼鏡的公司把遊客喜愛的畫格顏色儲存為「胡桃木」。 針對該特定訪客，建議設定為僅傳回符合彩色「胡桃」的眼鏡影格。
* 描述檔參數可定義為訪客瀏覽公司網站時的服裝尺寸（例如，「小」、「中」或「大」）。 建議可設定為符合該描述檔參數，並傳回僅針對使用者偏好服裝尺寸的特定產品。

## 描述檔屬性比對範例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 「描述檔屬性符合] 」可讓您僅建議符合訪客描述檔中屬性的項目，如下列範例所示。

### 從使用者最愛的品牌推薦項目

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. 透過此規則，如果訪客在查看特定品牌的慢跑短褲，則只有符合使用者最喜愛品牌 (訪客設定檔中 `profile.favoritebrand` 內儲存的值) 的建議才會出現。

![最愛的品牌](/help/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 將工作與求職者相匹配

假設你試圖把工作與求職者匹配。 您只想推薦與求職者位於同一城市的工作。

您可以使用包含規則，將求職者的位置從訪客的個人檔案比對至工作清單，如下列範例所示：

![使用者的城市](/help/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根據大小推薦項目

如需描述檔屬性比對如何影響建議的視覺化範例，請考慮銷售電風扇的網站。

當訪客點按此網站上的粉絲影像時，每個頁面會根據影像中的粉絲大小 `entity.size` ，來設定參數值。

假設您已建立描述檔指令碼，以追蹤並計算其值設定為小 `entity.size` 或大的次數。

如果訪客接著返回首頁，他或她會根據是否點按了更多小粉絲或大粉絲，看到篩選的建議。

根據在網站上檢視更多小粉絲的建議：

![小粉絲建議](/help/c-recommendations/c-algorithms/assets/small-fans.png)

根據在網站上檢視更多大型粉絲的建議：

![大型粉絲建議](/help/c-recommendations/c-algorithms/assets/large-fans.png)
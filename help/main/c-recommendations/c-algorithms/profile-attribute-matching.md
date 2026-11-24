---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；動態；設定檔屬性比對
description: 瞭解如何比較專案（實體）與使用者設定檔中的值，以在[!DNL Target Recommendations]中動態篩選。
title: 輪廓屬性比對
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
TQID: 'https://experienceleague.adobe.com/Gm91Mww5ylvNjUcmzp6KwxIG6LTibvI44LnW67KFzqk'
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
source-wordcount: '503'
ht-degree: 5%
---
# 輪廓屬性比對 {#profile-attribute-matching}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何比較專案（實體）與訪客設定檔中的值，以動態篩選[!DNL Adobe Target Recommendations]中的建議。

>[!ENDSHADEBOX]

使用&#x200B;**[!UICONTROL 設定檔屬性比對]**&#x200B;來顯示符合訪客設定檔中儲存之值（例如大小或最喜愛的品牌）的建議。 對於條件和促銷活動，建立和使用包含規則的過程很相似，就如同使用案例和範例很相似一樣。 如需詳細資訊，請參閱[使用動態和靜態包含規則](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)。

下列案例顯示如何使用&#x200B;**[!UICONTROL 設定檔屬性比對]**：

* 一家銷售眼鏡的公司會將訪客最喜愛的鏡框顏色儲存為「核桃」。 對於該訪客，建議設定為僅傳回顏色符合「核桃」的眼鏡框。
* 當訪客導覽公司網站時，可以針對訪客的服裝尺寸（例如，小、Medium或大）定義設定檔引數。 可設定建議以符合該設定檔引數，且僅傳回訪客穿戴偏好服裝尺寸的產品。

## 設定檔屬性比對範例

**[!UICONTROL 設定檔屬性比對]**&#x200B;只建議符合訪客設定檔中屬性的專案，如下列範例所示。

### 從使用者最喜愛的品牌推薦專案

**[!UICONTROL 設定檔屬性比對]**&#x200B;選項可建立一個規則，只在品牌等於`profile.favoritebrand`中儲存的值或文字時才建議專案。 透過此規則，如果訪客在檢視特定品牌的慢跑短褲，則只會顯示符合該訪客最喜愛品牌的建議（訪客設定檔中儲存在`profile.favoritebrand`中的值）。

![最喜愛的品牌](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 比對工作與求職者

若要比對工作與求職者，只建議工作與求職者位於相同城市。 包含規則可比對求職者從訪客設定檔到工作清單的位置，如下列範例所示：

![使用者的城市](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根據大小推薦專案

下列範例說明個人資料屬性比對在銷售電風扇的網站上影響推薦的方式。

當訪客點按此網站上各種粉絲影像時，每個頁面會根據影像中的粉絲大小是小還是大來設定`entity.size`引數的值。 設定檔指令碼會追蹤並計算`entity.size`值設為小與大的次數。

如果訪客接著返回首頁，則會根據點按了更多小型粉絲還是大型粉絲，顯示篩選的建議。

根據在網站上檢視更多小型粉絲的建議：

![小粉絲推薦](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

根據在網站上檢視較大粉絲的建議：

![大型粉絲推薦](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)

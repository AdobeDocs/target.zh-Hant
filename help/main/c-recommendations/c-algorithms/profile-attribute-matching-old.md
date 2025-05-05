---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；動態；設定檔屬性比對
description: 瞭解如何比較專案（實體）與使用者設定檔中的值，以在Adobe [!DNL Target] Recommendations中動態篩選。
title: 如何在Recommendations活動中依設定檔屬性比對來篩選？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 7%

---

# 設定檔屬性比對

比較專案（實體）與使用者設定檔中的值，以在[!DNL Adobe Target] [!DNL Recommendations]中動態篩選。

當您想要顯示符合儲存在訪客設定檔中的值（例如大小或最喜愛的品牌）的建議，請使用[!UICONTROL Profile Attribute Matching]。

>[!NOTE]
>
>建立和使用條件與促銷活動包含規則[&#128279;](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)的程式相似，使用案例和範例也類似。

下列案例顯示如何使用[!UICONTROL Profile Attribute Matching]：

* 一家銷售眼鏡的公司會將訪客最喜愛的鏡框顏色儲存為「核桃」。 對於該特定訪客，建議設定為僅傳回顏色符合「核桃」的眼鏡框。
* 您可以在訪客瀏覽您公司的網站時，針對訪客的服裝尺寸(例如，小、Medium或大)定義設定檔引數。 可設定建議以符合該設定檔引數，並只傳回使用者偏好服裝尺寸特有的產品。

## 設定檔屬性比對範例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching]可讓您僅建議符合訪客設定檔中某個屬性的專案，如下列範例所示。

### 從使用者最喜愛的品牌推薦專案

例如，您可以使用[!UICONTROL Profile Attribute Matching]選項來建立規則，而只在品牌等於`profile.favoritebrand`中儲存的值或文字時才建議專案。 透過此規則，如果訪客在查看特定品牌的慢跑短褲，則只有符合使用者最喜愛品牌 (訪客輪廓中 `profile.favoritebrand` 內儲存的值) 的建議才會出現。

![最喜愛的品牌](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 比對工作與求職者

假設您正嘗試將工作與求職者進行比對。 您只想建議與求職者位於相同城市的工作。

您可以使用包含規則，將求職者在其訪客設定檔中的位置與工作清單比對，如下列範例所示：

![使用者的城市](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根據大小推薦專案

如需設定檔屬性比對如何影響建議的視覺範例，請考量銷售電風扇的網站。

當訪客點按此網站上各種粉絲影像時，每個頁面會根據影像中的粉絲大小是小還是大來設定`entity.size`引數的值。

假設您已建立設定檔指令碼，以追蹤和計算`entity.size`值設定為小與大的次數。

如果訪客隨後返回首頁，他將看到根據點按了更多小粉絲還是大粉絲而篩選的建議。

Recommendations根據在網站上檢視更多小粉絲而定：

![小粉絲推薦](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations根據在網站上檢視更多大型粉絲：

![大型粉絲推薦](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)

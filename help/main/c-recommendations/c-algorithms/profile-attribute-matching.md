---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；動態；設定檔屬性比對
description: 瞭解如何在Adobe中動態篩選 [!DNL Target] 比較專案（實體）與使用者設定檔中的值，以進行Recommendations。
title: 如何在Recommendations活動中依設定檔屬性比對來篩選？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 7%

---

# 設定檔屬性比對

動態篩選 [!DNL Adobe Target] [!DNL Recommendations] 比較專案（圖元）與使用者設定檔中的值。

使用 [!UICONTROL 設定檔屬性比對] 當您想要顯示符合訪客設定檔中儲存之值（例如大小或最喜愛的品牌）的建議。

>[!NOTE]
>
>此 [建立及使用包含規則的程式](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) 對於條件和促銷活動，其使用案例和範例相當類似。

以下案例顯示您如何使用 [!UICONTROL 設定檔屬性比對]：

* 一家銷售眼鏡的公司將訪客最喜愛的鏡框顏色儲存為「核桃」。 對於該特定訪客，建議設定為僅傳回顏色符合「核桃」的眼鏡框。
* 當訪客瀏覽您公司的網站時，可以為訪客的服裝尺寸（例如，小、中或大）定義設定檔引數。 可設定建議以符合該設定檔引數，並僅傳回使用者偏好的衣服尺寸特定的產品。

## 設定檔屬性比對範例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 設定檔屬性比對] 可讓您僅建議符合訪客設定檔中某個屬性的專案，如下列範例所示。

### 從使用者最喜愛的品牌推薦專案

例如，您可以使用 [!UICONTROL 設定檔屬性比對] 選項來建立規則，僅在品牌等於中儲存的值或文字時建議專案。 `profile.favoritebrand`. 透過此規則，如果訪客在查看特定品牌的慢跑短褲，則只有符合使用者最喜愛品牌 (訪客設定檔中 `profile.favoritebrand` 內儲存的值) 的建議才會出現。

![最喜愛的品牌](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 匹配工作與求職者

假設您正嘗試將工作與求職者進行比對。 您只想建議與求職者位於相同城市的工作。

您可以使用包含規則，將求職者在其訪客設定檔中的位置與工作清單進行比對，如下列範例所示：

![使用者所在城市](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根據大小建議專案

如需設定檔屬性比對如何影響建議的視覺範例，請考量銷售電風扇的網站。

當訪客點按此網站上的各種粉絲影像時，每個頁面都會設定 `entity.size` 引數是根據影像中風扇的大小是小還是大。

假設您已建立個人資料指令碼來追蹤和計算下列專案的值次數： `entity.size` 設為小與大。

如果訪客隨後返回首頁，他將看到根據點選了更多小粉絲或大粉絲篩選出的建議。

Recommendations根據在網站上檢視更多小型粉絲：

![小型粉絲推薦](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations根據在網站上檢視更多大型粉絲：

![大型粉絲推薦](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)

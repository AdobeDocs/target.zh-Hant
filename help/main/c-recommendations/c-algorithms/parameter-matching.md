---
keywords: 包含規則；包含條件；建議；促銷活動；促銷活動；動態篩選；動態；引數比對
description: 瞭解如何透過比較專案（實體）與請求中的值（API或mbox），在Adobe [!DNL Target] Recommendations中動態篩選。
title: 參數比對
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
TQID: 'https://experienceleague.adobe.com/GTli-O1p4Gm2Fg9J-L0ukQ8dSw2t-da8OatFLP8Ks9g'
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
source-wordcount: '311'
ht-degree: 8%
---
# 參數比對 {#parameter-matching}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何比較專案（實體）與要求（API或mbox）中的值，以動態篩選[!DNL Adobe Target Recommendations]中的建議。

>[!ENDSHADEBOX]

**[!UICONTROL 引數符合]**&#x200B;只建議符合頁面引數或訪客引數的內容，例如裝置維度或地理位置。 例如，只能建議符合「產業」頁面引數的內容。 對於條件和促銷活動，建立和使用包含規則的過程很相似，就如同使用案例和範例很相似一樣。 如需詳細資訊，請參閱[使用動態和靜態包含規則](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)。

其他範例包括：

* 熒幕寬度和高度的Mbox引數可用來鎖定行動訪客，且僅建議行動裝置和配件。
* Recommendations規則只能傳回符合或超過訪客用來檢視頁面之行動裝置熒幕高度的熱銷手機。
* 區域地理位置引數可用來在冬季傳回工具建議。 在下雪地區的訪客可建議使用吹雪機和其他降雪工具，但不建議未下雪地區的訪客使用。

## 引數比對範例

[!DNL Recommendations]可以比對[!DNL Target]呼叫中傳送的引數值。 在下列範例中，[!DNL Target]會根據[!DNL Target]呼叫中傳送的熒幕高度和寬度引數，偵測到訪客正在使用行動裝置，並僅建議行動裝置專案。

考量下列範例[!DNL Target]呼叫：

![目標呼叫](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

訪客檢視的頁面上會顯示行動裝置產品。

![行動裝置產品](/help/main/c-recommendations/c-algorithms/assets/phones.png)

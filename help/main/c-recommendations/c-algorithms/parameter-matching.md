---
keywords: 包含規則；包含條件；建議；促銷活動；促銷活動；動態篩選；動態；引數比對
description: 瞭解如何透過比較專案（實體）與請求中的值（API或mbox），在Adobe [!DNL Target] Recommendations中動態篩選。
title: 如何在Recommendations活動中依引數比對來篩選？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 10%

---

# [!UICONTROL Parameter Matching]

比較專案（實體）與請求（API或mbox）中的值，以動態篩選。

例如，如下列範例所示，僅建議符合「產業」頁面引數或其他引數（例如裝置尺寸或地理位置）的內容。

* 熒幕寬度和高度的Mbox引數可用來鎖定行動訪客，且僅建議行動裝置和配件。
* 建立建議規則，只傳回符合或超過訪客使用檢視頁面之行動裝置熒幕高度的熱銷手機。
* 區域地理位置引數可用來在冬季傳回工具建議。 在下雪地區，建議使用吹雪車和其他降雪工具，但若未下雪，則不建議使用訪客。

>[!NOTE]
>
>如果活動是在2016年10月31日之前建立，假如使用「引數比對」篩選器，則傳送會失敗。 若想暫時解決此問題，請:
>
>* 建立新活動，並在其中新增條件。
>* 使用不包含「參數比對」篩選的條件。
>* 從條件中移除「參數比對」篩選。

## 引數比對範例

[!UICONTROL Parameter Matching]可讓您建議符合頁面引數或訪客引數的內容，例如裝置維度或地理位置，如下列範例所示：

[!DNL Recommendations]可以比對[!DNL Target]呼叫中傳送的引數值。 在此執行個體中，[!DNL Target]會根據[!DNL Target]呼叫中傳送的熒幕高度和寬度引數，偵測到訪客正在使用行動裝置，並僅建議行動裝置專案。

考量下列範例Target呼叫：

![目標呼叫](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

訪客在檢視的頁面上，將會看到行動裝置產品。

![行動裝置產品](/help/main/c-recommendations/c-algorithms/assets/phones.png)

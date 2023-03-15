---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；動態；參數比對
description: 了解如何在Adobe中動態篩選 [!DNL Target] Recommendations，比較項目（實體）與請求（API或mbox）中的值。
title: 如何在Recommendations活動中依參數比對篩選？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 10%

---

# 參數比對

比較項目（實體）與請求（API或mbox）中的值，以動態篩選。

例如，僅建議符合「產業」頁面參數或其他參數（例如裝置維度或地理位置）的內容，如下列範例所示。

* 螢幕寬度和高度的mbox參數可用來定位行動訪客，並僅建議行動裝置和附件。
* 建立建議規則，只傳回符合或超過訪客使用頁面檢視之行動裝置的螢幕高度、最暢銷的行動電話。
* 冬天期間，區域地理位置參數可用來傳回工具的建議。 可以為下雪地區的訪客建議吹雪器和其他降雪工具，但不建議為未下雪地區的訪客建議。

>[!NOTE]
>
>如果活動是在2016年10月31日之前建立，如果使用「參數比對」篩選，則傳送會失敗。 若想暫時解決此問題，請:
>
>* 建立新活動，並在其中新增條件。
>* 使用不包含「參數比對」篩選的條件。
>* 從條件中移除「參數比對」篩選。


## 參數比對範例

[!UICONTROL 參數比對] 可讓您建議符合頁面參數或訪客參數的內容，例如裝置維度或地理位置，如下列範例所示：

[!DNL Recommendations] 可比對中傳送的參數值 [!DNL Target] 呼叫。 在這種情況下， [!DNL Target] 會根據 [!DNL Target] 呼叫，且僅建議屬於行動裝置的項目。

請考量下列範例Target呼叫：

![Target呼叫](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

在訪客檢視的頁面上，他或她會看到行動裝置產品。

![行動裝置產品](/help/main/c-recommendations/c-algorithms/assets/phones.png)

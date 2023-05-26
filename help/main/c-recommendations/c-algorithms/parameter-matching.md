---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；動態；引數比對
description: 瞭解如何在Adobe中動態篩選 [!DNL Target] 比較專案（實體）與請求（API或mbox）中的值，以瞭解Recommendations。
title: 如何在Recommendations活動中依引數比對來篩選？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 10%

---

# 參數比對

比較專案（實體）與請求（API或mbox）中的值，以動態篩選。

例如，僅建議符合「產業」頁面引數或其他引數（例如裝置尺寸或地理位置）的內容，如以下範例所示。

* 熒幕寬度和高度的mbox引數可用來鎖定行動訪客，且僅建議使用行動裝置和配件。
* 建立建議規則，只傳回符合或超過訪客正在使用檢視頁面之行動裝置熒幕高度的熱銷手機。
* 區域地理位置引數可用於在冬季傳回對工具的建議。 對於下雪地區的訪客，建議使用吹雪機和其他降雪工具，但對於不下雪地區的訪客，則不建議使用。

>[!NOTE]
>
>如果活動是在2016年10月31日之前建立，假如使用「引數比對」篩選器，則傳送會失敗。 若想暫時解決此問題，請:
>
>* 建立新活動，並在其中新增條件。
>* 使用不包含「參數比對」篩選的條件。
>* 從條件中移除「參數比對」篩選。


## 引數比對範例

[!UICONTROL 引數比對] 可讓您建議符合頁面引數或訪客引數的內容，例如裝置維度或地理位置，如下列範例所示：

[!DNL Recommendations] 可比對中傳送的引數值 [!DNL Target] 呼叫。 在此情況下， [!DNL Target] 根據中傳送的熒幕高度和寬度引數，偵測訪客是否使用行動裝置 [!DNL Target] 呼叫，且只會建議屬於行動裝置的專案。

考量下列範例Target呼叫：

![目標呼叫](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

訪客在檢視的頁面上，將會看到行動裝置產品。

![行動裝置產品](/help/main/c-recommendations/c-algorithms/assets/phones.png)

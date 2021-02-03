---
keywords: 包含規則；包含條件；建議；促銷；動態過濾；動態；參數匹配
description: 透過比較項目（實體）與請求（API或mbox）中的值，在Adobe Target Recommendations中動態篩選。
title: Target Recommendations中動態包含規則中的參數匹配篩選
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 10%

---


# ![](/help/assets/premium.png) PREMIUMParameter匹配

透過比較項目（實體）與請求中的值（API或mbox），動態篩選。

例如，只建議符合「產業」頁面參數或其他參數的內容，例如裝置尺寸或地理位置，如下列範例所示。

* 螢幕寬度和高度的Mbox參數可用來定位行動訪客，並僅建議行動裝置和附件。
* 建立建議規則，只傳回符合或超過訪客使用頁面檢視之行動裝置螢幕高度的暢銷行動電話。
* 區域地理位置參數可用來在冬季傳回工具建議。 在下雪的地區，遊客可以建議使用吹雪機和其他降雪工具，但在沒有下雪的地區，不建議使用。

>[!NOTE]
>
>如果活動是在2016年10月31日之前建立，則其傳送會失敗（如果其使用「參數符合」篩選）。 若想暫時解決此問題，請:
>
>* 建立新活動，並在其中新增條件。
>* 使用不包含「參數比對」篩選的條件。
>* 從條件中移除「參數比對」篩選。


## 參數匹配示例

[!UICONTROL 參] 數匹配可讓您建議符合頁面參數或訪客參數的內容，例如裝置維度或地理位置，如下列範例所示：

[!DNL Recommendations] 可比對呼叫中傳送的參數 [!DNL Target] 值。在此例中，[!DNL Target]會根據[!DNL Target]呼叫中傳送的螢幕高度和寬度參數，偵測訪客是否使用行動裝置，並僅建議使用行動裝置的項目。

請考慮下列Target呼叫範例：

![目標呼叫](/help/c-recommendations/c-algorithms/assets/example-target-call-2.png)

訪客在檢視的頁面上，會看到行動裝置產品。

![行動裝置產品](/help/c-recommendations/c-algorithms/assets/phones.png)

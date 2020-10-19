---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;parameter matching
description: 透過比較項目（實體）與請求（API或mbox）中的值，在Adobe Target Recommendations中動態篩選。
title: Adobe Target Recommendations中動態包含規則中的依參數符合篩選
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 27%

---


# ![PREMIUM](/help/assets/premium.png) Parameter Matching

透過比較項目（實體）與請求中的值（API或mbox），動態篩選。

例如，只建議符合「產業」頁面參數或其他參數的內容，例如裝置尺寸或地理位置，如下列範例所示。

* 螢幕寬度和高度的Mbox參數可用來定位行動訪客，並僅建議行動裝置和附件。
* 區域地理位置參數可用來在冬季傳回工具建議。 在下雪的地區，遊客可以建議使用吹雪機和其他降雪工具，但在沒有下雪的地區，不建議使用。

>[!NOTE]
>
>如果活動是在2016年10月31日之前建立，則其傳送會失敗（如果其使用「參數符合」篩選）。 若想暫時解決此問題，請:
>
>* 建立新活動，並在其中新增條件。
>* 使用不包含「參數比對」篩選的條件。
>* 從條件中移除「參數比對」篩選。


可用運算子：

* 等於
* 不等於
* 包含
* 不包含
* 開始於
* 終止於
* 大於或等於
* 小於或等於
* 介於
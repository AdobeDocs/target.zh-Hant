---
keywords: 包含規則；包含條件；建議；促銷；動態過濾；動態匹配；inclusion rules;inclusion criteria;recommendations;promotions;dynamic filtering;dynamic matching
description: 瞭解如何在Adobe中動態篩選 [!DNL Target] Recommendations，將項（實體）與請求（API或mbox）中的值進行比較。
title: 如何按參數匹配篩選Recommendations活動？
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 10%

---

# ![高級](/help/main/assets/premium.png) 參數匹配

通過將項（實體）與請求（API或mbox）中的值進行比較來動態篩選。

例如，只建議與「工業」頁面參數或其他參數匹配的內容，如以下示例中的設備尺寸或地理位置。

* 螢幕寬度和高度的Mbox參數可用於目標移動訪問者，並僅推薦移動設備和附件。
* 建立一個建議規則，該規則僅返回與訪問者使用頁面視圖的移動設備的螢幕高度匹配或超過的暢銷行動電話。
* 在冬季，區域地理位置參數可用於返回工具建議。 在下雪的地區，遊客可以推薦吹雪機和其他降雪工具，但在不下雪的地區，遊客可以不推薦。

>[!NOTE]
>
>如果活動是在2016年10月31日之前建立的，則如果活動使用「參數匹配」篩選器，則其交付將失敗。 若想暫時解決此問題，請:
>
>* 建立新活動，並在其中新增條件。
>* 使用不包含「參數比對」篩選的條件。
>* 從條件中移除「參數比對」篩選。


## 參數匹配示例

[!UICONTROL 參數匹配] 允許您推薦與頁面參數或訪問者參數匹配的內容，如設備尺寸或地理位置，如下例所示：

[!DNL Recommendations] 可以匹配在 [!DNL Target] 呼叫。 在這個例子中， [!DNL Target] 檢測訪問者使用移動設備，根據在 [!DNL Target] 呼叫，並僅推薦屬於移動設備的項目。

請考慮以下Target調用示例：

![目標調用](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

訪問者在瀏覽的頁面上將看到移動設備產品。

![移動設備產品](/help/main/c-recommendations/c-algorithms/assets/phones.png)

---
keywords: Recommendations;設定;名稱;目標;優先順序;持續時間;報表設定;其他中繼資料
description: 瞭解如何配置用於描述和控制Adobe TargetRecommendations活動的設定。
title: 如何配置Recommendations活動設定？
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 84%

---

# ![PREMIUM](/help/main/assets/premium.png) Recommendations 活動設定

有關可用於描述和控制 [!UICONTROL Recommendations] 活動 [!DNL Adobe Target]。

![Recommendations 目標和設定頁面](/help/main/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

以下小節說明 [!UICONTROL Recommendations] 活動可用的設定。

## 名稱

提供將可幫助您和您的團隊識別活動的描述性名稱。

活動名稱中不允許下列字元:

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

如果指定已存在 [!UICONTROL Recommendations Classic] 另一個活動中的 [!UICONTROL Recommendations] 活動名稱，則會將新活動重新同步為新名稱。新名稱為原始名稱附加時間戳記的唯一名稱。此新名稱同時顯示在 [!DNL Target Standard/Premium] 和 [!UICONTROL Recommendations經典]。

## 目標

(可選) 描述活動的目標。

## 優先順序

調整滑桿來決定優先順序層級。

如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。

## 持續時間

設定活動的持續時間。

活動可以在啟用後開始，或者您可以設定特定的日期和時間。同樣地，活動可以在停用時結束，或者您可以設定日期和時間。時間選擇器使用 24 小時時鐘，午夜為 00:00。時區會設為瀏覽器中設定的時區。若要使用不同的時區，請將您的瀏覽器設定為其他時區並重新啟動瀏覽器。

## 報表設定

* **報告源：** 選擇報告源： [!DNL Adobe Target] 或 [分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。 活動上線後，請勿變更報表來源。在活動上線後變更報表來源會導致不一致的報表。
* **目標量度:** 選取判斷活動是否成功的成功量度。
* **其他度量:** 設定要在您的報表中使用的其他成功度量。
* **報表對象:** 定義篩選報表時可以使用的對象。

## 其他中繼資料

輸入關於您的活動的備註。

## 培訓視頻：活動設定(3:02) ![教程徽章](/help/main/assets/tutorial.png)

此影片包括關於活動設定的資訊。

* 輸入活動的目標
* 設定活動的優先順序層級
* 排程活動開始和結束時間
* 新增報表的對象，以建立報表篩選器
* 輸入活動的備註

>[!VIDEO](https://video.tv.adobe.com/v/17381)

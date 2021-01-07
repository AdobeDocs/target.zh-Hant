---
keywords: Goal & Settings;objective;priority;duration
description: 使用Adobe Target中的「活動設定」來管理活動的目標、優先順序和持續時間。
title: 活動設定
feature: Activities
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 83%

---


# 活動設定

使用[!DNL Adobe Target]中的[!UICONTROL 活動設定]來管理活動的目標、優先順序和持續時間。

1. 輸入關於活動目標的備註。

   輸入關於活動的任何資訊，將該資訊放在手邊對您或其他團隊成員來說很有用。拖曳以對[!UICONTROL 「目標」]欄位調整大小。
1. 設定活動的優先順序。

   視您的設定而定，[!UICONTROL 優先順序]的 UI 和選項可能有所不同。您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。

   如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。

   如果[!UICONTROL Administration] > [!UICONTROL Reporting]（預設值）中未啟用此選項，請指定優先順序：低、中或高。

   要啟用細粒度優先順序，請按一下「管理」>「報告」[!UICONTROL ，然後將「啟用細粒度優先順序」]選項切換到「開啟」位置。]][!UICONTROL [!UICONTROL 

   如果已啟用此選項，請指定介於 0 和 999 之間的值:

   * 0 = 低
   * 999 = 高

   對於在舊版 [!DNL Target Standard/Premium] 中建的立活動，低優先順序會轉換為 0，中會轉換為 5，而高則轉換為 10。您可以視需要調整這些值。

   >[!NOTE]
   >
   >在使用微調優先順序後，在您可以停用此選項之前，必須將所有優先順序設定回 0、5 和 10。

1. 設定活動的持續時間。

   您可以手動啟動和停用活動，或活動傳送指定日期和時間。時間控制項會使用 24 小時制，午夜為 00:00。時區會設為瀏覽器中設定的時區。若要使用不同的時區，請將您的瀏覽器設定為其他時區並重新啟動瀏覽器。

   >[!NOTE]
   >
   >排程活動可控制活動的傳送時間範圍，但是必須先明確啟動活動，才能根據指定的排程傳送該活動。

[!UICONTROL 「目標與設定」]頁面包括的其他設定可能因您要建立的活動類型而異。如需這些設定的詳細資訊，參閱您的活動類型:

* [A/B 測試](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [自動個人化](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [體驗鎖定目標](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [多變數測試](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Recommendations](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## 訓練影片: 活動設定  ![教學課程徽章](/help/assets/tutorial.png)

此影片包括關於活動設定的資訊。

* 輸入活動的目標
* 設定活動的優先順序層級
* 排程活動開始和結束時間
* 新增報表的對象，以建立報表篩選器
* 輸入活動的備註

   >[!VIDEO](https://video.tv.adobe.com/v/17381)

---
keywords: 時間範圍;開始日期;結束日期;開始/結束日期;目標排程;週劃分;日劃分;劃分
description: 了解如何使用開始和結束日期及時間，將目標鎖定於在特定時間範圍內造訪您網站的使用者。
title: 我可以定位在特定時間造訪我網站的訪客嗎？
feature: Audiences
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 44%

---

# 時間段

您可以在 [!DNL Adobe Target] 定位在特定時間範圍內造訪您網站的使用者。 您也可以設定「週與日劃分」選項，來為對象鎖定目標建立週期性模式。

例如，使用 [結合的隨選對象功能](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)，您可以鎖定在前三天到黑色星期五期間具有特定內容且低消費的人員，以及在黑色星期五之後具有其他內容的人員。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 為對象命名並新增選用說明。
1. 拖放 **[!UICONTROL 時間範圍]** 進入audience builder窗格。

   ![target_timerane_dialog影像](assets/target_timeframe_dialog.png)

1. 指定 [!UICONTROL 開始] 和 [!UICONTROL 結束] 對象的日期和時間。

   將開始日期保持空白，以根據活動的排程來鎖定目標。將結束日期保持空白，以繼續鎖定目標直到活動的結束日期和時間為止。

   您也可以將開始和結束日期都保持空白。此功能可讓您在多個活動中使用相同的對象（而不需製作對象副本），同時在活動層級控制開始和結束日期。

   >[!NOTE]
   >
   >開始/結束日期的時區會顯示為 GMT +/- NN:NN；其中 NN:NN 是 GMT 時差，會反映帳戶層級時區，而非訪客的時區。例如，加州時區會顯示為 GMT -08:00。

1. （有條件）按一下 **[!UICONTROL 設定頻率]** 設定循環模式，包括星期幾和時間。

   ![週與日劃分](assets/week_and_day_parting.png)

   您可以使用 [!UICONTROL 頻率] 選項，例如，只在呼叫中心人員配備的日期和時間，才向訪客顯示「立即聊天」選項。

   選取一或多個星期幾，然後設定開始和結束時間。按一下 **[!UICONTROL 新增頻率]** 以視需要指定其他模式。

   >[!NOTE]
   >
   >[!UICONTROL 週與日劃分]的時區會顯示為 GMT +/- NN:NN；其中 NN:NN 是 GMT 時差，會反映帳戶層級時區，而非訪客的時區。例如，加州太平洋日光時間的時區會顯示為GMT -07:00。

1. （選用）為對象設定其他規則。

   您可以視需要對每個規則重複步驟5。

1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

## 訓練影片：建立對象 ![概述徽章](/help/main/assets/overview.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

---
keywords: 時間範圍;開始日期;結束日期;開始/結束日期;目標排程;週劃分;日劃分;劃分
description: 瞭解如何使用開始和結束日期及時間，將目標鎖定在特定時間範圍內造訪您網站的使用者。
title: 我可以鎖定在特定時間造訪我網站的訪客嗎？
feature: Audiences
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: 0e4698935b90cc0236abe6a47a6183c7fd2a7b20
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 35%

---

# [!UICONTROL Time Frame]

您可以在[!DNL Adobe Target]中新增開始和結束日期及時間，以鎖定在特定時間範圍內造訪您網站的使用者。 您也可以設定「週與日劃分」選項，來為對象鎖定目標建立週期性模式。

例如，使用[結合的臨機對象功能](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)，您可以鎖定在這三天到黑色星期五期間具有特定內容且低消費的人員，以及在黑色星期五之後具有其他內容的人員。

1. 在[!DNL Target]介面中，按一下&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**。
1. 為對象命名並新增選擇性說明。
1. 將&#x200B;**[!UICONTROL Time Frame]**&#x200B;拖放至對象產生器窗格。

   ![target_timeframe_dialog影像](assets/target_timeframe_dialog.png)

1. 指定對象的[!UICONTROL Start]和[!UICONTROL End]日期和時間。

   將開始日期保持空白，以根據活動的排程來鎖定目標。將結束日期保持空白，以繼續鎖定目標直到活動的結束日期和時間為止。

   您也可以將開始和結束日期都保持空白。此功能可讓您在多個活動中使用相同的對象（不製作對象副本），同時在活動層級控制開始和結束日期。

   >[!NOTE]
   >
   >考慮以下事項：
   >
   >* 開始/結束日期的時區會顯示為 GMT +/- NN:NN；其中 NN:NN 是 GMT 時差，會反映帳戶層級時區，而非訪客的時區。例如，加州時區會顯示為 GMT -08:00。
   >
   >* [!DNL Target]時間對象未考慮日光節約時間(DST)變更。 您必須手動重新儲存對象，以考慮DST變更。

1. （視條件而定）按一下&#x200B;**[!UICONTROL Set frequency]**&#x200B;以設定週期性模式，包括星期幾和時間。

   ![週與日劃分](assets/week_and_day_parting.png)

   例如，您可以使用[!UICONTROL Frequency]選項，只在您客服中心人員配備的日和小時向訪客顯示「立即聊天」選項。

   選取一或多個星期幾，然後設定開始和結束時間。視需要按一下&#x200B;**[!UICONTROL Add frequency]**&#x200B;以指定其他模式。

   >[!NOTE]
   >
   >[!UICONTROL Week and Day Parting]的時區會顯示為GMT +/- NN：NN；其中NN：NN是GMT時差，會反映帳戶層級時區，而非訪客的時區。 例如，加州太平洋日光節約時間的時區會顯示為GMT -07:00。

1. （選用）為對象設定其他規則。

   如有需要，您可以對每個規則重複步驟5。

1. 按一下 **[!UICONTROL Done]**。

## 訓練影片：建立對象![Overview badge](/help/main/assets/overview.png)

此影片包括關於使用對象類別的資訊。

* 建立客群
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

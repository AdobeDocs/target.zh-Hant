---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: 本節說明如何將Adobe Target行動應用程式活動資訊傳送至Adobe Analytics，以利臨機分段。
title: 傳送Adobe Target活動資訊至Adobe Analytics
feature: mobile implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 31%

---


# 將活動資訊傳送到 Adobe Analytics{#send-activity-information-to-adobe-analytics}

This section describes how to send [!DNL Target] mobile app activity information to Adobe [!DNL Analytics] for post hoc segmentation.

**必要條件**

* This integration requires that [!DNL Analytics] and [!DNL Target] are implemented using the mobile SDK.
* Ensure that your report suite is enabled to receive activity information from [!DNL Target].

   This is usually done by adding the [!DNL Target] client code to the [!DNL Analytics] report suite. 如果您正在使用 SiteCatalyst-Test&amp;Target 整合來處理網頁活動，該功能可能已啟用。如果您對這個步驟有任何問題，請連絡 Adobe 客戶服務。

1. 取得活動資訊。

   If you include a string like the following in your experience content, [!DNL Target] returns the activity information that you can send to [!DNL Analytics]:

   ```
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   請將體驗 json 程式碼中的文字取代為類似以下範例的內容:

   ```
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   In this example, a node with the variable `tntVal` is added to obtain the activity information. 請為其他體驗新增類似的程式碼，並附上適當標題和訊息。

   This string delivers a number (such as 115110:0:0) in the response from [!DNL Target]. 這表示活動ID、體驗ID和流量類型。 The following is a sample response from [!DNL Target]:

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. 剖析 JSON 物件。

   Parse the response that came back from [!DNL Target] in the callback. You can use `NSJSONSerialization` to parse this response and store it in a dictionary or an array.

   有關詳細資訊， [請參閱NSJSONSerialization文檔](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) 。

1. 將資料傳送到 [!DNL Analytics].

   將剖析後的活動資訊 (如前述回應中的 `tntVal`) 新增到 呼叫中的內容資料物件。[!DNL Analytics]This [!DNL Analytics] call containing the context data can be fired immediately or it can wait until the next [!DNL Analytics] call is fired.

   例如，它可以在 `targetLoadRequest` 呼叫的回呼中觸發:

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt` 是行動 SDK 中保留的事件索引鍵。The post-classification of the `tntVal` variable in [!DNL Analytics] works in the same way in the mobile SDK as it does on the web (JavaScript). After the information is processed in [!DNL Analytics], you should see activity and experience names in the [!DNL Analytics] interface.


---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: 本節說明如何將Adobe Target行動應用程式活動資訊傳送至Adobe Analytics，以利臨機分段。
title: 傳送活動資訊至Adobe Analytics
feature: Implement Mobile
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 30%

---


# 將活動資訊傳送到 Adobe Analytics{#send-activity-information-to-adobe-analytics}

本節說明如何傳送[!DNL Target]行動應用程式活動資訊至Adobe [!DNL Analytics]以進行臨機後區段。

**必要條件**

* 此整合需要[!DNL Analytics]和[!DNL Target]是使用行動SDK實作。
* 請確定您的報表套裝已啟用，可從[!DNL Target]接收活動資訊。

   這通常是透過將[!DNL Target]用戶端程式碼新增至[!DNL Analytics]報表套裝來完成。 如果您正在使用 SiteCatalyst-Test&amp;Target 整合來處理網頁活動，該功能可能已啟用。如果您對這個步驟有任何問題，請連絡 Adobe 客戶服務。

1. 取得活動資訊。

   如果您的體驗內容包含類似下列的字串，[!DNL Target]會傳回您可傳送至[!DNL Analytics]的活動資訊：

   ```javascript
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   請將體驗 json 程式碼中的文字取代為類似以下範例的內容:

   ```javascript
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   在此示例中，添加了變數`tntVal`的節點以獲取活動資訊。 請為其他體驗新增類似的程式碼，並附上適當標題和訊息。

   此字串會在[!DNL Target]的回應中傳遞一個數字（例如115110:0:0）。 這表示活動ID、體驗ID和流量類型。 以下是來自[!DNL Target]的範例回應：

   ```javascript
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. 剖析 JSON 物件。

   剖析回呼中從[!DNL Target]傳回的回應。 您可以使用`NSJSONSerialization`來剖析此回應，並將它儲存在字典或陣列中。

   有關詳細資訊，請參閱[NSJSONSerialization文檔](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error)。

1. 將資料傳送到 [!DNL Analytics].

   將剖析後的活動資訊 (如前述回應中的 `tntVal`) 新增到 呼叫中的內容資料物件。[!DNL Analytics]此[!DNL Analytics]呼叫包含上下文資料，可立即引發，或等到下一個[!DNL Analytics]呼叫引發為止。

   例如，它可以在 `targetLoadRequest` 呼叫的回呼中觸發:

   ```javascript
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt` 是行動 SDK 中保留的事件索引鍵。[!DNL Analytics]中`tntVal`變數的後置分類在行動SDK中的運作方式與在網頁上相同(JavaScript)。 在[!DNL Analytics]中處理資訊後，您應會在[!DNL Analytics]介面中看到活動和體驗名稱。


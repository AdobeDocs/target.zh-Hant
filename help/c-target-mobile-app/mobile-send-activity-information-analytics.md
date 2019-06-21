---
description: 本節說明如何將 Target 行動應用程式活動資訊傳送到 Adobe Analytics，以便進行 postAhoc 分段。
seo-description: 本節說明如何將 Target 行動應用程式活動資訊傳送到 Adobe Analytics，以便進行 postAhoc 分段。
seo-title: 將活動資訊傳送到 Adobe Analytics
title: 將活動資訊傳送到 Adobe Analytics
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 將活動資訊傳送到 Adobe Analytics{#send-activity-information-to-adobe-analytics}

本節說明如何將 Target 行動應用程式活動資訊傳送到 Adobe Analytics，以便進行 postAhoc 分段。

**必要條件**

* 本項整合要求使用行動 SDK 實作 Analytics 和 Target。
* 請確認您的報表套裝可接收 Target 傳送的活動資訊。

   通常只要將 Target 用戶端程式碼新增到 Analytics 報表套裝就能實現。如果您正在使用 SiteCatalyst-Test&amp;Target 整合來處理網頁活動，該功能可能已啟用。如果您對這個步驟有任何問題，請連絡 Adobe 客戶服務。

1. 取得活動資訊。

   如果您在體驗內容中加入類似以下範例的字串，Target 會傳回可供傳送到 Analytics 的促銷活動資訊:

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

   該範例新增含變數 &#39;`tntVal`&#39; 的節點來取得活動資訊。請為其他體驗新增類似的程式碼，並附上適當標題和訊息。

   該字串會在 Target 傳回的回應中提供一組數值 (如 115110:0:0)。其代表活動 ID、體驗 ID 及流量類型。以下是來自 Target 的範例回應:

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. 剖析 JSON 物件。

   剖析在回呼中從 Target 回傳的回應。您可以使用 NSJSONSerialization 來剖析這則回應，以及將回應儲存在字典或陣列中。

   如需詳細資訊，請參閱 [NSJSONSerialization 文件](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error)。
1. 將資料傳送到 Analytics。

   將剖析後的活動資訊 (如前述回應中的 `tntVal`) 新增到 Analytics 呼叫中的內容資料物件。該 Analytics 呼叫含有內容資料，能立即觸發或等到下次 Analytics 呼叫時再觸發。

   例如，它可以在 `targetLoadRequest` 呼叫的回呼中觸發:

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt` 是行動 SDK 中保留的事件索引鍵。Analytics 中 `tntVal` 變數的後續類別，在行動 SDK 中的作用與在網頁 (JavaScript) 上相同。等到 Analytics 處理資訊後，您應該能在 Analytics 介面中看到活動和體驗名稱。


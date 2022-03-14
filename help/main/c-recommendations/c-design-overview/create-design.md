---
keywords: 建議設計;建立設計;複製設計
description: 瞭解如何建立Adobe [!DNL Target] Recommendations設計使用預設設計，或建立定制設計以最適合頁面佈局。
title: 如何在Recommendations建立設計？
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 30%

---

# ![PREMIUM](/help/main/assets/premium.png) 建立設計

設計可定義建議出現在頁面上的方式。

您可以使用預設的設計來建立 [!UICONTROL Recommendations] 設計，或建立自訂的設計。的 **[!UICONTROL Recommendations>設計]** 螢幕同時顯示預設設計卡和在您的帳戶中建立的所有設計。

使用設計時，請牢記以下資訊：

* 可以使用預設設計建立建議設計，也可以建立自定義設計。
* 不能編輯或刪除預設設計。
* 可以編輯、複製或刪除自定義設計。
* 要基於預設設計建立設計，必須先複製設計，然後編輯副本。

此圖顯示了預設1 x 4設計：

![1 x 4預設設計](/help/main/c-recommendations/c-design-overview/assets/default-design.png)

此插圖顯示自定義設計：

![定制設計](/help/main/c-recommendations/c-design-overview/assets/custom-design.png)

可以在活動建立過程中從Visual Experience Composer(VEC)或活動建立之外的設計庫建立設計。 以下部分假定您正在從庫中建立設計，但步驟相似。

## 建立設計

可以基於預設設計建立設計，也可以建立自定義設計。

### 基於預設設計建立設計

1. 按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 設計]** 顯示 [!UICONTROL 設計] 的下界。

   ![設計庫](/help/main/c-recommendations/c-design-overview/assets/design-library.png)

1. 將滑鼠移到要建立的設計的卡上，然後按一下 **[!UICONTROL 複製]** 表徵圖

   ![](assets/Card_CopyDesign.png)

   的 [!UICONTROL 建立設計] 對話框。

   ![](assets/createDesign.png)

1. 在 **[!UICONTROL 資訊]** 面板，添加 **[!UICONTROL 內容名稱]** 和可選的預覽影像，以在設計卡上顯示。

   使用預設設計時，設計名稱和「複製」(Copy)將出現在 **[!UICONTROL 內容名稱]** 的子菜單。 您可以編輯名稱。也可以選擇要在設計卡上顯示的影像。

1. （條件）編輯設計 **[!UICONTROL 代碼]**&#x200B;按需。

   Recommendation 設計使用開放式原始碼 Velocity 設計語言。有關Velocity的資訊，請參閱 [https://velocity.apache.org](https://velocity.apache.org) 在 [使用Velocity定制設計](/help/main/c-recommendations/c-design-overview/customizing-a-template.md)。

   設計可以是 HTML 或非 HTML。根據預設，HTML 設計會以`<div>`標籤包住，以允許在 Web 環境中進行點擊追蹤。非 HTML 設計用於非 Web 環境，在其中無法進行點擊追蹤。滑動 [!UICONTROL HTML設計] 切換到「off」位置以使用非HTML代碼。

   >[!NOTE]
   >
   >在設計中可以引用的最大圖元數為99。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

### 建立自訂設計

1. 按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 設計]** 顯示 [!UICONTROL 設計] 的下界。

1. 按一下 **[!UICONTROL 建立設計]**。

   如果要將新定制設計基於現有設計，請將滑鼠置於所需設計之上，然後按一下 [!UICONTROL 複製] 表徵圖 然後，可編輯副本以建立新的自定義設計。

1. 添加 **[!UICONTROL 內容名稱]** 和可選預覽影像。

1. （條件）編輯設計 **[!UICONTROL 代碼]**&#x200B;按需。

   有關詳細資訊，請參閱上面步驟4中的資訊。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 編輯、複製或刪除設計

請記住，不能編輯或複製預設設計；只能複製預設設計。

將滑鼠懸停在 [!UICONTROL 設計] 庫，然後按一下相應表徵圖：編輯、複製或刪除。

![懸停錶徵圖用於設計](/help/main/c-recommendations/c-design-overview/assets/hover-icons-design.png)

可複製現有設計以建立重複設計，然後可以修改。 這樣，您就可以以較少的工作量建立類似的設計。

請注意整個客戶都有設計。 請確保在刪除設計之前考慮此問題。 無法恢復已刪除的設計。

## JSON 範例 {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

以下示例說明如何通過基於表單的編輯器配置活動時返回JSON響應。

1. 從設計庫內或基於表單的工作流內建立設計。 如果在Visual Experience Composer(VEC)工作流中嘗試執行此操作，則不能建立HTML設計以外的任何內容，該設計包裝在 `<div>` 用於按一下跟蹤目的。

1. 確定「HTML 設計」選項已關閉:

   ![](assets/html_design_toggle.png)

1. 以下代碼是可貼上到設計中的示例：

   ```javascript
       #* 
       * "Return a simple list of recommended entity ids"   
       *#
   
       {   
         "notes":{   
         "purpose": "Return a simple list of recommended entity ids",   
         "use-case": "Use this approach if you prefer to do a real-time lookup of entity attribute details (such as inventory, price, rating) from another system (such as a CMS, PIM or ecommerce platform)",   
         "version": "01"   
         },   
         "recommendedItems": {   
           "key": "$key.id",   
           "slot-01": "$entity1.id",   
           "slot-02": "$entity2.id",   
           "slot-03": "$entity3.id",   
           "slot-04": "$entity4.id",   
           "slot-05": "$entity5.id",   
           "slot-06": "$entity6.id",   
           "slot-07": "$entity7.id",   
           "slot-08": "$entity8.id",   
           "slot-09": "$entity9.id",   
           "slot-10": "$entity10.id"   
         }   
       }  
   ```

1. 設定基於表單 [!DNL Recommendations] 使用此設計的活動。

   1. 導航到 **[!UICONTROL 活動]** 的子菜單。
   1. 按一下&#x200B;**[!UICONTROL 「建立活動」]**>**[!UICONTROL 「Recommendations」]**。
   1. 下 **[!UICONTROL 選擇體驗作曲家]**&#x200B;選中 **[!UICONTROL 窗體]**，然後按一下 **[!UICONTROL 下一個]**。
   1. 在位置下，輸入文字: &quot;Sample_Recs_Response&quot;
   1. 在&#x200B;**[!UICONTROL 「預設內容」]**&#x200B;下，按向下箭頭，然後按一下&#x200B;**[!UICONTROL 「新增建議」]**。
   1. 選擇頁面類型。這會決定下一個畫面的起始篩選。
   1. 選取條件卡，然後按&#x200B;**[!UICONTROL 「下一步」]**。
   1. 選取在上一步中建立的設計，然後按一下 **[!UICONTROL 下一個]**。
   1. 完成設定程序。
   1. 按一下&#x200B;**[!UICONTROL 「非使用中」]**&#x200B;旁的向右箭頭，然後選取&#x200B;**[!UICONTROL 「啟動」]**。

1. 在設定並啟動活動之後，您可以設定請求範例來取回全新的 JSON 回應。

   從您保存活動時起， [!DNL Target] 將需要構建模型以支援所選條件配置。 根據許多因素而定，這需要一些時間。模型建立後就會顯示結果。

   例如:

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   where

   | 參數 | 值 |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | 目標客戶端代碼(可在/help/target/products.html#recsSettings >RecommendationsAPI令牌>客戶端代碼上找到。 |
   | `[YOUR_MBOX_NAME]` | 您在基於表單的Recommendations的「位置」部分中選擇的名稱，在本例中為Sample_Recs_Response。 |
   | `[ENTITY_ID` | 目錄中之項目的 `entity.id`。 |
   | `[AT_PROPERTY_TOKEN]` | (可選) 如果您已在活動設定期間選取「屬性」(「企業權限」的部分)，則新增。 |

當演算法執行之後，而且也有結果，則回應會如下所示:

![](assets/json_recommendation.png){width=&quot;575px&quot;}

## 其他JSON對象提示和技巧 {#section_C305673C68944749969DB239E3221DC2}

您也可以使用下列語法來設定設計，只傳回一份簡單的以逗號分隔的項目清單:

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

或者，您可以在回應中傳送其他資訊。下列程式碼檔案是較複雜的範例，不只傳回實體 ID，還有其相關聯的位置 (訂單)。此設計示例還返回活動詳細資訊、目標配置檔案詳細資訊（如果適用）和其他 `entity.attributes` 與返回的項關聯。

```javascript
    {   
     "adobeRecommendations": {   
      "notes": {   
       "purpose": "Return a list of entity ids with their associated entity.attributes",   
       "use-case": "Use this approach to avoid looking up attribute details after receiving a response from Target",   
       "version": "01"   
      },   
      "recommendedItems": {   
       "slot-01": "$entity1.id",   
       "slot-02": "$entity2.id",   
       "slot-03": "$entity3.id",   
       "slot-04": "$entity4.id",   
       "slot-05": "$entity5.id",   
       "slot-06": "$entity6.id",   
       "slot-07": "$entity7.id",   
       "slot-08": "$entity8.id",   
       "slot-09": "$entity9.id",   
       "slot-10": "$entity10.id"   
      },   
      "activityDetails": {   
       "mbox.name": "email-mbox",   
       "campaign.name": "\${campaign.name}",   
       "campaign.id": "\${campaign.id}",   
       "campaign.recipe.name": "\${campaign.recipe.name}",   
       "campaign.recipe.id": "\${campaign.recipe.id}",   
       "offer.name": "\${offer.name}",   
       "offer.id": "\${offer.id}",   
       "criteria.title": "$criteria.title",   
       "algorithm.name": "$algorithm.name",   
       "algorithm.dayCount": "$algorithm.dayCount"   
      },   
      "visitorProfile": {   
       "profile.favorite-category": "\${profile.favorite-category}",   
       "profile.test": "\${profile.test}",   
       "user.endpoint.lastPurchasedEntity": "\${user.endpoint.lastPurchasedEntity}",   
       "user.endpoint.lastViewedEntity": "\${user.endpoint.lastViewedEntity}",   
       "user.endpoint.mostViewedEntity": "\${user.endpoint.mostViewedEntity}",   
       "user.endpoint.categoryAffinity": "\${user.endpoint.categoryAffinity}",   
       "profile.geolocation.city": "\${profile.geolocation.city}",   
       "profile.geolocation.dma": "\${profile.geolocation.dma}",   
       "profile.geolocation.state": "\${profile.geolocation.state}",   
       "profile.geolocation.country": "\${profile.geolocation.country}",   
       "profile.sessionCount": "\${profile.sessionCount}",   
       "profile.averageDaysBetweenVisits": "\${profile.averageDaysBetweenVisits}",   
       "profile.browserTime": "\${profile.browserTime}",   
       "user.activeActivities": "\${user.activeActivities}",   
       "user.pcId": "\${user.pcId}",   
       "user.isFirstSession": "\${user.isFirstSession}",   
       "user.isNewSession": "\${user.isNewSession}",   
       "user.header": "\${user.header}",   
       "user.parameter": "\${user.parameter}"   
      },   
      "recKey": {   
       "recKeyDetails": {   
        "id": "$key.id",   
        "name": "$key.name",   
        "category": "$key.category",   
        "pageUrl": "$key.pageUrl",   
        "thumbnailUrl": "$key.thumbnailUrl"   
       }   
      },   
      "recDetailedResults": {   
       "recEntity1Details": {   
        "id": "$entity1.id",   
        "name": "$entity1.name",   
        "category": "$entity1.category",   
        "pageUrl": "$entity1.pageUrl",   
        "thumbnailUrl": "$entity1.thumbnailUrl"   
       },   
       "recEntity2Details": {   
        "id": "$entity2.id",   
        "name": "$entity2.name",   
        "category": "$entity2.category",   
        "pageUrl": "$entity2.pageUrl",   
        "thumbnailUrl": "$entity2.thumbnailUrl"   
       },   
       "recEntity3Details": {   
        "id": "$entity3.id",   
        "name": "$entity3.name",   
        "category": "$entity3.category",   
        "pageUrl": "$entity3.pageUrl",   
        "thumbnailUrl": "$entity3.thumbnailUrl"   
       },   
       "recEntity4Details": {   
        "id": "$entity4.id",   
        "name": "$entity4.name",   
        "category": "$entity4.category",   
        "pageUrl": "$entity4.pageUrl",   
        "thumbnailUrl": "$entity4.thumbnailUrl"   
       },   
       "recEntity5Details": {   
        "id": "$entity5.id",   
        "name": "$entity5.name",   
        "category": "$entity5.category",   
        "pageUrl": "$entity5.pageUrl",   
        "thumbnailUrl": "$entity5.thumbnailUrl"   
       },   
       "recEntity6Details": {   
        "id": "$entity6.id",   
        "name": "$entity6.name",   
        "category": "$entity6.category",   
        "pageUrl": "$entity6.pageUrl",   
        "thumbnailUrl": "$entity6.thumbnailUrl"   
       },   
       "recEntity7Details": {   
        "id": "$entity7.id",   
        "name": "$entity7.name",   
        "category": "$entity7.category",   
        "pageUrl": "$entity7.pageUrl",   
        "thumbnailUrl": "$entity7.thumbnailUrl"   
       },   
       "recEntity8Details": {   
        "id": "$entity8.id",   
        "name": "$entity8.name",   
        "category": "$entity8.category",   
        "pageUrl": "$entity8.pageUrl",   
        "thumbnailUrl": "$entity8.thumbnailUrl"   
       },   
       "recEntity9Details": {   
        "id": "$entity9.id",   
        "name": "$entity9.name",   
        "category": "$entity9.category",   
        "pageUrl": "$entity9.pageUrl",   
        "thumbnailUrl": "$entity9.thumbnailUrl"   
       },   
       "recEntity10Details": {   
        "id": "$entity10.id",   
        "name": "$entity10.name",   
        "category": "$entity10.category",   
        "pageUrl": "$entity10.pageUrl",   
        "thumbnailUrl": "$entity10.thumbnailUrl"   
       }   
      }   
     }   
    }  
```

## 培訓視頻：在Recommendations建立定制設計(3:20) ![概述徽章](/help/main/assets/overview.png)

此影片包含下列資訊:

* 建立自訂設計
* 瞭解如何參考設計中的顯示變數

>[!VIDEO](https://video.tv.adobe.com/v/27687)

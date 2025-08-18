---
keywords: 建議設計;建立設計;複製設計
description: 瞭解如何使用預設設計或透過建立自訂設計以最符合您的頁面版面配置來建立 [!DNL Target Recommendations] 設計。
title: 如何在Recommendations建立設計？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 19%

---

# 建立設計

設計可定義建議出現在頁面上的方式。

您可以使用預設設計或建立自訂設計來建立[!UICONTROL Recommendations]設計。 **[!UICONTROL Recommendations > Designs]**&#x200B;畫面會顯示預設設計卡片以及在您的帳戶中建立的任何設計。

使用設計時，請牢記下列資訊：

* 您可以使用預設設計來建立建議設計，也可以建立自訂設計。
* 您無法編輯或刪除預設設計。
* 您可以編輯、複製或刪除自訂設計。
* 若要根據預設設計建立設計，您必須先複製設計，然後再編輯副本。

下圖顯示預設的1 x 4設計：

![1 x 4預設設計](/help/main/c-recommendations/c-design-overview/assets/default-design.png)

下圖顯示自訂設計：

![自訂設計](/help/main/c-recommendations/c-design-overview/assets/custom-design.png)

您可以在活動建立過程中從[!UICONTROL Visual Experience Composer] (VEC)內或在活動建立之外從設計程式庫建立設計。 以下各節假設您是從資料庫中建立設計，但步驟類似。

## 建立設計

您可以根據預設設計建立設計，也可以建立自訂設計。

### 根據預設設計建立設計

1. 按一下「**[!UICONTROL Recommendations]** > **[!UICONTROL Designs]**」以顯示[!UICONTROL Designs]資料庫。


1. 按一下您想要建立的設計的[更多動作]圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下&#x200B;**[!UICONTROL Copy]**。

   [!UICONTROL Create Design]對話方塊隨即顯示。

1. 輸入&#x200B;**[!UICONTROL  Name]**&#x200B;和選用的預覽影像以顯示於設計卡片。

   使用預設設計時，設計名稱和「Copy」會出現在&#x200B;**[!UICONTROL Content Name]**&#x200B;欄位中。 您可以編輯名稱。您也可以選取要在設計卡片上顯示的影像。

1. （視條件而定）視需要編輯設計&#x200B;**[!UICONTROL Code]**。

   Recommendation 設計使用開放式原始碼 Velocity 設計語言。有關Velocity的資訊，請參閱[https://velocity.apache.org](https://velocity.apache.org)和[使用Velocity自訂設計](/help/main/c-recommendations/c-design-overview/customizing-a-template.md)。

   設計可以是 HTML 或非 HTML。依預設，HTML設計會以`<div>`標籤包裝，以允許在Web環境中進行點選追蹤。 非HTML設計適用於無法進行點選追蹤的非Web環境。 將[!UICONTROL HTML Design]切換滑至「關閉」位置即可使用非HTML程式碼。

   >[!NOTE]
   >
   >可在設計中參照（硬式編碼或透過回圈）的實體數上限為99。

1. 按一下 **[!UICONTROL Create]**。

### 建立自訂設計

1. 按一下「**[!UICONTROL Recommendations]** > **[!UICONTROL Designs]**」以顯示[!UICONTROL Designs]資料庫。

1. 按一下 **[!UICONTROL Create Design]**。

   如果您想要讓新的自訂設計以現有設計為基礎，請按一下您要建立的設計的[!UICONTROL More Actions]圖示（ ![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下[!UICONTROL Copy]。 然後您可以編輯復本以建立新的自訂設計。

1. 新增&#x200B;**[!UICONTROL Name]**&#x200B;和選用的預覽影像。

1. （視條件而定）視需要編輯設計&#x200B;**[!UICONTROL Code]**。

   如需詳細資訊，請參閱上述步驟4中的資訊。

1. 按一下 **[!UICONTROL Create]**。

## 編輯、複製或刪除設計

請記住，您無法編輯或複製預設設計；您只能複製預設設計。

按一下您要編輯或刪除的設計的[!UICONTROL More Actions]圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg)），然後按一下適當的圖示： [!UICONTROL Edit]、[!UICONTROL Copy]或[!UICONTROL Delete]。

您可以複製現有設計來建立複製設計，然後可以修改設計。 此程式可讓您輕鬆建立類似設計。

請注意，設計在整個帳戶中皆可使用。 刪除設計之前，請務必考量各帳戶的使用情況。 已刪除的設計無法復原。

## JSON 範例 {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

下列範例說明在透過[表單式編輯器](/help/main/c-experiences/form-experience-composer.md)設定活動時，如何傳回JSON回應。

1. 從[!UICONTROL Design library]內或表單式工作流程內建立設計。 如果您嘗試在[!UICONTROL Visual Experience Composer] (VEC)工作流程中建立設計，則無法建立除了HTML設計以外的任何專案，此設計會包裝在`<div>`中以供點選追蹤之用。

1. 確定「HTML 設計」選項已關閉:

   ![html_design_toggle image](assets/html_design_toggle.png)

1. 下列程式碼為貼到設計中的範例：

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

1. 設定使用此設計的表單式[!DNL Recommendations]活動。

   1. 導覽至&#x200B;**[!UICONTROL Activities]**&#x200B;頁面。
   1. 按一下&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL Recommendations]**。
   1. 在&#x200B;**[!UICONTROL Choose Experience Composer]**&#x200B;下，選取&#x200B;**[!UICONTROL Form]**，然後按一下&#x200B;**[!UICONTROL Next]**。
   1. 在位置下，輸入文字: &quot;Sample_Recs_Response&quot;
   1. 在&#x200B;**[!UICONTROL Default Content]**&#x200B;下，按一下向下箭頭，然後按一下&#x200B;**[!UICONTROL Add Recommendation]**。
   1. 選擇頁面類型。這會決定下一個畫面的起始篩選。
   1. 選取條件卡，然後按一下&#x200B;**[!UICONTROL Next]**。
   1. 選取您在上一步建立的設計，然後按一下&#x200B;**[!UICONTROL Next]**。
   1. 完成設定程序。
   1. 按一下&#x200B;**[!UICONTROL Inactive]**&#x200B;旁的向右箭頭，然後選取&#x200B;**[!UICONTROL Activate]**。

1. 在設定並啟動活動之後，您可以設定請求範例來取回全新的 JSON 回應。

   從您儲存活動開始，[!DNL Target]需要建立模型以支援選取的條件設定。 根據許多因素，此程式可能需要一些時間。 模型建立後就會顯示結果。

   例如:

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   where

   | 參數 | 值 |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | Target使用者端代碼(位於/help/target/products.html#recsSettings > Recommendations API Token >使用者端代碼)。 |
   | `[YOUR_MBOX_NAME]` | 您在表單式「建議」的「位置」區段中選取的名稱，此例子中是Sample_Recs_Response。 |
   | `[ENTITY_ID` | 目錄中之項目的 `entity.id`。 |
   | `[AT_PROPERTY_TOKEN]` | (可選) 如果您已在活動設定期間選取「屬性」(「企業權限」的部分)，則新增。 |

當演算法執行之後，而且也有結果，則回應會如下所示:

![json_recommendation影像](assets/json_recommendation.png){width="575px"}

## 其他JSON物件秘訣與技巧 {#section_C305673C68944749969DB239E3221DC2}

您也可以使用下列語法設定設計，傳回簡單的逗號分隔專案清單：

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

或者，您可以在回應中傳送其他資訊。下列程式碼檔案是較複雜的範例，不只傳回實體 ID，還有其相關聯的位置 (訂單)。此設計範例也傳回活動詳細資料、[!UICONTROL Target Profile]詳細資料（如適用），以及與傳回的專案相關聯的其他`entity.attributes`。

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

## 訓練影片：在Recommendations (3:20) ![Overview badge](/help/main/assets/overview.png)中建立自訂設計

此影片包含下列資訊:

* 建立自訂設計
* 瞭解如何在設計中參考顯示變數

>[!VIDEO](https://video.tv.adobe.com/v/27687)

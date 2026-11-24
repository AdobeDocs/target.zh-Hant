---
keywords: 建議設計;建立設計;複製設計
description: 瞭解如何使用預設設計或透過建立自訂設計以最符合頁面版面配置來建立[!DNL Target Recommendations]設計。
title: 建立設計
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
TQID: 'https://experienceleague.adobe.com/GLWcKaQGl6TmL9i7LYUiYepg6SkAjBtL-78-zlaWCTk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 11%
---
# 建立設計 {#create-design}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在[!DNL Adobe Target Recommendations]中建立、編輯、複製和刪除設計，以及如何以JSON傳回建議。

>[!ENDSHADEBOX]

設計可定義建議出現在頁面上的方式。 設計可以基於預設設計或建立為自訂設計。 **[!UICONTROL Recommendations]** > **[!UICONTROL 設計]**&#x200B;畫面會顯示預設設計卡片以及在帳戶中建立的設計。

* 無法編輯或刪除預設設計。
* 可以編輯、複製或刪除自訂設計。
* 若要根據預設設計建立設計，請先複製設計，然後編輯副本。

在活動建立過程中，可以從&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)內，或在活動建立之外從設計程式庫建立設計。 下列步驟假設設計是從程式庫建立的，但步驟類似。

## 從程式庫建立設計 {#steps}

1. 按一下「**[!UICONTROL 建議]** > **[!UICONTROL 設計]**」以顯示&#x200B;**[!UICONTROL 設計]**&#x200B;資料庫。

1. 以下列其中一種方式開始設計：

   * 若要讓設計以預設設計或現有設計為基礎，請按一下該設計的「更多動作」圖示（ ![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下「**[!UICONTROL 複製]**」。 **[!UICONTROL 建立設計]**&#x200B;對話方塊隨即顯示。 已編輯的復本會變成新的自訂設計。
   * 若要從頭開始建立自訂設計，請按一下[建立設計]。**&#x200B;**

     ![反白顯示[建立設計]按鈕的設計資料庫](../assets/design_1.png)

1. 輸入&#x200B;**[!UICONTROL 名稱]**，並選取要顯示在設計卡片上的選擇性預覽影像。

   使用預設設計時，**[!UICONTROL 內容名稱]**&#x200B;欄位中會出現設計名稱，後面接著「複製」。 名稱可以編輯。

1. （視條件而定）視需要編輯設計&#x200B;**[!UICONTROL 程式碼]**。

   Recommendation 設計使用開放式原始碼 Velocity 設計語言。 如需Velocity的相關資訊，請參閱[https://velocity.apache.org](https://velocity.apache.org)和[使用Velocity](/help/main/c-recommendations/c-design-overview/customizing-a-template.md)自訂設計。

   設計可以是 HTML 或非 HTML。 依預設，HTML設計會以`<div>`標籤包裝，以允許在Web環境中進行點選追蹤。 非 HTML 設計用於非 Web 環境，在其中無法進行點擊追蹤。 滑動&#x200B;**[!UICONTROL HTML設計]**&#x200B;切換至「關閉」位置，使用非HTML程式碼。

   >[!NOTE]
   >
   >可在設計中參照（硬式編碼或透過回圈）的實體數上限為99。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

1. 按一下設計的「更多動作」圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ）以編輯、複製或刪除，然後按一下適當的選項： **[!UICONTROL 編輯]**、**[!UICONTROL 複製]**&#x200B;或&#x200B;**[!UICONTROL 刪除]**。

   ![開啟[更多動作]功能表的設計程式庫，顯示[編輯]、[複製]和[刪除]](../assets/design_2.png)

設計在整個帳戶中皆可使用。 刪除設計之前，必須先考慮跨帳戶的使用情況。 已刪除的設計無法復原。

## JSON範例 {#json-example}

下列範例說明當活動設定為[表單式編輯器](/help/main/c-experiences/form-experience-composer.md)時，如何傳回JSON回應。

1. 從&#x200B;**[!UICONTROL 設計資料庫]**&#x200B;或表單式工作流程中建立設計。 在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)工作流程中建立的設計只能是HTML設計，其包裝在`<div>`中以供點選追蹤之用。

1. 請確定&#x200B;**[!UICONTROL HTML設計]**&#x200B;選項已關閉：

   ![HTML設計切換至關閉位置](/help/main/c-recommendations/c-design-overview/assets/html_design_toggle.png)

1. 將類似下列範例的程式碼貼到設計中：

   +++ 傳回實體ID清單的設計程式碼範例

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

   +++

1. 設定使用此設計的表單式[!DNL Recommendations]活動。

   +++ 瞭解如何設定表單式[!DNL Recommendations]活動 

   1. 導覽至&#x200B;**[!UICONTROL 活動]**&#x200B;頁面。
   1. 按一下&#x200B;**[!UICONTROL 建立活動]** > **[!UICONTROL 建議]**。
   1. 在「**[!UICONTROL 選擇體驗撰寫器]**」下，選取「**[!UICONTROL 表單]**」，然後按一下「**[!UICONTROL 下一步]**」。
   1. 在「位置」下，輸入文字「Sample_Recs_Response」。
   1. 在&#x200B;**[!UICONTROL 「預設內容」]**&#x200B;下，按向下箭頭，然後按一下&#x200B;**[!UICONTROL 「新增建議」]**。
   1. 選擇頁面類型。 這會決定下一個畫面的起始篩選。
   1. 選取條件卡，然後按&#x200B;**[!UICONTROL 「下一步」]**。
   1. Select在上一步建立的設計，然後按一下&#x200B;**[!UICONTROL 下一步]**。
   1. 完成設定程序。
   1. 按一下&#x200B;**[!UICONTROL 「非使用中」]**&#x200B;旁的向右箭頭，然後選取&#x200B;**[!UICONTROL 「啟動」]**。

   +++

1. 設定並啟動活動後，可以設定範例請求以取得乾淨的JSON回應。

   從儲存活動開始，[!DNL Target]需要建立模型以支援選取的條件設定。 根據許多因素，此程式可能需要一些時間。 一旦建立模型，就會顯示結果。

   例如:

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   where

   | 參數 | 值 |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | [!DNL Target]使用者端代碼（位於#recsSettings > Recommendations API Token >使用者端代碼）。 |
   | `[YOUR_MBOX_NAME]` | 在表單式Recommendations活動的「位置」區段中選取的名稱，在此案例中是Sample_Recs_Response。 |
   | `[ENTITY_ID]` | 目錄中的專案`entity.id`。 |
   | `[AT_PROPERTY_TOKEN]` | （選用）在活動設定期間選取屬性（企業許可權的一部分）時新增。 |

演演算法執行完畢且結果可用後，回應會如下所示：

包含建議專案的![JSON回應](/help/main/c-recommendations/c-design-overview/assets/json_recommendation.png){width="575px"}

## 其他JSON物件提示 {#json-tips}

透過使用下列語法設定設計，也可以傳回簡單的逗號分隔專案清單：

```
$entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

回應中也可傳送其他資訊。 下列程式碼是較複雜的範例，不只傳回實體ID及其關聯位置（訂單），還傳回更多內容。 此設計範例也傳回活動詳細資料、**[!UICONTROL 目標設定檔]**&#x200B;詳細資料（如適用），以及與傳回的專案相關聯的其他`entity.attributes`。

+++ 傳回活動、設定檔和實體詳細資訊的設計程式碼範例

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

+++


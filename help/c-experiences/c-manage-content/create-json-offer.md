---
keywords: remote offer;create remote offer
description: 在Adobe Target的選件程式庫中建立JSON選件，以便用於表單型體驗撰寫器。
title: 建立 JSON 選件
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 91%

---


# 建立 JSON 選件{#create-json-offers}

在[!DNL Adobe Target]的[!UICONTROL 選件程式庫]中建立JSON選件，以用於[!UICONTROL 表單式體驗撰寫器]。

JSON 選件可用於表單式活動中，藉以啟用使用案例，此時 Target 需要決定以 JSON 格式傳送選件，供 SPA 架構或伺服器端整合取用。

使用 JSON 選件時，請考量下列資訊:

* JSON 選件目前只可用於 AB 和 XT 活動。
* JSON 選件只能用在表單式活動中。
* 當您使用「伺服器端 API」、「行動裝置 SDK」或 NodeJS SDK 時，可直接擷取 JSON 選件。
* 在瀏覽器中，「只能」透過 at.js 1.2.3 (或更新版) 和以下方法擷取 JSON 選項: 使用 [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md)，需利用 `setJson` 動作來篩選動作。
* JSON 選件是以原生 JSON 物件提供，而不是字串。這些物件的取用者不再需要將物件當作字串來處理，再轉換成 JSON 物件。
* 不同於其他選件 (例如 HTML 選件)，JSON 選件不會自動套用，因為 JSON 選件不是視覺化選件。開發人員必須撰寫程式碼來明確利用此方法取得選件: [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md)。
* 使用 mbox.js 時不支援 JSON 選件。

## 建立 JSON 選件 {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. 按一下&#x200B;**[!UICONTROL 「選件」]**，然後選取&#x200B;**[!UICONTROL 「代碼選件」]**&#x200B;索引標籤。
1. 按一下「**[!UICONTROL 建立]** > **[!UICONTROL JSON 選件]**」。

   ![](assets/offer-json.png)

1. 輸入選件名稱。
1. 在&#x200B;**[!UICONTROL 「程式碼」]**&#x200B;方塊中，輸入或貼上 JSON 程式碼。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 範例 {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

只有在使用表單式體驗撰寫器建立的活動中才支援 JSON 選件。目前只有透過直接呼叫 API 才能使用 JSON 選件。

其範例如下:

```json
adobe.target.getOffer({ 
  mbox: "some-mbox", 
  success: function(actions) { 
    console.log('Success', actions); 
  }, 
  error: function(status, error) { 
    console.log('Error', status, error); 
  } 
});
```

傳給成功回呼的動作是物件陣列。假設有單一 JSON 選件，其內容為:

```json
{ 
  "demo": {"a": 1, "b": 2} 
}
```

動作陣列會有此結構:

```json
[ 
 { 
   action: "setJson", 
   content: [{ 
     "demo": {"a": 1, "b": 2} 
   }] 
 }  
]
```

若要擷取 JSON 選件，請逐一查看動作，尋找含有 `setJson` 動作的動作，然後查一查看內容陣列。

## 使用案例 {#section_85B07907B51A43239C8E3498EF58B1E5}

假設下列 JSON 選件傳送至您的網頁:

```json
{ 
    "_id": "5a65d24d8fafc966921e9169", 
    "index": 0, 
    "guid": "7c006504-c6f7-468d-a46f-f72531ea454c", 
    "isActive": true, 
    "balance": "$2,075.06", 
    "picture": "https://placehold.it/32x32", 
    "tags": [ 
      "esse", 
      "commodo", 
      "excepteur", 
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      }, 
    ], 
    "greeting": "Hello, Stephenson Fernandez! You have 4 unread messages.", 
    "favoriteFruit": "strawberry" 
} 
  
```

下列程式碼顯示如何存取「greeting」屬性:

```json
adobe.target.getOffer({   
  "mbox": "name_of_mbox", 
  "params": {}, 
  "success": function(offer) {           
        console.log(offer[0].content[0].greeting); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

## 依 JSON 選件類型來篩選選件  {#section_52533555BCE6420C8A95EB4EB8907BDE}

您可以按一下&#x200B;**[!UICONTROL 「類型」]**&#x200B;下拉式清單，然後選取 **[!UICONTROL JSON]** 核取方塊，依 JSON 選件類型來篩選「選件資料庫」。

![](assets/offer-json-filter.png)


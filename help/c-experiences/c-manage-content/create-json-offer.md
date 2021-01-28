---
keywords: remote offer;create remote offer
description: 如何建立JSON選件？
title: 建立 JSON 選件
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 16b63ca221ef3a69dcb5b297b2164dc7bea864e8
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 57%

---


# 建立 JSON 選件{#create-json-offers}

在[!DNL Adobe Target]的[!UICONTROL 選件程式庫]中建立JSON選件，以用於[!UICONTROL 表單式體驗撰寫器]。

JSON選件可用於表單型活動中，啟用需要[!DNL Target]決策的使用案例，以傳送JSON格式的選件，以便在SPA架構或伺服器端整合中使用。

## JSON考量事項

使用 JSON 選件時，請考量下列資訊:

* JSON選件目前僅適用於[!UICONTROL A/B Test]和[!UICONTROL 體驗定位](XT)活動。
* JSON選件只能用於[表單型活動](/help/c-experiences/form-experience-composer.md)。
* 當您使用「伺服器端 API」、「行動裝置 SDK」或 NodeJS SDK 時，可直接擷取 JSON 選件。
* 在瀏覽器中，「只能」透過 at.js 1.2.3 (或更新版) 和以下方法擷取 JSON 選項: 使用 [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md)，需利用 `setJson` 動作來篩選動作。
* JSON 選件是以原生 JSON 物件提供，而不是字串。這些物件的取用者不再需要將物件當作字串來處理，再轉換成 JSON 物件。
* 不同於其他選件 (例如 HTML 選件)，JSON 選件不會自動套用，因為 JSON 選件不是視覺化選件。開發人員必須撰寫程式碼來明確利用此方法取得選件: [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md)。
* 使用 mbox.js 時不支援 JSON 選件。

## 建立JSON選件{#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. 按一下「**[!UICONTROL 選件]** > **[!UICONTROL 程式碼選件]**」。

   ![選件>程式碼選件標籤](/help/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. 按一下「**[!UICONTROL 建立]** > **[!UICONTROL JSON 選件]**」。

   ![](assets/offer-json.png)

1. 輸入選件名稱。
1. 在&#x200B;**[!UICONTROL 「程式碼」]**&#x200B;方塊中，輸入或貼上 JSON 程式碼。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## JSON範例{#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

JSON選件僅在使用[表單型體驗撰寫器](/help/c-experiences/form-experience-composer.md)建立的活動中受支援。 目前只有透過直接呼叫 API 才能使用 JSON 選件。

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

若要擷取JSON選件，請重複執行動作，並尋找具有`setJson`動作的動作，然後重複執行內容陣列。

## 使用案例{#section_85B07907B51A43239C8E3498EF58B1E5}

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

## 依JSON選件類型{#section_52533555BCE6420C8A95EB4EB8907BDE}篩選選件

您可以按一下&#x200B;**[!UICONTROL Type]**&#x200B;下拉式清單，然後選取&#x200B;**[!UICONTROL JSON]**&#x200B;核取方塊，依JSON選件類型篩選[!UICONTROL 選件]程式庫。

![](assets/offer-json-filter.png)


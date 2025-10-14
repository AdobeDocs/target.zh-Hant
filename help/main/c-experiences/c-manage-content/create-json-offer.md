---
keywords: json選件；建立json選件
description: 瞭解如何建立JSON選件以用於[!UICONTROL Form-Based Experience Composer]。
title: 如何建立JSON選件？
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 25%

---

# 建立 JSON 產品建議

在[!UICONTROL Offer Library]的[!DNL Adobe Target]中建立JSON選件以用於[!UICONTROL Form-Based Experience Composer]。

JSON選件可用於表單式活動，以啟用需要[!DNL Target]決策才能以JSON格式傳送選件以用於SPA架構或伺服器端整合的使用案例。

## JSON考量事項

使用 JSON 產品建議時，請考量下列資訊:

* JSON選件目前僅適用於[!UICONTROL A/B Test]、[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Experience Targeting] (XT)活動。
* JSON選件只能用於[表單式活動](/help/main/c-experiences/form-experience-composer.md)。
* 使用[伺服器端API和Mobile Node.js、Java、.NET及Python SDK](https://experienceleague.adobe.com/zh-hant/docs/target-dev/developer/server-side/server-side-overview){target=_blank}時，可以直接擷取JSON選件。
* 在瀏覽器中，只能透過at.js 1.2.3 （或更新版本）及使用[getOffer()](https://experienceleague.adobe.com/zh-hant/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer){target=_blank} （使用`setJson`動作來篩選動作）來擷取JSON選件。
* JSON 產品建議是以原生 JSON 物件提供，而不是字串。這些物件的取用者不再需要將物件當作字串來處理，再轉換成 JSON 物件。
* 不同於其他產品建議 (例如 HTML 產品建議)，JSON 產品建議不會自動套用，因為 JSON 產品建議不是視覺化產品建議。開發人員必須撰寫程式碼，才能使用[getOffer()](https://experienceleague.adobe.com/zh-hant/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer){target=_blank}明確取得選件。

## 建立JSON選件 {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. 按一下&#x200B;**[!UICONTROL Offers]** > **[!UICONTROL Code Offers]**。
1. 按一下&#x200B;**[!UICONTROL Create Offer]** > **[!UICONTROL JSON Offer]**。
1. 輸入產品建議名稱。
1. （視條件而定）如果您有[[!DNL Target] 進階帳戶](/help/main/c-intro/intro.md#premium)，請選擇所需的[工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#workspace)。
1. （視條件而定）選擇所需的設定檔屬性。
1. 在「**[!UICONTROL Code]**」方塊中，輸入或貼上JSON程式碼。
1. 按一下 **[!UICONTROL Create]**。

## JSON範例 {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

只有使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)建立的活動才支援JSON選件。 目前，能使用JSON選件的唯一方式是透過直接API/SDK呼叫。

其範例如下:

![建立JSON選件對話方塊](/help/main/c-experiences/c-manage-content/assets/json-example.png)

傳給成功回呼的動作是物件陣列。假設您有單一JSON選件，且具有此內容：

```json
{ 
  "demo": {"a": 1, "b": 2} 
}
```

動作陣列具有此結構：

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

若要擷取JSON選件，請逐一檢視動作，找出具有`setJson`動作的動作，然後查一檢視內容陣列。

## 使用案例 {#section_85B07907B51A43239C8E3498EF58B1E5}

假設下列 JSON 產品建議傳送至您的網頁:

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
      "excepteur"
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      } 
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

## 使用Real-time CDP設定檔屬性的JSON選件範例

Real-time CDP設定檔屬性可與[!DNL Target]共用，以用於HTML和JSON選件。

如需詳細資訊，請參閱[與 [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes)共用Real-time CDP設定檔屬性。

## 依JSON選件型別篩選選件 {#section_52533555BCE6420C8A95EB4EB8907BDE}

您可以按一下[!UICONTROL Offers]圖示（**[!UICONTROL Show filters]**&#x200B;顯示篩選器圖示![&#x200B; ），然後選取](/help/main/assets/icons/Filter.svg)核取方塊，依JSON選件型別來篩選&#x200B;**[!UICONTROL JSON Offers]**&#x200B;資料庫。

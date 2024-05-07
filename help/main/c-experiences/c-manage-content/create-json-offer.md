---
keywords: 遠端選件; 建立遠端選件
description: 瞭解如何在Adobe中建立JSON選件 [!DNL Target] ，以用於表單式體驗撰寫器。
title: 如何建立JSON選件？
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: 6423c6c324fce30087056d81ee0c4432de8999df
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 30%

---

# 建立 JSON 選件

在中建立JSON選件 [!UICONTROL Offer Library] 在 [!DNL Adobe Target] 用於 [!UICONTROL Form-Based Experience Composer].

JSON選件可用於表單式活動，可透過以下用途啟用使用案例： [!DNL Target] 傳送JSON格式的選件以用於SPA框架或伺服器端整合中的使用需要決策。

## JSON考量事項

使用 JSON 選件時，請考量下列資訊:

* JSON選件目前僅適用於 [!UICONTROL A/B Test]、 Automated Personalization (AP)和 [!UICONTROL Experience Targeting] (XT)活動。
* JSON選件可用於 [表單式活動](/help/main/c-experiences/form-experience-composer.md) 僅限。
* 使用時，可直接擷取JSON選件 [伺服器端API和Mobile Node.js、Java、.NET和Python SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html){target=_blank}.
* 在瀏覽器中，只能透過at.js 1.2.3 （或更新版本）並使用來擷取JSON選件 [getOffer()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer.html){target=_blank} 使用來篩選動作 `setJson` 動作。
* JSON 選件是以原生 JSON 物件提供，而不是字串。這些物件的取用者不再需要將物件當作字串來處理，再轉換成 JSON 物件。
* 不同於其他選件 (例如 HTML 選件)，JSON 選件不會自動套用，因為 JSON 選件不是視覺化選件。開發人員必須撰寫程式碼來明確利用取得選件 [getOffer()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer.html){target=_blank}.

## 建立JSON選件 {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. 按一下 **[!UICONTROL Offers]** > **[!UICONTROL Code Offers]**.

   ![選件>代碼選件索引標籤](/help/main/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. 按一下 **[!UICONTROL Create]** > **[!UICONTROL JSON Offer]**.

   ![offer-json影像](assets/offer-json.png)

1. 輸入選件名稱。
1. 在「 」中輸入或貼上JSON程式碼 **[!UICONTROL Code]** 方塊。
1. 按一下 **[!UICONTROL Save]**。

## JSON範例 {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

只有使用建立的活動才支援JSON選件 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md). 目前，能使用JSON選件的唯一方式是透過直接API/SDK呼叫。

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

若要擷取JSON選件，請逐一檢視動作，然後找到包含 `setJson` 動作，然後逐一檢視內容陣列。

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

Real-time CDP設定檔屬性可與共用 [!DNL Target] 用於HTML和JSON選件。

如需詳細資訊，請參閱 [與共用Real-time CDP設定檔屬性 [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes).

## 依JSON選件型別篩選選件 {#section_52533555BCE6420C8A95EB4EB8907BDE}

您可以篩選 [!UICONTROL Offers] 依JSON選件型別按一下 **[!UICONTROL Type]** 下拉式清單，然後選取 **[!UICONTROL JSON]** 核取方塊。

![offer-json-filter影像](assets/offer-json-filter.png)

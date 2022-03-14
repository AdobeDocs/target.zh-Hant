---
keywords: targetPageParams;targetpageparams;pageParams;pageparams;頁面參數;頁面參數;at.js;函數;函數
description: 將targetPageParams()函式用於Adobe [!DNL Target] at.js JavaScript庫，將參數從請求代碼外部附加到全局框。
title: 如何使用targetPageParams()函式？
feature: at.js
role: Developer
exl-id: 0772b400-626c-45d8-a4b5-a12691978cf3
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 72%

---

# targetPageParams()

此方法允許您將參數從要求程式碼外部附加至全域 mbox。

對於要在多個 mbox 呼叫上併入相同的一組參數，此函數很實用。函數需要由客戶定義。它應該傳回僅會傳遞至全域 mbox 要求的參數陣列。可以在載入at.js之前或在中定義此函式 **[!UICONTROL 管理]** > **[!UICONTROL 實施]** > **[!UICONTROL 編輯]** > **[!UICONTROL 庫標題]**。

您可以使用 `targetPageParams()` 函數，透過下列任何方式將參數傳入 target-global-mbox 中:

* 以 &amp; 符號區隔的清單
* 陣列
* JSON 物件

## 範例

以 &amp; 符號分隔的清單 (值必須經過 URL 編碼):

```javascript
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

陣列 (值不需經過 URL 編碼):

```javascript
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (值不需經過 URL 編碼):

```javascript
targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
```

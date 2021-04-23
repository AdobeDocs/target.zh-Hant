---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;頁面參數;頁面參數;at.js;函數;函數
description: 使用Adobe [!DNL Target] at.js JavaScript程式庫的targetPageParamsAll()函式，將參數附加至請求程式碼以外的所有mbox。
title: 我要如何使用targetPageParamsAll()函式？
feature: at.js
role: Developer
exl-id: 58fbb62e-30da-486f-b771-6452ad5e27e6
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 72%

---

# targetPageParamsAll()

此方法允許您將參數從要求程式碼外部附加至所有 mbox。

對於要在多個 mbox 呼叫上併入相同的一組參數，這很實用。函數需要由客戶定義。它應該傳回將傳遞至頁面上所有 mbox 要求的參數陣列。此函式可在at.js載入之前或在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**&#x200B;中定義。

您可以使用 targetPageParamsAll() 函數，透過下列任何方式將參數傳入至 target-global-mbox:

* 以 &amp; 符號區隔的清單
* 陣列
* JSON 物件

## 範例

以 &amp; 符號分隔的清單 (值必須經過 URL 編碼):

```javascript
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

陣列 (值不需經過 URL 編碼):

```javascript
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (值不需經過 URL 編碼):

```javascript
targetPageParamsAll = function() { 
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

---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;page params;page parameters;at.js;functions;function
description: 有關適用於 Adobe Target at.js JavaScript 資料庫的 targetPageParamsAll() 函數的資訊。
title: targetPageParamsAll()
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 87%

---


# targetPageParamsAll()

此方法允許您將參數從要求程式碼外部附加至所有 mbox。

對於要在多個 mbox 呼叫上併入相同的一組參數，這很實用。函數需要由客戶定義。它應該傳回將傳遞至頁面上所有 mbox 要求的參數陣列。This function can be defined before at.js is loaded or in **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

您可以使用 targetPageParamsAll() 函數，透過下列任何方式將參數傳入至 target-global-mbox:

* 以 &amp; 符號區隔的清單
* 陣列
* JSON 物件

## 範例

以 &amp; 符號分隔的清單 (值必須經過 URL 編碼):

```
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

陣列 (值不需經過 URL 編碼):

```
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (值不需經過 URL 編碼):

```
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

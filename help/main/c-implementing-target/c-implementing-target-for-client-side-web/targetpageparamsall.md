---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;頁面參數;頁面參數;at.js;函數;函數
description: 使用targetPageParamsAll()函式進行Adobe [!DNL Target] at.js JavaScript庫，將參數附加到請求代碼之外的所有框。
title: 如何使用targetPageParamsAll()函式？
feature: at.js
role: Developer
exl-id: 58fbb62e-30da-486f-b771-6452ad5e27e6
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 72%

---

# targetPageParamsAll()

此方法允許您將參數從要求程式碼外部附加至所有 mbox。

對於要在多個 mbox 呼叫上併入相同的一組參數，這很實用。函數需要由客戶定義。它應該傳回將傳遞至頁面上所有 mbox 要求的參數陣列。可以在載入at.js之前或在中定義此函式 **[!UICONTROL 管理]** > **[!UICONTROL 實施]** > **[!UICONTROL 編輯]** > **[!UICONTROL 代碼設定]** > **[!UICONTROL 庫標題]**。

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

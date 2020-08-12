---
keywords: global mbox parameters;targetPageParams;query string;array;json;dtm;dynamic tag management
description: JavaScript targetPageParams 函數用來將參數傳遞至全域 mbox。在要將額外的鎖定目標/環境資訊傳遞至 Target 的任何案例中，需要此函數。
title: 傳遞參數至全域 mbox
feature: null
subtopic: Getting Started
topic: Standard
uuid: 058f0ef5-037a-4daf-8a1e-a9c7ecc7f0bd
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 97%

---


# 傳遞參數至全域 mbox{#pass-parameters-to-a-global-mbox}

JavaScript targetPageParams 函數用來將參數傳遞至全域 mbox。在要將額外的鎖定目標/環境資訊傳遞至 Target 的任何案例中，需要此函數。

例如，在「建議」活動中，使用參數來代表目前正在檢視的產品或類別。

在頁面上，用來呼叫 JavaScript 函式的程式碼必須出現在全域 mbox 之前，而不論全域 mbox 是從 mbox.js 中觸發，還是手動包含在頁面程式碼中。

>[!NOTE]
>
>如果您要將參數新增至頁面上的所有 mbox 而非僅新增至非全域 mbox，請使用 [targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) 函數 (僅限 at.js)。

您可以透過下列任何方式，利用 `target-global-mbox` 函數將參數傳入 `targetPageParams()`:

* 陣列
* JSON 物件
* 以 &amp; 符號區隔的清單

使用這三個方法來驗證是否正確傳遞參數。您可以使用 [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) 來驗證參數傳遞。

在將全域 mbox 新增至頁面之前，您必須定義 JavaScript 函式。名稱必須是 `targetPageParams`。

**查詢字串**

```
p1=v1&p2=v2&p3=hello%20world
```

* 名稱: `targetPageParams`
* 傳回值: 以 &quot;&amp;&quot; 分隔的參數，含 URL 編碼的參數值。

   範例:  

   在此範例中，p3 的值是 `hello world` (以 URL 編碼)。

以下是可能的頁面程式碼範例:

```
<html> 
  <head> 
    <title>Title here..</title> 
    <script type="text/javascript"> 
        function targetPageParams() { 
           
<b>return "p1=v1&p2=v2&p3=hello%20world"</b>; 
        } 
    </script> 
    <script src="mbox.js" type="text/javascript"></script> 
  </head> 
  <body>Body here... 
  </body> 
</html>
```

此範例會將下列資料傳送至 mbox 邊緣:

* p1=v1
* p2=v2
* p3=hello world

**陣列**

```
<!--window.-->targetPageParams = function() { 
  return ["a=1", "b=2", "c=hello world"]; 
}; 
```

值不需經過 URL 編碼。例如，假設一個值包含空格，則不需要將空格編碼。

此範例會將下列資料傳送至 mbox 邊緣:

* a=1
* b=2
* c=hello world

**JSON**

JSON 是傳遞參數的強大方式。Target 使用 JSON 物件索引鍵將複雜的結構平扁化為簡單參數。

```
<!--window.-->targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
                  "memberStatus": Gold, 
                  "country": { 
                                "city": "San Francisco" 
                            } 
              } 
  }; 
}; 
```

值不需經過 URL 編碼。例如，&quot;San Francisco&quot; 不需要將空格編碼。一個空格就足夠。

此範例會將下列資料傳送至 mbox 邊緣:

* a=1
* b=2
* `profile.age`=26
* `profile.country.city`=San Francisco
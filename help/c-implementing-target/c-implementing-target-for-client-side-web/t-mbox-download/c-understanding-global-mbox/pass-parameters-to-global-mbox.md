---
keywords: global mbox parameters;targetPageParams;query string;array;json;dtm;dynamic tag management
description: JavaScript targetPageParams 函數用來將參數傳遞至全域 mbox。在要將額外的鎖定目標/環境資訊傳遞至 Target 的任何案例中，需要此函數。
title: 傳遞參數至全域 mbox
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 74%

---


# 傳遞參數至全域 mbox{#pass-parameters-to-a-global-mbox}

JavaScript `targetPageParams` 函數用來將參數傳遞至全域 mbox。This is needed in any scenario where additional targeting/context information is to be passed into [!DNL Target].

For example, in a [!DNL Recommendations] activity, use the parameters to represent the current product or category that is being viewed.

呼叫JavaScript函式的程式碼必須位於頁面上的全域mbox之前，不論全域mbox是作為at.js的一部分引發，還是手動包含在頁面程式碼中。

>[!NOTE]
>
>If you want to add parameters to all mboxes on the page, not just to the global mbox, use the [targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) function.

您可以透過下列任何方式，利用 `target-global-mbox` 函數將參數傳入 `targetPageParams()`:

* 陣列
* JSON 物件
* 以 &amp; 符號區隔的清單

使用這三個方法來驗證是否正確傳遞參數。您可以使用 [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) 來驗證參數傳遞。

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
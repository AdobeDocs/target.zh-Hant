---
keywords: 全局mbox參數；targetPageParams;query string;array;json;dtm
description: 瞭解如何使用targetPageParams函式將其他目標或上下文資訊傳遞給Adobe [!DNL Target] 全局框。
title: 如何將參數傳遞給全局框？
feature: at.js
role: Developer
exl-id: 37d143af-83a8-48fd-91eb-58f21f8c7b94
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 60%

---

# 傳遞參數至全域 mbox

JavaScript `targetPageParams` 函式用於將參數傳遞到中的全局框 [!DNL Adobe Target]。 在要將其他目標/上下文資訊傳遞給任何情形中，都需要這樣做 [!DNL Target]。

例如，在 [!DNL Recommendations] 活動，使用參數表示當前正在查看的產品或類別。

調用JavaScript函式的代碼必須位於頁面上的全局框之前，無論全局框是作為at.js的一部分觸發還是手動包含在頁面代碼中。

>[!NOTE]
>
>如果要將參數添加到頁面上的所有框，而不只是全局框，請使用 [targetPageParamsAll()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) 的子菜單。

您可以透過下列任何方式，利用 `target-global-mbox` 函數將參數傳入 `targetPageParams()`:

* 陣列
* JSON 物件
* 以 &amp; 符號區隔的清單

使用這三個方法來驗證是否正確傳遞參數。您可以使用 [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) 來驗證參數傳遞。

在將全域 mbox 新增至頁面之前，您必須定義 JavaScript 函式。名稱必須是 `targetPageParams`。

## 查詢字串

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
          return "p1=v1&p2=v2&p3=hello%20world";
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

## 陣列

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

## JSON

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
* `profile.memberStatus`=金
* `profile.country.city`=San Francisco

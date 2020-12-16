---
keywords: qa;preview;bookmarklet;preview links
description: 此資訊可協助您使用Adobe Target QA書籤小工具來強制Target從QA模式釋放您。
title: Adobe Target的活動QA書籤小工具
feature: qa
translation-type: tm+mt
source-git-commit: 6704ac2ec73361ad95e110e9182485537d0de642
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 26%

---


# 活動 QA 書籤小程式{#activity-qa-bookmarklet}

協助您使用[!DNL Target] QA書籤小工具強制[!DNL Target]從QA模式釋放您的資訊。

>[!NOTE]
>
>建立書籤小程式的程序因瀏覽器類型與版本而異。如需具體指示，請參閱瀏覽器的說明或搜尋網際網路。

## at.js 1的活動QA書籤小工具。*x*

由於[QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)有黏性，當您以 QA 模式來瀏覽網站後，您的 工作階段必須到期，否則需要由 幫您脫離 QA 模式，才能像一般訪客一樣檢視您的網站。[!DNL Target][!DNL Target]使用QA [!DNL Target]書籤小工具強制自己退出QA模式。

若要使用[!DNL Target] QA書籤小工具，請建立包含下列JavaScript程式碼的書籤小工具，並將它新增至瀏覽器的書籤工具列：

```javascript
javascript:(
    function () {
        if (window.location.href.indexOf('?') != -1) {
            var parts = window.location.href.split('at_preview_token',2);
            if (parts.length > 1) {
                window.location.href = parts[0].concat('at_preview_token=');
            } else {
                window.location.href = window.location.href.concat("&at_preview_token=")
            }
        } else {
            window.location.href = window.location.href.concat("?at_preview_token=")
        }
    }
)();
```

您也可以透過以空值載入含有`at_preview_token`參數之網站上的頁面，手動強制自己退出QA模式。

例如:

`https://www.mysite.com/?at_preview_token=`

## at.js 2的活動QA書籤小工具。*x*

與at.js 1相反。*x*,at.js 2.** xdoes不支援協力廠商Cookie，而QA模式僅適用於第一方網域（透過at.js所設定的第一方Cookie）。因此，在at.js 2中。*x*,QA模式作業僅在用戶端進行管理，且不會將QA模式Cookie傳送至Target。

若要使用[!DNL Target] QA書籤小工具，請建立包含下列JavaScript程式碼的書籤小工具，並將它新增至瀏覽器的書籤工具列：

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Path=/; Max-Age=-0;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.open(url.substring(0, url.length - 1), '_self', 'noreferrer');
        }
    })();
```

## 使用活動QA書籤小工具

按一下瀏覽器工具列上的書籤小工具。


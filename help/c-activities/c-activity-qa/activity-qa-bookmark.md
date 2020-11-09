---
keywords: qa;preview;bookmarklet;preview links
description: 此資訊可協助您使用Adobe Target QA書籤小工具來強制Target從QA模式釋放您。
title: Adobe Target的活動QA書籤小工具
feature: qa
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 26%

---


# 活動 QA 書籤小程式{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

>[!NOTE]
>
>建立書籤小程式的程序因瀏覽器類型與版本而異。如需具體指示，請參閱瀏覽器的說明或搜尋網際網路。

## at.js 1的活動QA書籤小工具。*x*

由於[QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)有黏性，當您以 QA 模式來瀏覽網站後，您的 工作階段必須到期，否則需要由 幫您脫離 QA 模式，才能像一般訪客一樣檢視您的網站。[!DNL Target][!DNL Target]Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

```
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

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

例如:

`https://www.mysite.com/?at_preview_token=`

## at.js 2的活動QA書籤小工具。*x*

與at.js 1相反。*x*,at.js 2.*x不支援* 協力廠商Cookie，而QA模式僅適用於第一方網域（透過at.js所設定的第一方Cookie）。 因此，在at.js 2中。*x*,QA模式作業僅在用戶端進行管理，且不會將QA模式Cookie傳送至Target。

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

```
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


---
description: 此資訊可協助您使用Adobe Target QA書籤小工具來強制Target從QA模式釋放您。
keywords: qa;預覽;書籤小程式;預覽連結
seo-description: 此資訊可協助您使用Adobe Target QA書籤小工具來強制Target從QA模式釋放您。
seo-title: Adobe Target的活動QA書籤小工具
solution: Target
title: 活動 QA 書籤小程式
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: 1df7fbf78f9e20d8a907809b228ed591036c1a24

---


# 活動 QA 書籤小程式{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

由於[QA 模式](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40)有黏性，當您以 QA 模式來瀏覽網站後，您的 工作階段必須到期，否則需要由 幫您脫離 QA 模式，才能像一般訪客一樣檢視您的網站。[!DNL Target][!DNL Target]Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser's Bookmarks Toolbar:

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

書籤小程式即會出現在工具列中供重複使用。

>[!NOTE]
>
>建立書籤小程式的程序因瀏覽器類型與版本而異。如需具體指示，請參閱瀏覽器的說明或搜尋網際網路。

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

例如:

`https://www.mysite.com/?at_preview_token=`

---
keywords: qa;預覽;書籤小程式;預覽連結
description: 瞭解如何使用Adobe [!DNL Target] QA書籤將強制 [!DNL Target] 從QA模式中釋放您。
title: 如何使用活動QA書籤？
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 27%

---

# 活動 QA 書籤小程式

幫助您使用 [!DNL Target] QA書籤將強制 [!DNL Target] 從QA模式中釋放您。

>[!NOTE]
>
>建立書籤小程式的程序因瀏覽器類型與版本而異。如需具體指示，請參閱瀏覽器的說明或搜尋網際網路。

## at.js 1的活動QA書籤。*x*

由於[QA 模式](/help/main/c-activities/c-activity-qa/activity-qa.md)有黏性，當您以 QA 模式來瀏覽網站後，您的 工作階段必須到期，否則需要由 幫您脫離 QA 模式，才能像一般訪客一樣檢視您的網站。[!DNL Target][!DNL Target]使用QA [!DNL Target] bookmarklet強制您退出QA模式。

使用 [!DNL Target] QA書籤，建立包含以下JavaScript代碼的書籤並將其添加到瀏覽器的書籤工具欄：

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

您還可以通過在您的站點上載入頁面來手動強制您退出QA模式 `at_preview_token` 值為空的參數。

例如：

`https://www.mysite.com/?at_preview_token=`

## at.js 2的活動QA書籤。*x*

與at.js 1不同。*x*, at.js 2。*x* 不支援第三方cookie，並且QA模式僅對第一方域是粘滯的（通過at.js設定的第一方cookie）。 因此，在at.js 2中。*x*,QA模式會話僅在客戶端上管理，並且沒有將QA模式cookie發送到目標。

使用 [!DNL Target] QA書籤，建立包含以下JavaScript代碼的書籤並將其添加到瀏覽器的書籤工具欄：

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

## 使用活動QA書籤

按一下瀏覽器工具欄上的書籤。

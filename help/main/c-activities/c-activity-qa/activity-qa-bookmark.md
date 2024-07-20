---
keywords: qa;預覽;書籤小程式;預覽連結
description: 瞭解如何使用Adobe [!DNL Target] QA書籤小程式來強制 [!DNL Target] 將您從QA模式中釋出。
title: 如何使用活動QA書籤小程式？
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 13%

---

# 活動 QA 書籤小程式

可協助您使用[!DNL Target] QA書籤小程式來強制[!DNL Target]將您從QA模式釋出的資訊。

>[!NOTE]
>
>建立書籤小程式的程序因瀏覽器類型與版本而異。如需具體指示，請參閱瀏覽器的說明或搜尋網際網路。

## at.js 1的活動QA書籤小程式&#x200B;*x*

由於[QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md)有粘性，當您以QA模式瀏覽網站後，您的[!DNL Target]工作階段必須到期，或您需要[!DNL Target]將您從QA模式中釋出，才能像一般訪客一樣檢視您的網站。 使用QA [!DNL Target]書籤小程式強迫自己離開QA模式。

若要使用[!DNL Target] QA書籤小程式，請建立包含下列JavaScript程式碼的書籤小程式，並將其新增至瀏覽器的書籤工具列：

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

您也可以在網站上以帶有空白值的`at_preview_token`引數載入頁面，以手動強迫自己離開QA模式。

例如：

`https://www.mysite.com/?at_preview_token=`

## at.js 2的活動QA書籤小程式&#x200B;*x*

與at.js 1.*x*， at.js 2.*x*&#x200B;不支援第三方Cookie，且QA模式只對第一方網域有粘性（透過at.js設定的第一方Cookie）。 因此，在at.js 2.*x*，QA模式工作階段僅在使用者端受到管理，且不會將QA模式Cookie傳送至Target。

若要使用[!DNL Target] QA書籤小程式，請建立包含下列JavaScript程式碼的書籤小程式，並將其新增至瀏覽器的書籤工具列：

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

## 使用活動QA書籤小程式

按一下瀏覽器工具列上的書籤小程式。

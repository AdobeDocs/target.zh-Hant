---
keywords: qa;預覽;書籤小程式;預覽連結
description: 瞭解如何使用Adobe [!DNL Target] QA書籤小程式來強制[!DNL Target]將您從QA模式中釋出。
title: 如何使用活動QA書籤小程式？
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
TQID: 'https://experienceleague.adobe.com/kOQcdF2WgiAGkOS3rrLWfDSFTvRJX8jb-IeaahWnM0c'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 6%
---
# 活動 QA 書籤小程式 {#activity-qa-bookmarklet}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何使用[!DNL Target] QA書籤小程式結束&#x200B;**[!UICONTROL 活動QA]**&#x200B;模式，並像一般訪客一樣檢視您的網站。

>[!ENDSHADEBOX]

當您以[QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md)瀏覽網站後，QA模式會跨頁面持續存在，直到[!DNL Target]工作階段過期為止。 書籤小程式是執行JavaScript的瀏覽器書籤。 [!DNL Target] QA書籤小程式強制[!DNL Target]將您從QA模式中釋出，因此您不必等待工作階段過期。 使用與網站上部署的at.js版本相符的版本。

>[!NOTE]
>
>建立書籤小程式的程序因瀏覽器類型與版本而異。 請參閱瀏覽器的說明，或在網際網路上搜尋特定指示。

## at.js 1.*x*&#x200B;的活動QA書籤小程式

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

您也可以在網站上載入頁面，並將`at_preview_token`引數設為空白值，以手動強迫自己離開QA模式。 例如：

`https://www.mysite.com/?at_preview_token=`

## at.js 2.*x*&#x200B;的活動QA書籤小程式

與at.js 1.*x*&#x200B;不同，at.js 2.*x*&#x200B;不支援第三方Cookie。 QA模式只會透過at.js設定的第一方Cookie在第一方網域中持續存在。 因此，QA模式工作階段僅在使用者端受到管理，而且不會將任何QA模式Cookie傳送到[!DNL Target]。

若要使用[!DNL Target] QA書籤小程式，請建立包含下列JavaScript程式碼的書籤小程式，並將其新增至瀏覽器的書籤工具列：

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {            
            document.cookie = AT_QA_MODE + ';domain='+window.location.hostname+";Path=/; Max-Age=-0;";
            var token = window.location.href.indexOf("?at_preview_token")<0? "&at_preview_token" : "?at_preview_token";
            var url = window.location.href.split(token,2)[0];
            window.open(url, '_self', 'noreferrer');
        }
    })(); 
```

## 使用活動QA書籤小程式

將符合at.js版本的書籤小程式新增至瀏覽器後，每當想要離開QA模式時都可以使用：

1. 處於QA模式時開啟網站的任何頁面。
1. 按一下瀏覽器書籤工具列中的書籤小程式。
1. 載入網站的頁面。 [!DNL Target]會從QA模式釋出工作階段，網站會以一般訪客的樣子顯示。

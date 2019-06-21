---
description: 可協助您使用 Target QA 小書籤來強制 Target 將您從 QA 模式釋出的資訊。
keywords: qa;預覽;書籤小程式;預覽連結
seo-description: 可協助您使用 Target QA 小書籤來強制 Target 將您從 QA 模式釋出的資訊。
seo-title: 活動 QA 書籤小程式
solution: Target
title: 活動 QA 書籤小程式
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 活動 QA 書籤小程式{#activity-qa-bookmarklet}

可協助您使用 Target QA 小書籤來強制 Target 將您從 QA 模式釋出的資訊。

由於[QA 模式](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40)有黏性，當您以 QA 模式來瀏覽網站後，您的 Target 工作階段必須到期，否則需要由 Target 幫您脫離 QA 模式，才能像一般訪客一樣檢視您的網站。使用 QA Target 書籤小程式來強迫您自己離開 QA 模式。

若要使用 Target QA 書籤小程式，請建立含以下 JavaScript 程式碼的書籤小程式，然後新增到瀏覽器的書籤工具列:

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

您也可以在網站上以帶有空白值的 `at_preview_token` 參數 (例如，`https://www.mysite.com/?at_preview_token=`) 來載入頁面，以手動強迫自己離開 QA 模式。

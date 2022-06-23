---
keywords: 內容安全性原則;csp;at.js;白名單;允許清單;閃現;預隱藏;預先隱藏
description: 了解當您使用 Adobe Target 時應該新增的內容安全性原則 (CSP) 指示。
title: ' [!DNL Target] 如何處理內容安全性原則 (CSP)？'
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 97%

---

# 內容安全性原則 (CSP) 指示

如果您正在使用[內容安全性原則](https://zh.wikipedia.org/wiki/Content_Security_Policy) (CSP) 進行 [!DNL Adobe Target] 實作，您應該在使用 [at.js 2.1 或更新版本](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/)時新增下列 CSP 指示：

* `connect-src` 並將 `*.tt.omtrdc.net` 加入允許清單。 允許將網路要求傳送到 [!DNL Target] 邊緣所需。
* `style-src unsafe-inline`。 預先隱藏和閃現控制所需。
* `script-src unsafe-inline`.  允許執行可能是 HTML 選件之一部分的 JavaScript 所需。

## 常見問題集 (FAQ)

查詢以下關於內容安全性原則的常見問題：

### 跨原始資源共用 (CORS) 和 Flash 跨網域原則會出現安全問題嗎？

實施 CORS 原則的推薦方法是允許存取限可信任的來源；這類來源規定要通過受信任網域的允許清單來進行。Flash 跨網域原則也是同樣的道理。 有些 [!DNL Adobe Target] 客戶擔心在 [!DNL Target] 網域使用萬用字元。 問題是如果用戶已登入應用程式，並瀏覽原則允許的網域，則該網域上執行的任何惡意內容都可以從應用程式中擷取敏感內容，並在用戶已登入的安全性環境中執行操作。這通常稱為跨網站請求偽造 (CSRF)。

但是，在 [!DNL Adobe Target] 實施中，這些政策應該不表示有安全問題。

「adob&#x200B;&#x200B;e.tt.omtrdc.net」是 Adobe 擁有的網域。 [!DNL Adobe Target] 是一種測試和個人化工具，[!DNL Target] 應可從任何地方接收和處理請求，而無需任何身份驗證。 這些請求包含用來進行 A/B 測試、建議或內容個人化的機碼/值組。

[!DNL Adobe] 不會將 [!DNL Adobe Target] 邊緣伺服器內的可識別個人身份的資訊 (PII) 或其他敏感資訊儲存在「adobe.tt.omtrdc.net」指向處。

[!DNL Target] 應可透過 JavaScript 呼叫從任何網域存取。 允許這類存取的唯一方法是運用附萬用字元的「Access-Control-Allow-Origin」。

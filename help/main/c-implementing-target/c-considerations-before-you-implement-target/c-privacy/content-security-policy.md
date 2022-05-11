---
keywords: 內容安全性原則;csp;at.js;白名單;允許清單;閃現;預隱藏;預先隱藏
description: 了解當您使用 Adobe Target 時應該新增的內容安全性原則 (CSP) 指示。
title: ' [!DNL Target] 如何處理內容安全性原則 (CSP)？'
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: db632225d21c2e061e82269bec168341b410575a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 29%

---

# 內容安全性原則 (CSP) 指示

如果您正在使用[內容安全性原則](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) 進行 [!DNL Adobe Target] 實作，您應該在使用 [at.js 2.1 或更新版本](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)時新增下列 CSP 指示：

* `connect-src` 並將 `*.tt.omtrdc.net` 加入允許清單。 允許將網路要求傳送到 [!DNL Target] 邊緣所需。
* `style-src unsafe-inline`。 預先隱藏和閃現控制所需。
* `script-src unsafe-inline`.  允許執行可能是 HTML 選件之一部分的 JavaScript 所需。

## 常見問題(FAQ)

有關安全策略，請參閱以下常見問題解答：

### 跨源資源共用(CORS)和Flash跨域策略是否存在安全問題？

實施CORS策略的建議方法是允許僅通過受信任域的允許清單訪問需要它的受信任源。 Flash跨域策略也是如此。 部分 [!DNL Adobe Target] 客戶擔心在中為域使用通配符 [!DNL Target]。 問題是，如果用戶已登錄到應用程式，並訪問策略允許的域，則在該域上運行的任何惡意內容都可能從應用程式檢索敏感內容，並在登錄用戶的安全上下文中執行操作。 這通常稱為跨站點請求偽造(CSRF)。

在 [!DNL Adobe Target] 但是，這些政策的實施不應代表安全問題。

&quot;adobe.tt.omtrdc.net&quot;是Adobe擁有的域。 [!DNL Adobe Target] 是測試和個性化工具，預期 [!DNL Target] 可以從任何位置接收和處理請求，而無需任何身份驗證。 這些請求包含用於A/B測試、建議或內容個性化的密鑰/值對。

[!DNL Adobe] 不儲存個人識別資訊(PII)或其他敏感資訊 [!DNL Adobe Target] 指向「adobe.tt.omtrdc.net」的邊緣伺服器。

預計 [!DNL Target] 可通過JavaScript調用從任何域訪問。 允許此訪問的唯一方法是使用帶通配符的「訪問控制允許來源」。

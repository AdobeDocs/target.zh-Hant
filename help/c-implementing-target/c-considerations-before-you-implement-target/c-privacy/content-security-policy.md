---
description: 使用Adobe Target at.js 2.1或更新版本時，您應新增的內容安全性政策(CSP)指令相關資訊。
keywords: 內容安全策略；csp;at.js；白名單；flicker;pre-hide;pre-hide;pre-hiding;pre-hiding
seo-description: 使用Adobe Target at.js 2.1或更新版本時，您應新增的內容安全性政策(CSP)指令相關資訊。
seo-title: Content Security Policies (CSP)
solution: Target
subtopic: 快速入門
title: Content Security Policy (CSP) directives
topic: Standard
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# 內容安全性政策(CSP)指令

If you are using [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) for your Target implementation, you should add the following CSP directives when using [at.js 2.1 or later](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` 有白 `*.tt.omtrdc.net` 名單。 必須允許對邊緣進行網路 [!DNL Target] 請求。
* `style-src unsafe-inline`。預隱藏和閃爍控制所需。
* `script-src unsafe-inline`.  允許可能屬於HTML選件一部分的JavaScript執行時，此為必要項。

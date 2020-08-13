---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: 使用Adobe Target at.js 2.1或更新版本時，您應新增的內容安全性政策(CSP)指令相關資訊。
title: 內容安全性政策(CSP)
feature: privacy and security
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---


# 內容安全性政策(CSP)指令

如果您使用 [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)進行Target實作，在使用 [at.js 2.1或更新版本時，應新增下列CSP指令](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` 的 `*.tt.omtrdc.net` 值。 必須允許對邊緣進行網路 [!DNL Target] 請求。
* `style-src unsafe-inline`。預隱藏和閃爍控制所需。
* `script-src unsafe-inline`.  允許可能屬於HTML選件一部分的JavaScript執行時，此為必要項。

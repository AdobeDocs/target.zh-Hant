---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: 使用Adobe Target at.js 2.1或更新版本時，您應新增的內容安全性政策(CSP)指令相關資訊。
title: 內容安全性政策(CSP)
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 0%

---


# 內容安全性政策(CSP)指令

如果您使用[內容安全性原則](https://en.wikipedia.org/wiki/Content_Security_Policy)(CSP)來實施[!DNL Adobe Target]，則在使用[at.js 2.1或更新版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)時應新增下列CSP指令：

* `connect-src` 中 `*.tt.omtrdc.net` 列出。必須允許對[!DNL Target]邊的網路請求。
* `style-src unsafe-inline`。預隱藏和閃爍控制所需。
* `script-src unsafe-inline`.允許可能屬於HTML選件一部分的JavaScript執行時，此為必要項。

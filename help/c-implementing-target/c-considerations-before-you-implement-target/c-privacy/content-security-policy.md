---
keywords: 內容安全策略；csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hide;pre-hiding;pre-hiding
description: 瞭解使用Adobe Target時應新增的內容安全性政策(CSP)指示。
title: Target如何處理內容安全性政策(CSP)?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---


# 內容安全性政策(CSP)指令

如果您使用[內容安全性原則](https://en.wikipedia.org/wiki/Content_Security_Policy)(CSP)來實施[!DNL Adobe Target]，則在使用[at.js 2.1或更新版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)時應新增下列CSP指令：

* `connect-src` 中 `*.tt.omtrdc.net` 列出。必須允許對[!DNL Target]邊的網路請求。
* `style-src unsafe-inline`。預隱藏和閃爍控制所需。
* `script-src unsafe-inline`.允許可能屬於HTML選件一部分的JavaScript執行時，此為必要項。

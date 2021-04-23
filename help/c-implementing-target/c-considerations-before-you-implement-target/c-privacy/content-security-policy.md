---
keywords: 內容安全策略；csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hide;pre-hiding;pre-hiding
description: 瞭解使用Adobe Target時應加入的內容安全性政策(CSP)指示。
title: '如何處理內容安全策略(CSP)? [!DNL Target] '
feature: 隱私權與安全性
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# 內容安全性政策(CSP)指令

如果您使用[內容安全性原則](https://en.wikipedia.org/wiki/Content_Security_Policy)(CSP)來實施[!DNL Adobe Target]，則在使用[at.js 2.1或更新版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)時，應新增下列CSP指令：

* `connect-src` 中 `*.tt.omtrdc.net` 列出。必須允許對[!DNL Target]邊的網路請求。
* `style-src unsafe-inline`。預隱藏和閃爍控制所需。
* `script-src unsafe-inline`.允許可能屬於HTML選件一部分的JavaScript執行時，此為必要項。

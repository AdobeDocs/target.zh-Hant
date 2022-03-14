---
keywords: 內容安全策略；csp;at.js;whitelist;allowlist;flicge;prehide;pre-hideng;pre-hiding
description: 瞭解使用Adobe Target時應添加的內容安全策略(CSP)指令。
title: 如何 [!DNL Target] 處理內容安全策略(CSP)?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 5%

---

# 內容安全性政策 (CSP)

如果您使用 [內容安全策略](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) [!DNL Adobe Target] 實現時，應在使用 [at.js 2.1或更高版本](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` 與 `*.tt.omtrdc.net` 已列出。 必須允許網路請求 [!DNL Target] 邊。
* `style-src unsafe-inline`。預隱藏和閃爍控制所需。
* `script-src unsafe-inline`。  允許執行可能是HTML提供一部分的JavaScript時必需。

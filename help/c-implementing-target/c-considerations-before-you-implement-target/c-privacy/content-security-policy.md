---
keywords: 內容安全策略；csp;at.js；白名單；flicker;pre-hide;pre-hide;pre-hiding;pre-hiding
description: 使用Adobe Target at.js 2.1或更新版本時，您應新增的內容安全性政策(CSP)指令相關資訊。
title: 內容安全性政策(CSP)
subtopic: 快速入門
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 內容安全性政策(CSP)指令

如果您使用 [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)進行Target實作，在使用 [at.js 2.1或更新版本時，應新增下列CSP指令](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` 有白 `*.tt.omtrdc.net` 名單。 必須允許對邊緣進行網路 [!DNL Target] 請求。
* `style-src unsafe-inline`。預隱藏和閃爍控制所需。
* `script-src unsafe-inline`.  允許可能屬於HTML選件一部分的JavaScript執行時，此為必要項。

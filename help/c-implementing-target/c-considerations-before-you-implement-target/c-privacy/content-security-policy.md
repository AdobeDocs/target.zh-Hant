---
description: 有關使用Adobe Target at. js2.1或更新版本時應新增之內容安全政策(CSP)指示的資訊。
keywords: 內容保全政策；csp；at. js；白名單；閃爍；預先隱藏；預先隱藏；預先隱藏
seo-description: 有關使用Adobe Target at. js2.1或更新版本時應新增之內容安全政策(CSP)指示的資訊。
seo-title: 內容安全政策(CSP)
solution: Target
subtopic: 快速入門
title: 內容安全政策(CSP)指示
topic: Standard
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# 內容安全政策(CSP)指示

如果您使用 [的是Target實作的內容安全性政策](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP)，則在使用 [at. js2.1或更新版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)時，應新增下列CSP指示：

* `connect-src` 以 `*.tt.omtrdc.net` 列入白名單。允許網路要求 [!DNL Target] 邊緣。
* `style-src unsafe-inline`。預先隱藏和閃爍控制所需。
* `script-src unsafe-inline`.  必須允許JavaScript執行，此動作可能屬於HTML選件的一部分。

---
keywords: 內容安全性原則;csp;at.js;白名單;允許清單;閃現;預隱藏;預先隱藏
description: 了解當您使用 Adobe Target 時應該新增的內容安全性原則 (CSP) 指示。
title: ' [!DNL Target] 如何處理內容安全性原則 (CSP)？'
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: ht
source-wordcount: '97'
ht-degree: 100%

---

# 內容安全性原則 (CSP) 指示

如果您正在使用[內容安全性原則](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) 進行 [!DNL Adobe Target] 實作，您應該在使用 [at.js 2.1 或更新版本](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)時新增下列 CSP 指示：

* `connect-src` 並將 `*.tt.omtrdc.net` 加入允許清單。 允許將網路要求傳送到 [!DNL Target] 邊緣所需。
* `style-src unsafe-inline`。 預先隱藏和閃現控制所需。
* `script-src unsafe-inline`.  允許執行可能是 HTML 選件之一部分的 JavaScript 所需。

---
keywords: registerExtension;registerextension;註冊擴充功能;at.js;函數;函數;clientCode;serverDomain;globalMboxName;globalMboxAutoCreate;逾時
description: 使用registerExtension()函式進行Adobe [!DNL Target] at.js JavaScript庫以註冊特定擴展。 (at.js 1.x)
title: 如何使用registerExtension()函式？
feature: at.js
role: Developer
exl-id: 7f0898b4-ddd5-425c-99dc-94f9b30f8ba7
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 90%

---

# registerExtension() - at.js 1.x

提供標準方式來註冊特定的延伸模組。

>[!NOTE]
>
>此函數僅適用於 at.js 1.*x* 版。自 at.js 2.x 版起已棄用此函數。如果與 at.js 2.x 搭配使用，此函數會傳回預設內容。

options 參數是強制性的，並且具有下列結構:

| 機碼 | 類型 | 必要 | 說明 |
|--- |--- |--- |--- |
| 名稱 | 字串 | 是 | 延伸模組名稱。 |
| 模組 | Array[String] | 是 | 代表要求的模組名稱的字串陣列。 |
| register | 函數 | 是 | 用來初始化和建置延伸模組的函數。此函數會根據模組陣列接收引數。 |

附註:

* 如果未提供其中一個參數，則會擲出例外。
* 如果模組陣列是空的，則會擲出例外。

如需詳細資訊和如何使用 `registerExtension` 的範例，請參閱 GitHub 上的 [Adobe Experience Cloud Target atjs 擴充功能](https://github.com/Adobe-Marketing-Cloud/target-atjs-extensions)頁面。

## 設定模組方法 {#section_8501CDD4B0624FA2B10532C98C5F4328}

| 機碼 | 類型 | 說明 |
|--- |--- |--- |
| clientCode | 字串 | 用戶端代碼 |
| serverDomain | 字串 | Edge 伺服器網域 |
| globalMboxName | 字串 | Target 全域 mbox 名稱 |
| globalMboxAutoCreate | 布林值 | 指出自動建立是否已啟用 |
| timeout | 數字 | 要求逾時 |

## 記錄器模組方法 {#section_10AF62B49AEF48F981E950D26E176138}

| 機碼 | 類型 | 說明 |
|--- |--- |--- |
| 記錄 | 函數 | 將引數的變數清單記錄至瀏覽器主控台 (如果存在)。只有在將 `mboxDebug=true` 傳遞至 URL 時，它才會啟動。 |
| error | 函數 | 將引數的變數清單記錄至瀏覽器主控台。只有在有嚴重錯誤，例如網路逾時、找不到 HTML 節點時，它才會啟動。 |

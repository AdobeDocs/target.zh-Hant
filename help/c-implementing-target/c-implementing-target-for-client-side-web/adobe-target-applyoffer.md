---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;apply offer;at.js;functions;function
description: 有關適用於 Adobe Target at.js JavaScript 資料庫的 adobe.target.applyOffer(options) 函數的資訊。
title: 有關適用於 Adobe Target at.js JavaScript 資料庫的 adobe.target.applyOffer() 函數的資訊。
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 100%

---


# adobe.target.applyOffer(options) {#reference_BBE83F513B5B4E03BBC3F50D90864245}

此函數用來套用回應內容。

>[!NOTE]
>
>`applyOffer` 需要 `mbox` 參數。如果未指定 mbox 名稱，則會發生錯誤。

options 參數是強制性的，並且具有下列結構:

| 機碼 | 類型 | 必要 | 說明 |
|--- |--- |--- |--- |
| mbox | 字串 | 是 | mbox 名稱<br>利用 at.js 1.3.0 (和更新版本)，Target 可強制使用 mbox 機碼。此機碼在過去為必要，但現在 Target 會強制使用它，以確保 Target 有正確的驗證，且客戶能正確使用函數。 |
| selector | 字串或 DOM 元素 | 無 | HTML 元素或 CSS 選取器過去會識別 Target 應該放置選件內容的 HTML 元素。如果未提供選取器，Target 會假設我們應該使用的 HTML 元素為 HTML HEAD。 |
| offer | 陣列 | 是 | 應該套用至元素的動作陣列。 |

## 範例 {#section_D8D6A17B73DE4542937CDB687193A5CC}

下列範例顯示如何將 `getOffer` 和 `applyOffer` 一起使用:

```
adobe.target.getOffer({   
  "mbox": "mbox",   
  "success": function(offers) {           
        adobe.target.applyOffer( {  
           "mbox": "mbox", 
           "offer": offers  
        } ); 
  },   
  "error": function(status, error) {           
      if (console && console.log) { 
        console.log(status); 
        console.log(error); 
      } 
  }, 
 "timeout": 5000 
}); 
```

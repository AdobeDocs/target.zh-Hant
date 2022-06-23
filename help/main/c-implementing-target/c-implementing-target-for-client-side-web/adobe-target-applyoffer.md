---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;套用選件;at.js;函數;函數
description: 使用adobe.target.applyOffer()函式進行Adobe [!DNL Target] at.js JavaScript庫以應用響應內容。
title: 如何使用adobe.target.applyOffer()函式？
feature: at.js
role: Developer
exl-id: d230d48f-0d6c-4f55-96a0-681dd31e8d16
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 72%

---

# adobe.target.applyOffer(options)

此函式用於將響應內容與 [!DNL Adobe Target]。

>[!NOTE]
>
>`applyOffer` 需要 `mbox` 參數。如果未指定 mbox 名稱，則會發生錯誤。

options 參數是強制性的，並且具有下列結構:

| 機碼 | 類型 | 必要 | 說明 |
|--- |--- |--- |--- |
| mbox | 字串 | 是 | mbox 名稱<br>利用 at.js 1.3.0 (和更新版本)，Target 可強制使用 mbox 機碼。此機碼在過去為必要，但現在 Target 會強制使用它，以確保 Target 有正確的驗證，且客戶能正確使用函數。 |
| selector | 字串或 DOM 元素 | 無 | HTML 元素或 CSS 選取器過去會識別 Target 應該放置選件內容的 HTML 元素。如果未提供選擇器，則Target假定HTML元素應使用HTMLHEAD。 |
| 優惠 | 陣列 | 是 | 應該套用至元素的動作陣列。 |

## 範例 {#section_D8D6A17B73DE4542937CDB687193A5CC}

下列範例顯示如何將 `getOffer` 和 `applyOffer` 一起使用:

```javascript
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

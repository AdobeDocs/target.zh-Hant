---
description: '有關適用於 at.js 的 targetPageParams() 函數的資訊。 '
keywords: adobe.target.notification;元素;選取器;通知;擴充功能
seo-description: 有關適用於 Adobe Target at.js JavaScript 資料庫的 targetPageParams() 函數的資訊。
seo-title: 有關適用於 Adobe Target at.js JavaScript 資料庫的 targetPageParams() 函數的資訊。
solution: Target
subtopic: 快速入門
title: targetPageParams()
topic: Standard
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

此方法允許您將參數從要求程式碼外部附加至全域 mbox。

對於要在多個 mbox 呼叫上併入相同的一組參數，此函數很實用。函數需要由客戶定義。它應該傳回僅會傳遞至全域 mbox 要求的參數陣列。可以在載入 at.js 之前定義此函數，或是在&#x200B;**[!UICONTROL 「設定]** &gt; **[!UICONTROL 實作]** &gt; **[!UICONTROL 編輯 at.js 設定]** &gt; **[!UICONTROL 程式碼設定]** &gt; **[!UICONTROL 資料庫標題」]**&#x200B;中定義。

您可以使用 `targetPageParams()` 函數，透過下列任何方式將參數傳入 target-global-mbox 中:

* 以 &amp; 符號區隔的清單
* 陣列
* JSON 物件

## 範例

以 &amp; 符號分隔的清單 (值必須經過 URL 編碼):

```
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

陣列 (值不需經過 URL 編碼):

```
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (值不需經過 URL 編碼):

```
targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
```

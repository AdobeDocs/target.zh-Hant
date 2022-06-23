---
keywords: adobe.target.trackEvent;trackEvent;trackevent;追蹤事件;at.js;函數;函數;preventDefault;preventdefault;防止預設
description: 使用adobe.target.trackEvent()函式進行Adobe [!DNL Target] at.js JavaScript庫以觸發報告用戶操作（如在站點上按一下和轉換）的請求。
title: 如何使用adobe.target.trackEvent()函式？
feature: at.js
role: Developer
exl-id: 36005236-ce18-4845-b4fb-e52056018bc7
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 67%

---

# adobe.target.trackEvent(options)

此函數會觸發要求以報告使用者動作，例如點擊和轉換。它不會在回應中傳遞活動。

然後這些事件追蹤 mbox 呼叫可以用來定義活動中的量度。如需詳細資訊，請參閱[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)和[追蹤轉換](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)。

以下是 API 詳細資料:

| 機碼 | 類型 | 必要 | 說明 |
|--- |--- |--- |--- |
| mbox | 字串 | 是 | 郵箱名稱&#x200B;<br>**注釋**:如果觸發trackEvent()調用時使用的mbox名稱已在頁面上激發，則trackEvent()的SDID將重置，並且將與頁面上的Target調用不同。 但是，使用不同的mbox名稱觸發trackEvent()調用會使trackEvent()調用的SDID與頁面上的Page Load Request/triggerView()調用保持一致。 |
| selector | 字串 | 無 | 用來尋找 HTML 元素的 CSS 選取器。事件接聽程式將附加至找到的元素。 |
| type | 字串 | 無 | 代表已註冊的事件類型。它可以是 HTML 已知事件，如: 按一下、按下滑鼠等等，也可以是自訂 HTML 事件。 |
| preventDefault | 布林值 | 無 | 指出是否在事件接聽程式回呼中使用 `event.preventDefault()`。預設值設為 false。<br>**注釋**:僅 `form[submit]` 和 `a[click]` 。 由於複雜度和要支援的案例數量太大，不支援其他案例。 |
| params | 物件 | 無 | mbox 參數.機碼/值組的物件具有下列結構: <br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | 數字 | 無 | 逾時，以毫秒為單位。<br>如果未指定，會使用預設值:<br>`...timeoutInSeconds: 0.15...}` |
| success | 函數 | 無 | 回呼函數，用來指出已報告該事件。 |
| error | 函數 | 無 | 回呼函數，用來指出無法報告該事件。 |

## 範例

```javascript
<a href="https://asite.com">click me!</a> 
```

加上 javaScript 程式碼來指派 `trackEvent`:

```javascript
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

或:

```javascript
adobe.target.trackEvent({ 
    "mbox": "clicked-cta", 
    "params": { 
        "param1": "value1" 
    } 
});
```

>[!NOTE]
>
>如果未設定強制欄位，則不會執行任何要求，並且擲出錯誤。

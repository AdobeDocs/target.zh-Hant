---
keywords: adobe.target.trackEvent;trackEvent;trackevent;追蹤事件;at.js;函數;函數;preventDefault;preventdefault;防止預設
description: 使用Adobe Target at.js JavaScript程式庫的adobe.target.trackEvent()函式，觸發報告使用者動作的要求，例如您網站上的點按和轉換。
title: 我要如何使用adobe.target.trackEvent()函式？
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 70%

---


# adobe.target.trackEvent(options)

此函數會觸發要求以報告使用者動作，例如點擊和轉換。它不會在回應中傳遞活動。

然後這些事件追蹤 mbox 呼叫可以用來定義活動中的量度。如需詳細資訊，請參閱[成功量度](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)和[追蹤轉換](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)。

以下是 API 詳細資料:

| 機碼 | 類型 | 必要 | 說明 |
|--- |--- |--- |--- |
| mbox | 字串 | 是 | Mbox名稱&#x200B;<br>**Note**:如果觸發trackEvent()呼叫時的mbox名稱已在頁面上引發，則會重設trackEvent()的SDID，其值會與頁面上的Target呼叫不同。 但是，觸發具有不同mbox名稱的trackEvent()呼叫會使trackEvent()呼叫的SDID與頁面上的頁面載入請求/triggerView()呼叫保持一致。 |
| selector | 字串 | 無 | 用來尋找 HTML 元素的 CSS 選取器。事件接聽程式將附加至找到的元素。 |
| type | 字串 | 無 | 代表已註冊的事件類型。它可以是 HTML 已知事件，如: 按一下、按下滑鼠等等，也可以是自訂 HTML 事件。 |
| preventDefault | 布林值 | 無 | 指出是否在事件接聽程式回呼中使用 `event.preventDefault()`。預設值設為 false。<br>**注意**: 僅支援 `form[submit] and `a[click]。由於複雜度和要支援的案例數量太大，不支援其他案例。 |
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
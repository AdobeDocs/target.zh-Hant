---
description: 'at. js的adobe. target. trackEvent(選項)函數相關資訊。 '
keywords: adobe.target.notification;元素;選取器;通知;擴充功能
seo-description: Adobe Target at. js JavaScript程式庫的adobe. target. trackEvent(選項)函數的相關資訊。
seo-title: Adobe Target at. js JavaScript程式庫的adobe. target. trackEvent(選項)函數的相關資訊。
solution: Target
subtopic: 快速入門
title: adobe.target.trackEvent(options)
topic: Standard
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# adobe.target.trackEvent(options)

此函數會觸發要求以報告使用者動作，例如點擊和轉換。它不會在回應中傳遞活動。

然後這些事件追蹤 mbox 呼叫可以用來定義活動中的量度。如需詳細資訊，請參閱[成功量度](../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)和[追蹤轉換](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)。

以下是 API 詳細資料:

| 機碼 | 類型 | 必要 | 說明 |
|--- |--- |--- |--- |
| mbox | 字串 | 是 | Mbox 名稱 |
| selector | 字串 | 無 | 用來尋找 HTML 元素的 CSS 選取器。事件接聽程式將附加至找到的元素。 |
| type | 字串 | 無 | 代表已註冊的事件類型。它可以是 HTML 已知事件，如: 按一下、按下滑鼠等等，也可以是自訂 HTML 事件。 |
| preventDefault | 布林值 | 無 | 指出是否在事件接聽程式回呼中使用 `event.preventDefault()`。預設值設為 false。<br>**注意**: 僅支援 `form[submit] and `a[click]。由於複雜度和要支援的案例數量太大，不支援其他案例。 |
| params | 物件 | 無 | mbox 參數. 機碼/值組的物件具有下列結構: <br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | 數字 | 無 | 逾時，以毫秒為單位。<br>如果未指定，會使用預設值:<br>`...timeoutInSeconds: 0.15...}` |
| success | 函數 | 無 | 回呼函數，用來指出已報告該事件。 |
| error | 函數 | 無 | 回呼函數，用來指出無法報告該事件。 |

## 範例

```
<a href="https://asite.com">click me!</a> 
```

加上 javaScript 程式碼來指派 `trackEvent`:

```
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

或:

```
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
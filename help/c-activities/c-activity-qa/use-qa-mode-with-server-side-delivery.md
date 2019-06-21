---
description: 透過伺服器端傳送使用 QA URL，來執行簡易的端對端活動 QA，同時具有永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的 QA 報表。
keywords: qa;伺服器端;伺服器端;預覽;預覽連結
seo-description: 透過伺服器端傳送使用 QA URL，來執行簡易的端對端活動 QA，同時具有永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的 QA 報表。
seo-title: 使用透過伺服器端傳送的活動 QA
solution: Target
title: 使用透過伺服器端傳送的活動 QA
topic: Advanced,Standard,Classic
uuid: c1875243-e37f-4205-9e6b-6e96cadf4a7f
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 使用透過伺服器端傳送的活動 QA{#use-activity-qa-with-server-side-delivery}

透過伺服器端傳送使用 QA URL，來執行簡易的端對端活動 QA，同時具有永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的 QA 報表。

活動 QA 標準實作支援透過 `qa_mode` mbox 參數傳遞 `pageUrl` 參數。此方式便於標準/ajax mbox 呼叫。但若為伺服器對伺服器呼叫，無法使用 `pageUrl` 時，則對 Mobile SDK 而言不是最佳方式。

以下程式碼範例說明伺服器端呼叫的活動 QA:

```
{
  "mbox" : "orderConfirmPage",
  "clientSideAnalyticsLogging": true,
  "clicked" : true,
  "tntId" : "12121212.17_01",
  "order" : {
    ...
  },
  "profileParameters" : {
    ...
  },
  "mboxParameters" : {
    ...
  },
  "requestLocation" : {
    ...
  },
  "qaMode" : {
    "token" : "<encrypted token string>",
    "bypassEntryAudience" : true,
    "listedActivitiesOnly" : true,
    "evaluateAsTrueAudienceIds" : [audienceId1, audienceId2...],
    "evaluateAsFalseAudienceIds" : [audienceId3, audienceId4...],
    "previewIndexes" : [
       {
         "activityIndex" : 1,
         "experienceIndex" : 1
       }
     ],
  },
  "mboxTrace" : true
}
```

下表說明伺服器端要求的詳細資訊:

| 參數 | 類型 | 預設值 | 說明 |
|--- |--- |--- |--- |
| token | 加密 Token | 無.<br>不得空白。 | 此加密實體包含可在活動 QA 中執行的活動 ID 清單。<br>驗證規則: 加密 Token 應屬於 mbox 要求中指定的用戶端。該 Token 中指定的所有活動應屬於該用戶端。 |
| bypassEntryAudience | 布林值 | False | 指定是否應評估 QA 活動的入門目標，或是否應視為相符。 |
| listedActivitiesOnly | 布林值 | False | 指定是否應單獨執行 QA 活動，或是否應評估為目前環境的使用中活動。 |
| evaluateAsTrueAudienceIds | ID 清單 | 空白清單。 | mbox 要求範圍內應一律評為 True 的對象 ID 清單。 |
| evaluateAsFalseAudienceIds | ID 清單 | 空白清單。 | mbox 要求範圍內應一律評為 False 的對象 ID 清單。 |
| activityIndex | 整數 | Null。<br>不得空白。 | 加密 Token 的活動索引。如果 activityIndex 不在加密 Token 活動的範圍中，或為 null，系統會加以忽略。索引從 1 開始。<br>驗證規則: 至少應有一個活動索引，並應參考 Token 中指定的活動。 |
| experienceIndex | 整數 | Null。 | 指定此參數時，請依照活動定義中的索引選取體驗。如果未指定或不在範圍內，會改回使用活動的體驗選取器策略。索引從 1 開始    驗證規則: 可為 null，或應參考活動中的體驗。 |
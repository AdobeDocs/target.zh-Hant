---
keywords: qa;伺服器端;伺服器端;預覽;預覽連結
description: 瞭解如何使用Adobe [!DNL Target] 具有伺服器端交付的QA URL，可以執行簡單的端到端活動QA，具有永不更改的預覽連結、可選的受眾目標，以及與即時活動資料保持分段的QA報告。
title: 是否可以使用伺服器端交付來執行活動QA?
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 70%

---

# 使用透過伺服器端傳送的活動 QA

將QA URL與伺服器端傳遞一起使用 [!DNL Adobe Target] 通過預覽連結執行輕鬆的端到端活動QA，這些連結永遠不會更改，可選的受眾目標，以及保留與即時活動資料分段的QA報告。

活動 QA 標準實作支援透過 `qa_mode` 參數傳遞 `pageUrl` 參數。該方法對標準/ajax方便 [!DNL Target] 呼叫。 但若為伺服器對伺服器呼叫，無法使用 `pageUrl` 時，則對 Mobile SDK 而言不是最佳方式。

以下程式碼範例說明伺服器端呼叫的活動 QA:

```json
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
| token | 加密 Token | 無.<br>不得空白。 | 此加密實體包含可在活動 QA 中執行的活動 ID 清單。<br>[!DNL Target]驗證規則: 加密 Token 應屬於 要求中指定的用戶端。該 Token 中指定的所有活動應屬於該用戶端。 |
| bypassEntryAudience | 布林值 | False | 指定是否應評估 QA 活動的入門目標，或是否應視為相符。 |
| listedActivitiesOnly | 布林值 | 假 | 指定是否應單獨執行 QA 活動，或是否應評估為目前環境的使用中活動。 |
| evaluateAsTrueAudienceIds | ID 清單 | 空白清單。 | 應在範圍中始終計算為true的受眾ID清單 [!DNL Target] 請求。 |
| evaluateAsFalseAudienceIds | ID 清單 | 空白清單。 | 應始終在範圍中評估為false的受眾ID清單 [!DNL Target] 請求。 |
| activityIndex | 整數 | Null。<br>不得空白。 | 加密 Token 的活動索引。如果 activityIndex 不在加密 Token 活動的範圍中，或為 null，系統會加以忽略。索引從 1 開始。<br>驗證規則: 至少應有一個活動索引，並應參考 Token 中指定的活動。 |
| experienceIndex | 整數 | Null。 | 指定此參數時，請依照活動定義中的索引選取體驗。如果未指定或不在範圍內，會改回使用活動的體驗選取器策略。索引從 1 開始驗證規則: 可為 null，或應參考活動中的體驗。 |

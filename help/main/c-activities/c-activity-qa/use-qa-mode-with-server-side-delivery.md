---
keywords: qa;伺服器端;伺服器端;預覽;預覽連結
description: 瞭解如何在伺服器端傳送中使用Adobe [!DNL Target] QA URL，透過永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的QA報表，輕鬆執行端對端活動QA。
title: 使用我可以在伺服器端傳送時執行活動QA嗎？
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 59%

---

# 使用透過伺服器端傳送的活動 QA

在[!DNL Adobe Target]中使用伺服器端傳送的QA URL，來執行簡易的端對端活動QA，同時具有永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的QA報表。

活動QA的標準實作支援透過`pageUrl`引數傳遞`qa_mode`引數。 此方式便於標準/ajax [!DNL Target]呼叫。 但若為伺服器對伺服器呼叫，無法使用 `pageUrl` 時，則對 Mobile SDK 而言不是最佳方式。

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
| token | 加密 Token | 無.<br>不得空白。 | 此加密實體包含可在活動 QA 中執行的活動 ID 清單。<br>驗證規則：加密權杖應屬於[!DNL Target]要求中指定的使用者端。 該 Token 中指定的所有活動應屬於該用戶端。 |
| bypassEntryAudience | 布林值 | False | 指定是否應評估 QA 活動的入門目標，或是否應視為相符。 |
| listedActivitiesOnly | 布林值 | False | 指定是否應單獨執行 QA 活動，或是否應評估為目前環境的使用中活動。 |
| evaluateAsTrueAudienceIds | ID 清單 | 空白清單。 | 在[!DNL Target]要求的範圍內一律應評估為true的受眾ID清單。 |
| evaluateAsFalseAudienceIds | ID 清單 | 空白清單。 | 在[!DNL Target]要求的範圍內一律應評估為False的受眾ID清單。 |
| activityIndex | 整數 | Null。<br>不得空白。 | 加密 Token 的活動索引。如果 activityIndex 不在加密 Token 活動的範圍中，或為 null，系統會加以忽略。索引從 1 開始。<br>驗證規則: 至少應有一個活動索引，並應參考 Token 中指定的活動。 |
| experienceIndex | 整數 | Null。 | 指定此參數時，請依照活動定義中的索引選取體驗。如果未指定或不在範圍內，會改回使用活動的體驗選取器策略。索引從1個驗證規則開始：可以是Null，或應該參考活動中的體驗。 |

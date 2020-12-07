---
keywords: qa;server side;server-side;preview;preview links
description: 透過伺服器端傳送使用 QA URL，來執行簡易的端對端活動 QA，同時具有永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的 QA 報表。
title: 使用透過伺服器端傳送的活動 QA
feature: qa
translation-type: tm+mt
source-git-commit: 6704ac2ec73361ad95e110e9182485537d0de642
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 88%

---


# 使用透過伺服器端傳送的活動 QA{#use-activity-qa-with-server-side-delivery}

透過伺服器端傳送使用 QA URL，來執行簡易的端對端活動 QA，同時具有永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的 QA 報表。

活動 QA 標準實作支援透過 `qa_mode` 參數傳遞 `pageUrl` 參數。This approach is convenient for standard/ajax [!DNL Target] calls. 但若為伺服器對伺服器呼叫，無法使用 `pageUrl` 時，則對 Mobile SDK 而言不是最佳方式。

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
| listedActivitiesOnly | 布林值 | False | 指定是否應單獨執行 QA 活動，或是否應評估為目前環境的使用中活動。 |
| evaluateAsTrueAudienceIds | ID 清單 | 空白清單。 | List of audience IDs that should always be evaluated as true in the scope of the [!DNL Target] request. |
| evaluateAsFalseAudienceIds | ID 清單 | 空白清單。 | List of audience IDs that should always be evaluated as false in the scope of the [!DNL Target] request. |
| activityIndex | 整數 | Null。<br>不得空白。 | 加密 Token 的活動索引。如果 activityIndex 不在加密 Token 活動的範圍中，或為 null，系統會加以忽略。索引從 1 開始。<br>驗證規則: 至少應有一個活動索引，並應參考 Token 中指定的活動。 |
| experienceIndex | 整數 | Null。 | 指定此參數時，請依照活動定義中的索引選取體驗。如果未指定或不在範圍內，會改回使用活動的體驗選取器策略。索引從 1 開始驗證規則: 可為 null，或應參考活動中的體驗。 |
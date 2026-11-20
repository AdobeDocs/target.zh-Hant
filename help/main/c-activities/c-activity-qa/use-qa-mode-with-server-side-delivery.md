---
keywords: qa;伺服器端;伺服器端;預覽;預覽連結
description: 瞭解如何使用Adobe [!DNL Target] QA URL搭配伺服器端傳送，以永不變更的預覽連結、可選對象鎖定目標以及與即時活動資料保持分段的QA報表，輕鬆執行端對端活動QA。
title: 使用我可以在伺服器端傳送時執行活動QA嗎？
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
TQID: 'https://experienceleague.adobe.com/zZJmFqpXtAigTiEWMZhRqXBJqvG3ANLussSPE3-NoDA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 18%
---
# 使用透過伺服器端傳送的活動 QA {#qa-server-side}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在伺服器端[!DNL Adobe Target]呼叫中傳遞活動QA引數，以便您可以在`pageUrl`無法使用時測試活動。

>[!ENDSHADEBOX]

活動QA的標準實作支援透過`pageUrl`引數傳遞`qa_mode`引數。 此方式便於標準/ajax [!DNL Target]呼叫。 但是，它不適用於伺服器對伺服器呼叫，例如無法使用`pageUrl`的Mobile SDK實作。 在這些情況下，請在請求本身中傳遞QA引數，這會保留與即時活動資料中相同的預覽連結、選擇性對象鎖定目標和QA報表。

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

下表說明伺服器端要求的引數：

| 參數 | 類型 | 預設值 | 說明 |
|--- |--- |--- |--- |
| token | 加密 Token | 無。 不得空白。 | 包含可在活動QA中執行的活動ID清單的加密實體。<br>驗證規則：權杖必須是屬於[!DNL Target]要求中指定的使用者端的加密權杖。 Token中指定的所有活動都必須屬於使用者端。 |
| bypassEntryAudience | 布林值 | False | 指定是評估QA活動的進入步驟目標，還是將其視為相符專案。 |
| listedActivitiesOnly | 布林值 | False | 指定QA活動是單獨執行，還是評估為目前環境的作用中活動。 |
| evaluateAsTrueAudienceIds | ID 清單 | 空白清單 | 在[!DNL Target]要求的範圍內一律評估為true的對象ID清單。 |
| evaluateAsFalseAudienceIds | ID 清單 | 空白清單 | 在[!DNL Target]要求範圍內一律評估為False的受眾ID清單。 |
| activityIndex | 整數 | Null. 不得空白。 | 加密 Token 的活動索引。 如果`activityIndex`為Null或超出權杖中活動的界限，則會忽略它。 索引以1開始。<br>驗證規則：至少需要一個活動索引，而且它必須參考Token中指定的活動。 |
| experienceIndex | 整數 | Null | 指定此參數時，請依照活動定義中的索引選取體驗。 如果未指定或超出邊界，則會退回活動的體驗選擇器策略。 索引從1開始。<br>驗證規則：值可以是Null，或它必須參考活動中的體驗。 |

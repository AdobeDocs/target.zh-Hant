---
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications importer;post-tnt-action
description: 此主題包含經常詢問關於分類和使用 Analytics 做為 Target 報表來源 (A4T) 問題的回答。
title: 分類 - A4T 常見問題集
feature: a4t troubleshooting
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 67%

---


# 分類 - A4T 常見問題集{#classifications-a-t-faq}

This topic contains answers to questions that are frequently asked about classifications and using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## 使用分類匯入工具下載分類之後，如何讓 pos -tnt-action 值和活動名稱相配? {#section_6045DAC488B248418F430E663C38D001}

您可以從管理工具[分類匯入工具](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)下載 A4T/TNT 字串的分類。在匯出清單中，變數稱為 &quot;TNT&quot;。下載的資料包括活動、體驗等等的易記名稱。

對於收到 Adobe 點擊串流資料摘要的客戶，此查閱檔案非常有用。此檔案提供易記名稱給 `post_tnt` 和 `post_tnt_action` 欄。

TNT 變數的字串格式為 `activityID:experienceID:targettype|event`。

* 定位類型= 0（控制／隨機）或1(已定 [!UICONTROL 位)自動分配][!UICONTROL 和自動定位活動] 。
* Event = 0 代表體驗進入。
* Event = 1 代表體驗造訪。
* Event = 2 代表活動曝光次數。
* Event = 32767 代表活動轉換。

You can import the classification file on a frequent basis from the UI using a [browser import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) or an [FTP import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). 您也可以聯絡「工程服務」，連同點擊資料摘要一起取得此檔案作為查閱表。

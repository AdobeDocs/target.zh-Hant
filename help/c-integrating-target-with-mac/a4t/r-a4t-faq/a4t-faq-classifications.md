---
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications importer;post-tnt-action
description: 此主題包含經常詢問關於分類和使用 Analytics 做為 Target 報表來源 (A4T) 問題的回答。
title: 分類 - A4T 常見問題集
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 403a56da912fa143cf6c20b078c0bba63c6f4420
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 65%

---


# 分類 - A4T 常見問題集{#classifications-a-t-faq}

本主題包含有關分類及使用[!DNL Analytics]作為[!DNL Target](A4T)報告來源的常見問題的解答。

## 使用分類匯入工具下載分類之後，如何讓 pos -tnt-action 值和活動名稱相配? {#section_6045DAC488B248418F430E663C38D001}

您可以從管理工具[分類匯入工具](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)下載 A4T/TNT 字串的分類。在匯出清單中，變數稱為 &quot;TNT&quot;。下載的資料包括活動、體驗等等的易記名稱。

對於收到 Adobe 點擊串流資料摘要的客戶，此查閱檔案非常有用。此檔案提供易記名稱給 `post_tnt` 和 `post_tnt_action` 欄。

TNT 變數的字串格式為 `activityID:experienceID:targettype|event`。

* targettype = 0（控制／隨機）或1（目標），用於[!UICONTROL 自動分配]和[!UICONTROL 自動目標]活動。
* Event = 0 代表體驗進入。
* Event = 1 代表體驗造訪。
* Event = 2 代表活動曝光次數。
* 事件= 3-32766代表分析成功度量ID。
* Event = 32767 代表活動轉換。

您可以使用[瀏覽器讀入](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html)或[FTP讀入](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html)，經常從UI讀入分類檔案。 您也可以聯絡「工程服務」，連同點擊資料摘要一起取得此檔案作為查閱表。

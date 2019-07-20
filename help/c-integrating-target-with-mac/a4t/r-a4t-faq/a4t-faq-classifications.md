---
description: 此主題包含經常詢問關於分類和使用 Analytics 做為 Target 報表來源 (A4T) 問題的回答。
keywords: faq;常見問題集;analytics for target;a4T;分類;分類匯入程式;post-tnt-action
seo-description: 此主題包含經常詢問關於分類和使用 Analytics 做為 Target 報表來源 (A4T) 問題的回答。
seo-title: 分類 - A4T 常見問題集
solution: Target
title: 分類 - A4T 常見問題集
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 分類 - A4T 常見問題集{#classifications-a-t-faq}

此主題包含經常詢問關於分類和使用 Analytics 做為 Target 報表來源 (A4T) 問題的回答。

## 使用分類匯入工具下載分類之後，如何讓 pos -tnt-action 值和活動名稱相配? {#section_6045DAC488B248418F430E663C38D001}

您可以從管理工具[分類匯入工具](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html)下載 A4T/TNT 字串的分類。在匯出清單中，變數稱為 "TNT"。下載的資料包括活動、體驗等等的易記名稱。

對於收到 Adobe 點擊串流資料摘要的客戶，此查閱檔案非常有用。此檔案提供易記名稱給 `post_tnt` 和 `post_tnt_action` 欄。

TNT 變數的字串格式為 `activityID:experienceID:targettype|event`。

* 針對 A4T，targettype 一律為 0。
* Event = 0 代表體驗進入。
* Event = 1 代表體驗造訪。
* Event = 2 代表活動曝光次數。
* Event = 32767 代表活動轉換。

您可以使用[瀏覽器匯出](https://marketing.adobe.com/resources/help/en_US/reference/browser_export.html)或 [FTP 匯出](https://marketing.adobe.com/resources/help/en_US/reference/ftp_export.html)，經常從 UI 下載分類檔案。您也可以聯絡「工程服務」，連同點擊資料摘要一起取得此檔案作為查閱表。

---
keywords: faq;常見問題集;analytics for target;a4T;分類;分類匯入程式;post-tnt-action
description: 尋找分類和使用Analytics進行 [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] 活動的相關問題解答。
title: 我可以在哪裡找到A4T分類的相關資訊？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: cdb79c82fe1e7158a2f2014df661bd6fa852df92
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 51%

---

# 分類 - A4T 常見問題集

本主題包含經常詢問關於分類和使用[!DNL Analytics]做為[!DNL Target](A4T)報表來源問題的回答。

## 使用分類匯入工具下載分類之後，如何讓 pos -tnt-action 值和活動名稱相配? {#section_6045DAC488B248418F430E663C38D001}

您可以從管理工具[分類匯入工具](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)下載 A4T/TNT 字串的分類。在匯出清單中，變數稱為 &quot;TNT&quot;。下載的資料包括活動、體驗等等的易記名稱。

對於收到 Adobe 點擊串流資料摘要的客戶，此查閱檔案非常有用。此檔案提供易記名稱給 `post_tnt` 和 `post_tnt_action` 欄。

TNT 變數的字串格式為 `activityID:experienceID:targettype|event`。

* targettype = 0（控制/隨機）或1（鎖定），用於[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動。
* Event = 0 代表體驗進入。
* Event = 1 代表體驗造訪。
* Event = 2 代表活動曝光次數。
* 事件= 3-32766代表分析成功量度ID。
* Event = 32767 代表活動轉換。
* 事件–1或65535代表使用者已從活動或體驗中移除。 這種情況通常會在訪客轉換時發生。 訪客會從體驗中釋出，現在可供其他體驗使用。

您可以使用[瀏覽器匯入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en)或[FTP匯入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en)，經常從UI匯入分類檔案。 您也可以聯絡「工程服務」，連同點擊資料摘要一起取得此檔案作為查閱表。

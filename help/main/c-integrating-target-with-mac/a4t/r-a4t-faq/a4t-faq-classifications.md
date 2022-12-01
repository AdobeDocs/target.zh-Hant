---
keywords: faq；常見問題集；analytics for target;a4T；分類；分類匯入工具；post-tnt-action；事件程式碼
description: 尋找分類和使用的相關問題解答 [!UICONTROL Analytics for Target] (A4T)。
title: 我可以在哪裡找到A4T分類的相關資訊？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 21%

---

# 分類 - A4T 常見問題集

此主題包含經常詢問關於分類和使用之問題的回答 [!DNL Analytics] 作為的報表來源 [!DNL Target] (A4T)。

## 使用 [!UICONTROL 分類匯入工具] 若要下載分類，如何讓post-tnt-action值與活動名稱相符？ {#section_6045DAC488B248418F430E663C38D001}

+++答案您可以從管理工具下載A4T/TNT字串的分類 [分類匯入工具](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html). 變數在匯出清單中稱為「TNT」。 下載的資料包括活動、體驗等等的易記名稱。

此查閱檔案對於接收 [!DNL Adobe]的點按流資料饋送。 此檔案提供易記名稱給 `post_tnt` 和 `post_tnt_action` 欄。

標準 [!UICONTROL A/B測試] 和 [!UICONTROL 體驗鎖定] (XT)活動，TNT字串的格式為：

```
activityID:experienceID:targettype|event
```

針對 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動，TNT字串的格式為：

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` 和 `algorithmId` 使用的內部識別碼 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動。
* Event = 0 代表體驗進入。
* Event = 1 代表體驗造訪。
* Event = 2 代表活動曝光次數。
* 事件= 3-32766代表分析成功量度ID。
* Event = 32767 代表活動轉換。
* 事件–1或65535代表使用者已從活動或體驗中移除。 這種情況通常會在訪客轉換時發生。 訪客會從體驗中釋出，現在可供其他體驗使用。

您可以使用 [瀏覽器匯入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) 或 [FTP匯入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). 您也可以聯絡「工程服務」，連同點擊資料摘要一起取得此檔案作為查閱表。

+++

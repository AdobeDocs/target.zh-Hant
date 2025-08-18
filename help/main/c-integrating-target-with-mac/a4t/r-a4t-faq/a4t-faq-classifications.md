---
keywords: faq；常見問題集；analytics for target；a4T；分類；分類匯入程式；post-tnt-action；事件程式碼
description: 尋找有關分類和使用[!UICONTROL Analytics for Target] (A4T)問題的解答。
title: 我可以在哪裡找到有關使用A4T分類的資訊？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 30%

---

# 分類 - A4T 常見問題集

此主題包含經常詢問關於分類和使用[!DNL Analytics]做為[!DNL Target] (A4T)報表來源問題的回答。

## 使用[!UICONTROL Classifications Importer]下載分類之後，如何讓post-tnt-action值與活動名稱相配？ {#section_6045DAC488B248418F430E663C38D001}

+++回答
您可以從管理工具[分類匯入工具](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)下載 A4T/TNT 字串的分類。匯出清單中的變數稱為「TNT」。 下載的資料包括活動、體驗等等的易記名稱。

此查詢檔案對於接收[!DNL Adobe]點按資料流摘要的客戶非常有用。 此檔案提供易記名稱給 `post_tnt` 和 `post_tnt_action` 欄。

對於標準[!UICONTROL A/B Test]和[!UICONTROL Experience Targeting] (XT)活動，TNT字串的格式為：

```
activityID:experienceID:targettype|event
```

對於[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動，TNT字串的格式為：

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype`和`algorithmId`是[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動使用的內部識別碼。
* Event = 0 代表體驗進入。
* Event = 1 代表體驗造訪。
* Event = 2 代表活動曝光次數。
* 事件= 3-32766代表Analytics成功量度ID。
* Event = 32767 代表活動轉換。
* 事件–1或65535表示已將使用者從活動或體驗中移除。 訪客轉換時經常會發生這種情況。 訪客已從體驗中釋放，現在可以符合任何其他體驗的資格。

您可以使用[瀏覽器匯入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en)或[FTP匯入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en)，經常從UI匯入分類檔案。 您也可以聯絡「工程服務」，連同點擊資料摘要一起取得此檔案作為查閱表。

+++

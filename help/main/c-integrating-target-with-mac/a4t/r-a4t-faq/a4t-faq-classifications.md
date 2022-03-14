---
keywords: faq；常見問題；目標分析；a4T；分類；分類導入程式；post-tnt-action；事件代碼
description: 查找有關分類和使用的問題的答案 [!UICONTROL 目標分析] (A4T)。
title: 在哪裡可以找到有關A4T分類的資訊？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 29%

---

# 分類 - A4T 常見問題集

本主題包含有關分類和使用的常見問題的答案 [!DNL Analytics] 作為 [!DNL Target] (A4T)。

## 使用 [!UICONTROL 分類導入程式] 要下載分類，如何將tnt-action後值與活動名稱匹配？ {#section_6045DAC488B248418F430E663C38D001}

您可以從管理工具[分類匯入工具](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)下載 A4T/TNT 字串的分類。在匯出清單中，變數稱為 &quot;TNT&quot;。下載的資料包括活動、體驗等等的易記名稱。

此查找檔案對於接收 [!DNL Adobe]按一下流資料饋送。 此檔案提供易記名稱給 `post_tnt` 和 `post_tnt_action` 欄。

標準 [!UICONTROL A/BTest] 和 [!UICONTROL 體驗目標] (XT)活動，TNT字串的格式為：

```
activityID:experienceID:targettype|event
```

對於 [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 活動，TNT字串的格式為：

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` 和 `algorithmId` 是內部標識符， [!UICONTROL 自動分配] 和 [!UICONTROL 自動目標] 活動。
* Event = 0 代表體驗進入。
* Event = 1 代表體驗造訪。
* Event = 2 代表活動曝光次數。
* 事件= 3-32766表示分析成功度量ID。
* Event = 32767 代表活動轉換。
* 事件–1或65535表示用戶已從活動或體驗中刪除。 這種情況常在遊客轉身時發生。 訪問者將從體驗中獲釋，現在可以獲得任何其他體驗。

您可以使用 [瀏覽器導入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) 或 [FTP導入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en)。 您也可以聯絡「工程服務」，連同點擊資料摘要一起取得此檔案作為查閱表。

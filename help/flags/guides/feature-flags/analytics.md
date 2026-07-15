---
title: 報告
description: 瞭解如何使用Customer Journey Analytics檢視旗標中的功能標幟報告。
hide: true
exl-id: edddca99-f263-461b-a16f-b46ee7c15f6c
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 1%

---

# 報表 {#reporting}

旗標會透過&#x200B;**Customer Journey Analytics (CJA)**&#x200B;傳送報表。 主控台中沒有結果或報告標籤，而是每個功能標幟或功能群組上的&#x200B;**報告**&#x200B;按鈕會為該專案開啟一個限定範圍的CJA儀表板。

## 先決條件 {#prerequisites}

檢視報表之前，請確定：

1. 已為您的應用程式設定報告 — 請參閱[使用Customer Journey Analytics設定報告](#setup)。
1. 您的功能標幟或功能群組處於作用中狀態，並已累積資料。

## 檢視報告 {#view-report}

若要開啟功能標幟或功能群組的報表：

1. 導覽至主控台中的功能標幟或功能群組。
1. 選取&#x200B;**報表**。

範圍設定的Customer Journey Analytics儀表板隨即開啟，顯示該旗標或功能群組的資料。 控制面板包括：

* **參與者** — 符合功能資格的使用者總數（變體+控制組組合）
* **控制組** — 指派給控制組的使用者數目（收到預設體驗的使用者）
* **變體劃分** — 已註冊每個變體和控制組的使用者累計計數
* **每日註冊** — 顯示一段時間內每個變體和控制組中的註冊的日層級圖表

## 使用Customer Journey Analytics設定報告 {#setup}

報表需要將Customer Journey Analytics資料集連線至您的Flags應用程式。 請聯絡Flags支援或您的Adobe代表，為您的應用程式啟用報告功能。

>[!NOTE]
>
>在功能要求中傳遞的身分不需要連結到設定檔。 評估會在執行階段進行，且事件會傳送至Customer Journey Analytics。

## 另請參閱 {#see-also}

* [建立您的第一個功能標幟](create-your-first-feature-flag.md)
* [使用功能標幟的A/B測試](a-b-testing.md)
* [建立功能群組](create-a-feature-group.md)

<!-- -->

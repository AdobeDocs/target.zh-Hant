---
keywords: 發行說明；發行；更新；未來發行；增強；新功能；修正；更新；搶鮮版
description: 瞭解即將發行的Adobe Target版本（包括SDK、API和JavaScript程式庫）中包含的新功能、增強功能和修正。
title: 即將發行的版本包含哪些新功能？
feature: '  版本說明 '
translation-type: tm+mt
source-git-commit: ddc357197f6a182865c5f06930de747c143c7c38
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 21%

---


# Target 版本說明 (發行前)

本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期: 2021 年 1 月 3 日**

若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 將不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>Adobe建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免與您的網站發生任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## Target Standard/Premium 21.2.1（2021年3月9日和10日）

此維護髮行包含下列增強功能、修正和變更。

括號內的問題編號供 [!DNL Adobe] 內部使用。

* 增加允許的選件大小(TGT-38304):

   | 類型 | 上一個限制 | 新限制 |
   | --- | --- | --- |
   | HTML | 256KB | 1024KB |
   | Target UI的視覺化選件 | 64KB | 每個體驗1024 KB |
   | 透過API | 512KB | 1024KB |

* [!UICONTROL 現] 在每 [!UICONTROL 天製作Auto-Target] (AT)和 [!UICONTROL Automated Personalization] (AP)活動的個人化洞察報告。您可以選擇提供[!UICONTROL 自動化區段]或[!UICONTROL 重要屬性]的報表，以查看過去15、30和60天。 已移除45和90天選項，讓其他回顧視窗設定可每日執行。 (TGT-39472)
* 修正當客戶在活動的[!UICONTROL 目標與設定]頁面上按一下編輯相依性時，無法顯示目前相依性的問題。 (TGT-39340)
* 修正重新整理工作區的[!UICONTROL 對象庫]時的問題。 在重新整理之前，會顯示目前所選工作區的對象。 重新整理後，會顯示[!UICONTROL 預設工作區]及其觀眾。 目前的工作區及其觀眾現在會在重新整理後持續存在。 (TGT-38871)
* 修正複製[!UICONTROL Recommendations]活動，並稍後變更其准則順序編輯原始活動時的問題。 原始活動中標準序列的更改也錯誤地應用於複製的活動。 (TGT-39155)
* 修正造成[!UICONTROL Recommendations]排除顯示錯誤產品數的問題。 (TGT-39599)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

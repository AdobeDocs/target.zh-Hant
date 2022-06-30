---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: fa6324606b32f265084615fd1c13ce6c49921b48
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 55%

---

# Target 發行說明 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2022 年 6 月 30 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium]22.6.2 (2022 年 6 月 30 日)

此版本包含以下功能、增強和修復：

| 功能 | 說明 |
| --- | ---  |
| 產品內通知 | 獲取以下相關的產品內通知：<ul><li>**活動**:當活動被批准或停用時（手動或達到其開始或結束日期時），所有活動類型的通知。 通知包括活動的名稱，其中包含指向活動概述頁的連結。</li><li>**配置檔案指令碼** 在手動或目標激活或停用配置檔案指令碼時通知。</li><li>**Recommendations飼料**:在手動或由Target激活或停用Recommendations源時通知。 當Recommendations饋送失敗時也會發送通知。</li></ul> 預設情況下，產品管理員、發佈者和批准者會接收通知。 通知可在Experience Cloud首選項內配置。<br>有關詳細資訊，請參閱 [通知和公告](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements)。 |
| *Adobe Target開發人員指南* | 的 *Adobe Target開發人員指南* 合併所有 [!DNL Target] 開發人員內容。 指南包括有關實施的資訊 [!DNL Target] 和 [!DNL Recommendations]。 [!DNL Target] SDK和 [!DNL Target] API。<br>有關詳細資訊，請參見 [Adobe Target開發人員指南](https://developer.adobe.com/target/){target=_blank}。 |

* 具有「[!UICONTROL 編輯者]」角色的使用者無法在即時活動中編輯受眾。 (TGT-43582)
* 如果客戶試圖以對象名字的第一個字元 (如 !London) 的嘆號 ( ! ) 來儲存對象，就會出現警告訊號。 (TGT-43643)
* 修正導致一些客戶的對象定義細節卡顯示已結束活動仍然在進行中的問題。 (TGT-43527)

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

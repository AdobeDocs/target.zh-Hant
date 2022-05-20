---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 953b511db6d2c7ccf883d8e256c4e0ab22718862
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 99%

---

# Target 發行說明 (搶鮮版)

本文包含搶鮮版版本資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2022 年 5 月 9 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 22.5.1 (分批發行；2022 年 5 月 11 至 13 日)

我們將根據以下排程分批發行此版本：

* **5 月 11 日**：亞太 (APAC) 區域
* **5月12日**:美洲地區
* **5 月 13 日**：歐洲、中東和非洲 (EMEA) 區域

此版本包含下列增強功能和修正：

* 已修正造成 JavaScript 錯誤以及部分客戶無法存取特定 [!UICONTROL Automated Personalization] (AP) 活動的活動詳細資訊的錯誤。(TGT-43526)
* 已修正導致部分客戶無法新增 (或編輯) 特定優惠方案至 AP 活動的問題。(TGT-43503)
* 已修正 [!DNL Target] UI 中顯示下列錯誤訊息的問題：「您的全域 mbox 可能不同步。請嘗試重新儲存。」這個問題是 UI 問題，並不會影響客戶的實作。(TGT-43475)
* 已修正導致一位客戶無法編輯活動的經驗層級微調和受眾的問題 (若該微調和受眾是在部署新的[!UICONTROL 受眾] UI 之前建立的)。(TGT-43433)
* 已修正允許客戶在編輯活動的通報受眾時可選取重複 [!DNL Adobe Audience Manager] (AAM) 受眾的問題。(TGT-43430)
* 已修正導致客戶除了在不同的工作區外無法建立重複受眾的問題。 (TGT-43423)
* 已修正導致客戶對於在[!UICONTROL 表單式體驗撰寫器]中建立的活動中擁有臨時優惠方案的位置無法進行刪除的問題。(TGT-43315)
* 已修正導致客戶在按下影像優惠方案然後重新整理 UI 之後無法存取代碼優惠方案的問題。(TGT-43566)
* 已修正導致對個人資料指令碼的編輯在編輯、啟動然後停用該指令碼後恢復為原始、未編輯的指令碼的問題。該個人資料指令碼現在保持在其已編輯狀態。(TGT-43249)
* 已修正在嘗試將受眾移動到另一個工作區時導致以下錯誤的問題：「我們無法完成您的請求。如果問題仍然存在，請聯絡 Adobe 客戶服務」。(TGT-43212)
* 已修正在複製單次頁面應用程式 (SPA) 頁面的自訂代碼修正時導致錯誤的錯誤。(TGT-43137)
* 已修正導致在複製體驗接著編輯促銷後原始促銷受到影響的問題。(TGT-41775)

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

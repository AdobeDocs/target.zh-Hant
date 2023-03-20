---
keywords: 版本注意事項;發行;更新;未來發行;增強;新功能;修正;更新;版本注意事項
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7b8390042a0e15df6c05d176b2f525ddd83c9608
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Target 版本注意事項 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2023 年 3 月 20 日**

若要檢視目前版本的相關資訊，請參閱 [Target 版本注意事項](release-notes.md)。這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 23.3.1（2023年3月28日至30日）

我們將根據以下排程分批發行此版本：

* **3 月 28 日**：歐洲、中東和非洲 (EMEA) 區域
* **3 月 29 日**：亞太 (APAC) 區域
* **3 月 30 日**：美洲區域

此版本包含以下新功能、增強功能和修正：

| 功能 | 詳細資料 |
|--- |--- |
| 用於無頭個人化和實驗的AEM內容片段 | 使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 內容片段] in [!DNL Target] 活動。 將AEM的易用性和強大功能與強大的人工智慧(AI)和機器學習(ML)功能結合在 [!DNL Target] 大規模測試並個人化體驗。 |
| 為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]最佳化的 A4T 量度 | [!DNL Target]可讓您在為[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]活動使用 [!UICONTROL A4T] 時，選擇以二項式事件為基礎的量度，或是以持續事件為基礎的量度。<P>請注意受支援量度的以下變更：<ul><li>[!DNL Target] 已保留現有活動的先前行為，直到 2023 年 9 月 9 日。在此日期之後，將停止使用非支援之量度的活動，以強制現有活動遷移至新行為。</li></ul> |
| 使用 [!UICONTROL Analytics for Target] (A4T) 的[!UICONTROL 自動分配] | 更新的教學課程：<ul><li>[在  [!DNL Analysis Workspace]  中設定[!UICONTROL 自動分配]活動的 A4T 報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| 使用 [!UICONTROL Analytics for Target] (A4T) 的[!UICONTROL 自動鎖定目標] | 更新的教學課程：<ul><li>[在  [!DNL Analysis Workspace]  中設定[!UICONTROL 自動鎖定目標]活動的 A4T 報告](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

* 增強對象和活動同步，以便在中建立項目 [!DNL Adobe Experience Platform] 和 [!DNL Adobe Audience Manager] 在 [!DNL Target] UI更快。 (TGT-44568)
* 進行變更以允許使用者移除 [!UICONTROL 預設URL] 在 [!UICONTROL 管理] > [!UICONTROL 可視化體驗撰寫器] > [!UICONTROL 預設URL]. 此變更可讓客戶將預設URL變更為空白字串，此字串之前在初始設定後無法使用。 (TGT-44577)
* 移除客戶無法編輯或刪除現成可用對象（具有保留名稱的對象）的限制。 (TGT-44655)
* 已停用「[!UICONTROL 完成]「 」選項，此選項在 [!DNL Target] 建立時的UI [合併對象](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* 修正 [!UICONTROL 語言] 連結 [!UICONTROL 對象] 頁面，以便正確連結至「[!UICONTROL 帳戶通信首選項]」頁。 (TGT-43562)
* 解決客戶有時無法建立 [!UICONTROL A/B測試] 活動 [!UICONTROL Adobe Analytics] 選項 [!UICONTROL 管理] > [!UICONTROL 報表] > [!UICONTROL 報表Experience Cloud解決方案]. (TGT-44844)
* 修正客戶無法檢視 [!UICONTROL 多變數測試] 活動中有許多來自 [!UICONTROL 可視化體驗撰寫器] (VEC)。 此 [DOM路徑](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) 在VEC底部時，有時會讓客戶看不到最後一個體驗。 (TGT-44578)
* 修正VEC中的瀏覽URL無法反映一般瀏覽器工作階段中可見的目前頁面（如果頁面需要授權或叫用重新導向）的問題。 (TGT-44350)
* 修正客戶無法變更 [!UICONTROL 篩選不相容的條件] 設定 [!UICONTROL Recommendations] > [!UICONTROL 設定]. (TGT-44398)
* 修正導致POST請求建立新 [!DNL Recommendations] 使用時摘要失敗 [!UICONTROL Analytics分類] 報表套裝的名稱中有點。 (TGT-44598)
* 更新 [!DNL Target] 指向新的 [Visual Editing Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* 增強安全性，以防止 [!DNL Recommendations] 動態消息。 (TGT-43769)
* 修正客戶無法在 [!DNL Recommendations] 如果影像名稱包含 [GB18030字元](https://en.wikipedia.org/wiki/GB_18030){target=_blank}. (TGT-44614)
* 修正造成 [GB18030字元](https://en.wikipedia.org/wiki/GB_18030){target=_blank} 在 [!UICONTROL 修改] 編輯面板時 [!UICONTROL 文字/HTML] 在活動上 [!UICONTROL 體驗] 頁面。 (TGT-44600)
* 對整個 [!DNL Target] UI 進行了各種本地化修正。


## 額外的版本注意事項和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [版本注意事項：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |


## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

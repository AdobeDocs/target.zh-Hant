---
keywords: 版本注意事項;發行;更新;未來發行;增強;新功能;修正;更新;版本注意事項
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c12df34c9c7392a0ea50e8d1dea32147e8b7b165
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 52%

---

# Target 版本注意事項 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2023 年 1 月 12 日**

若要檢視目前版本的相關資訊，請參閱「[Target 版本注意事項](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 22.13.3 (2023 年 1 月 25 - 26 日)

此版本包含以下新功能、增強功能和修正：

* 使用表單式體驗撰寫器在 [!UICONTROL Automated Personalization] (AP) 活動中新增對 JSON 選件的支援。 (TGT-41460)
* 已實作 [QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md) （適用於AP活動）。 (TGT-44341)
* 中的體驗名稱 [!DNL Recommendations] 活動現在會以好記的名稱顯示，讓客戶能夠更妥善地將資料關聯至 [!DNL Adobe Analytics] 在 [!DNL Target] UI。 (TGT-41853)
* 修正 [!UICONTROL A/B測試] 和 [!UICONTROL 體驗鎖定] (XT)包含建議的活動。 此問題是由 [!DNL Target] 未能正確從 [!DNL Target] UI和 [!DNL Recommendations] 已不再使用的後端。 (TGT-44383)
* 從 [!UICONTROL 選件層級] 報表 [!UICONTROL Automated Personalization] 活動。 這項變更讓報表更容易閱讀。 (TGT-44294)
* 將「[!UICONTROL 體驗片段]」選項 [!UICONTROL 可視化體驗撰寫器] (VEC)工作流程。 該選項現在是「[!UICONTROL HTML XF]」。 (TGT-44132)
* 新增了在優惠資訊工具提示中檢視體驗片段優惠中繼資料的功能。 (TGT-43838)
* 已從 AP 和「[!UICONTROL 自動鎖定目標][!UICONTROL 個人化前瞻分析]」和「[!UICONTROL 重要屬性]」報表 ([!DNL Target] UI 中) 移除 45 天和 90 天行事曆選項。 由於使用模式並且為了改善效能，這些日期範圍已被取代。 UI 已更新以反映目前允許的範圍：15、30 和 60 天。 (TGT-39357)
* 不允許更改 [!UICONTROL 與最佳化目標相同] 設定 [!UICONTROL 目標與設定] 活動上線後的頁面。 (TGT-43923)
* 修正造成 [!DNL Target] 從 [!DNL Target Standard] to [!DNL Target Premium]. (TGT-44081 和 TGT-44306)
* 變更 [!UICONTROL 實作] 頁面([!UICONTROL 管理] > [!UICONTROL 實作])(針對「具有裝置決策功能的實作方法」，請指向說明如何對所有支援的SDK使用裝置決策功能的頁面：Node.js、Java、.NET和Python。 如需詳細資訊，請參閱 [Target SDK快速入門](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* 修正造成使用 [!DNL Scene7] 和 [!DNL Target].
* 增強 [!DNL Target] 使用內部可用性稽核的結果，為殘疾人提供UI。 這些協助工具增強功能包括存取先前無法透過鍵盤存取的功能、替代文字增強功能、縮放部分UI的功能，以及改善鍵盤焦點等。   (TGT-42759)
* 在 [!DNL Target] UI。

## 額外的版本注意事項和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [版本注意事項：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |


## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

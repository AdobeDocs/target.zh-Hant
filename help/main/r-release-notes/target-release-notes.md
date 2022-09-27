---
keywords: 版本注意事項;發行;更新;未來發行;增強;新功能;修正;更新;版本注意事項
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bd12d615b784b26e2b5a7b9e391f3e7d5a9cc8c5
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Target 版本注意事項 (搶鮮版)

本文包含搶鮮版版本資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新日期：2022 年 27 月 9 日**

若要檢視目前版本的相關資訊，請參閱「[Target 版本注意事項](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 22.10.1（錯開發行，2022年10月4日至6日）

我們將根據以下排程分批發行此版本：

* **10月4日**:歐洲、中東和非洲(EMEA)地區
* **10月5日**:亞太地區
* **10月6日**:美洲地區

此版本包含下列新功能、增強功能和修正：

| 功能 | 詳細資料 |
| --- | --- |
| 新增 [!UICONTROL 可視化體驗撰寫器] Google Chrome擴充功能 | 新 [!DNL Adobe Target] [!UICONTROL 可視化體驗撰寫器] Chrome線上應用程式(VEC)擴充功能已在Chrome線上應用程式商店中推出。<br>自2023年1月起， [!DNL Target] VEC Helper擴充功能將在Google Chrome中停止運作，因為Google不允許使用資訊清單V2的擴充功能。 下載新的擴充功能，以繼續在中以視覺化方式撰寫您的網站 [!DNL Target] 從新年開始。 |
| 針對 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標]<br>（確切的發行日期待定。） | 請注意下列變更：<ul><li>新增對二進位和最大化量度的支援，於 [!UICONTROL Analytics for Target] 適用於 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標] 活動</li><li>移除的二進位量度警告訊息 [!UICONTROL 自動鎖定目標] 活動</li><li>保留現有活動的行為，直到2023年2月20日。 在此日期後，活動將停止，以強制現有活動移轉至新行為</li><li>自2023年2月20日起，支援 `averagetimespentonsite`, `bouncerate`，和 `entries` 量度 [!DNL Target] 活動將遭取代。</li></ul> |

* 修正對象規則資訊無法在 [!UICONTROL 受眾細分] 資訊窗口。 (TGT-43917)
* 改善 [!DNL Target] 載入接近 [目標規則的建議限制](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* 修正造成部分元件無法正確顯示於 [!UICONTROL 修改] 面板 [!UICONTROL 體驗] 頁面時(從 [!UICONTROL 撰寫] to [!UICONTROL 瀏覽] 模式。 (TGT-43300)
* 修正部分客戶無法封存的問題 [!UICONTROL A/B測試] 使用的活動 [!UICONTROL 自動鎖定目標]. (TGT-40978)
* 新增在單一報表群組內的多個位置自動使用單一選件的功能。 (TGT-43974)
* 新增可依下列類型(HTML或JSON)篩選體驗片段的功能： [!UICONTROL 選件] 清單。 (TGT-43121)
* 修正允許客戶插入JSON的問題 [!UICONTROL 體驗片段] 不支援的VEC時提供選件。 JSON選件只能在使用 [!UICONTROL 表單式體驗] 撰寫器。 (TGT-43846)

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

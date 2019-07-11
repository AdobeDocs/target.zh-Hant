---
description: 這些發行說明提供最新或即將到來[！DNL Adobe Target]發行。
keywords: 版本說明
seo-description: 這些發行說明提供最新或即將到來[！DNL Adobe Target]發行。
seo-title: Adobe Target發行說明(搶鮮版)
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: ce1758df44740213a2d9011ee43f84cb52f6a29d

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新日期: 2019 年 7 月 9 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會變更，恕不另行通知。若要檢視關於最新版本的資訊，請參閱 [Target 發行說明](release-notes.md)。視發行的時間點而定，這些頁面上的資訊可能相同或有所不同。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1 (2019 年 7 月 23 日) {#tgt-19-7-1}

此版本包含下列新功能和增強功能:

| 功能 / 增強功能 | 說明 |
| --- | --- |
| 可視化體驗撰寫器 (VEC) | When you click an image then click [!UICONTROL Replace With], two new options display:<ul><li>**HTML**：您可以使用HTML取代影像，讓您完全控制元素，而不需選取父元素來存取HTML選項。</li><li>**體驗片段**：您可以使用Adobe Experience Manager(AEM) [體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md) 取代影像，以便快速插入Target活動中AEM中建立的元素。</li></ul>(TGT-34097) |
| 行動應用程式可視化體驗撰寫器 | Mobile App CMS會顯示新的「修改」面板，顯示您已設定用於點按追蹤的元素。(TGT-31741) |
| ![A/B測試與體驗定位(XT)活動](/help/assets/premium.png)<br>中的Premium BadgereCommendations | Recommendations(演算法)狀態會顯示在「概述」頁面上，用於A/B測試和包含Recommendations選件的XT活動。狀態包括：Results Ready、Results not Ready和Feed fails.(TGT-33649) |
| 透過Experience Cloud ID(ECID)程式庫對at. js2.0+的跨網域追蹤支援 | 以前，at. js不支援跨網域追蹤。*x* 版本不支援此函數。在此版本中，使用at. js2.0或更新版本的客戶現在可以透過ECID程式庫使用跨網域追蹤。必須將ECID程式庫與at. js2.0或以上版本一起安裝在頁面上，才能讓跨網域追蹤運作。It is highly recommended to use [Experience Cloud ID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html). |

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到有關 Target 和其他 Adobe Experience Cloud 解決方案的未來產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

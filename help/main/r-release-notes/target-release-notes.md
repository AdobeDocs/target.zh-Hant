---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 729b88c3db9e88a5cd428587e34614c5d56542da
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 34%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年3月7日**

>[!NOTE]
>
>發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.3.5 （2025年3月11日）

此版本包含下列修正和更新：

* 已解決阻止使用者變更[!UICONTROL Modifications]面板中選件的問題。 (TGT-51800)
* 解決動作在體驗和對象（包括在[!UICONTROL ClickTrack]模式下）的左側面板中無法正確顯示的問題。 (TGT-51895)
* 解決[!UICONTROL ClickTrack]選取器未套用至正確對象頁面的問題。 (TGT-51871)

## [!DNL Target Standard/Premium] 25.3.4 （2025年3月7日）

此版本包含下列修正和更新：

* 解決在[!UICONTROL Audiences]面板中看不到僅限於此活動的對象的問題，使其無法編輯或重複使用。 (TGT-51860)
* 修正封鎖[!DNL Target Standard]客戶使用[!UICONTROL Analytics for Target] (A4T)報告建立活動的問題。 (TGT-51854)
* 修正在批次建立和編輯作業期間，從承載中排除本機ID計數器的問題。 (TGT-51867)

## [!DNL Target Standard/Premium] 25.3.2 （2025年3月6日）

此版本包含下列修正和更新：

* 修正複製具有僅限於此活動對象的活動時，無法建立新活動，錯誤地使用原始活動的對象的問題。 (TGT-51855)
* 修正無法編輯僅限於此活動受眾的[!UICONTROL Experience Targeting] (XT)活動的問題。 (TGT-51846)
* 修正[!UICONTROL Visual Experience Composer] (VEC)在第一次編輯時無法正確套用修改至體驗的問題。 (TGT-51843)
* 修正按一下VEC內特定元素時觸發「ID」錯誤的問題。 (TGT-51814)
* 在活動建立期間更新VEC中的錯誤處理。 (TGT-51759)
* 修正[!UICONTROL Modifications]面板中缺少檢視在儲存活動時造成「無效使用者輸入」錯誤的問題。 (TGT-51827)
* 修正無法建立Recommendations條件的問題。 (TGT-51834)
* 在重新導向至其他URL之前新增確認訊息。 (TGT-51703)
* 修正選件和資料夾中GraphQL整合測試的問題。 (TGT-51839)

## [!DNL Target Standard/Premium] 25.3.1 （2025年3月3日）

此版本包含下列修正和更新：

* 合併的對象可包含子群組，每個子群組都包含多個對象。 此版本修正子群組對象無法在[!UICONTROL Rules]對話方塊中顯示的問題。 (TGT-51813)
* 解決在開啟舊版活動時，某些體驗對象會被[!UICONTROL All Visitors]取代的問題。 (TGT-51812)
* 已解決無法編輯僅限於此活動的受眾之活動的問題。 (TGT-51807)
* 解決無法在更新的[!DNL Target] UI中編輯頁面標題修改的問題。 (TGT-51797)
* 解決複製體驗、刪除其他體驗，然後嘗試儲存活動時發生的Null錯誤。 (TGT-51796)
* 解決在建立活動的[!UICONTROL Targeting]步驟期間，對象排除規則無法顯示在對象資訊面板中的問題。 (TGT-51579)
* 更新韓文本地化的錯誤訊息。 (TGT-51701 和 TGT-51699)

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

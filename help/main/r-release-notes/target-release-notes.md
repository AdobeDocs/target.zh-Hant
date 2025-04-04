---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: ca14a94365e75704622e76ac13aab324fc836e09
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 43%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年4月2日**

>[!NOTE]
>
>發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.4.1 （2025年4月2日）

此版本包含下列修正和更新：

* 修正造成體驗對象從活動中消失的問題。 (TGT-52003)
* 修正傳送期間造成非預期元素的問題。 (TGT-52011)
* 修正阻止客戶在Ove[!UICONTROL r]檢視頁面上的目標圖形中及活動編輯期間檢視對象的問題。 (TGT-52050)
* 已修正導致客戶無法在[!UICONTROL Experience Targeting] (XT)活動中依優先順序重新排序體驗的問題。 (TGT-52054)
* 修正復原文字樣式變更時，造成轉譯錯誤的問題。 (TGT-51876)
* 修正修改重新導向選件時，[!DNL Target]也會移除與該選件相關聯的任何[!UICONTROL ClickTrack]選取器的問題。 (TGT-51936)
* 修正取消[!UICONTROL ClickTrack]時，[!DNL Target]無法正確儲存選取器的問題。 (TGT-51937)
* 修正在[!UICONTROL Goals & Settings]頁面上開啟和關閉mbox選擇器（未進行任何變更）後，觸發無效名稱錯誤的問題。 (TGT-51983)
* 修正封鎖編輯在舊版[!DNL Target] UI中建立的臨時優惠的問題。 (TGT-51984)
* 修正封鎖編輯具有包含自訂程式碼的臨時優惠方案的活動的問題。 (TGT-51995)
* 修正在編輯合併的受眾定義時，排除規則顯示為包含規則的問題。 (TGT-51999)
* 修正導致自訂程式碼在體驗編輯期間無法正確顯示的問題。 (TGT-52005)
* 修正[!UICONTROL Insert Before]選項無法用於導覽列前插入內容的問題。 (TGT-52031)
* 修正無法正確反白報告預設體驗的問題。 (TGT-51716)
* 修正建立活動時觸發`default message [Invalid optionLocalIds: xx]]`訊息的問題。 (TGT-52038)

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

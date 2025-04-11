---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新、目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: b9ec7af30fda6e97e3b0372a02a682a177764742
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 34%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 25.4.3 （2025年4月11日）

此版本包含下列修正和更新：

* 修正導致客戶無法開啟特定[!UICONTROL Experience Targeting] (XT)活動的對象資訊快顯視窗的錯誤。 (TGT-52049)
* 修正在[!UICONTROL Visual Experience Composer] (VEC)中完成變更後，對象設定恢復為&quot;[!UICONTROL All Visitors]&quot;的問題。 (TGT-52132)
* 修正未針對特定活動顯示對象細分的問題(TGT-52057)
* 修正客戶無法在預設工作區中插入[!UICONTROL Experience Fragment]的問題。 (TGT-52073)
* 修正了針對[!UICONTROL Automated Personalization] (AP)活動，選件顯示為「找不到內容」且未顯示在[!UICONTROL Offers]頁面的問題。 (TGT-52150)
* 新增在活動中允許重複受眾的功能。 (TGT-51200)
* 修正編輯後XT活動的[!UICONTROL Goals & Settings]頁面上顯示錯誤mbox名稱的問題。 (TGT-52026)
* 修正`defaultContent`不在`experiences/optionLocations`中卻顯示在選項中的問題。 (TGT-52036)
* 修正確保空白字串未轉換為Null值的問題。 (TGT-52037)
* 已修正要求客戶在編輯[!UICONTROL Goals & Settings]頁面上的[!UICONTROL Reporting Settings]中重新設定[!UICONTROL Optimization Goal]的問題。 (TGT-52071)
* 修正無頁面傳送規則的活動在[!UICONTROL Overview]頁面上顯示多個規則的問題。 (TGT-52084)
* 新增錯誤訊息，說明使用者嘗試以基本多語言平面以外的字元（例如表情符號）儲存優惠方案。 (TGT-52105)
* 修正開啟活動觸發錯誤訊息的問題：「此活動使用一或多個在來源中刪除的對象。」 (TGT-52120)
* 修正在編輯期間ClickTrack量度未顯示在更新的[!UICONTROL Visual Experience Composer] (VEC)中的問題。 (TGT-52152)
* 修正具有查詢引數作為活動位置的URL未在活動的[!UICONTROL Overview]頁面上顯示查詢引數的問題。 (TGT-51635)
* 修正無法在[!UICONTROL Visual Experience Composer] (VEC)的[!UICONTROL Browse mode]中顯示整個體驗URL的問題。 (TGT-52101)
* 修正編輯活動導致頁面傳送在URL結尾新增「/」使其無效的問題。 (TGT-52114)
* 修正[!UICONTROL Form-Based Experience Composer]中的[!UICONTROL Activity QA]連結不正確地重新導向至[!DNL Adobe Experience Cloud]首頁的問題。 (TGT-52055)
* 修正儲存及重新開啟後，新增至[!UICONTROL A/B Test]活動的其他頁面未保留的問題。 (TGT-51994)
* 已修正導致客戶無法刪除內嵌樣式區段中的樣式的問題。 (TGT-52070)
* 已還原存取[!UICONTROL Activity QA]對話方塊中的[對象定義卡](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780)，類似於舊版UI。 (TGT-52056)
* 更新後的UI未儲存頁面或對象而未經修改。 如果客戶將新頁面或對象新增至活動，但未進行變更，[!DNL Target]會在儲存時捨棄未修改的對象。 已在相關位置新增通知，以通知使用者此行為。 (TGT-52104)

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

## at.js 2.11.8版（2025年3月31日）

* 解決字串尾碼驗證中CodeQL識別的漏洞，以防止在調整大小和移動作業期間出現邊緣案例。 (TNT-51516)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |

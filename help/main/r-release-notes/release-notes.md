---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新、目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: bdc2f76af2a1f1554556d56a983748aa2c9caf2c
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 31%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 25.3.7 （2025年3月26日）

此版本包含下列修正和更新：

* 解決修改頁面後刪除時，無法儲存多頁活動的問題。 (TGT-51988)
* 解決編輯活動時發生的錯誤： `default message [Invalid optionLocalIds: xx]]`。 (TGT-51985)
* 解決在活動新增修改並移除現有修改的問題。 (TGT-51981)
* 解決在活動建立或編輯期間，將對象取代為「[!UICONTROL All visitors]」所導致「不允許重複的對象」錯誤的問題。 (TGT-51978)
* 解決儲存[!UICONTROL A/B Test]活動時造成「使用者輸入無效」錯誤的問題。 (TGT-51976)
* 解決計算量度無法在[!UICONTROL Goals & Settings]頁面上正確顯示的問題。 (TGT-51975)
* 已解決無法在`pageviews`量度的[!DNL Analytics]設定中比對`companyName`與`reportSuite`的問題。 (TGT-51965)
* 解決在活動中切換體驗時移除修改的問題。 (TGT-51945)
* 解決移除頁面對象時也移除[!UICONTROL ClickTrack]選取器的問題。 (TGT-51935)
* 解決在開啟[!UICONTROL Overview]頁面後導致活動無法編輯的問題。 (TGT-51931)
* 已解決在建立活動期間造成`[Unused optionLocalIds: 0]]`錯誤的問題。 (TGT-51920)
* 解決移除文字樣式變更後，部分變更未正確轉譯的問題。 (TGT-51876)
* 已解決導致目標對象無法在[!UICONTROL Form-Based Experience Composer]中正確更新的問題。 (TGT-51845)
* 解決[!UICONTROL Visual Experience Composer]中的URL在活動導覽期間未正確更新的問題。 (TGT-51832)
* 解決在建立活動和新增優惠方案時，無法正確顯示優惠方案在[!UICONTROL Offers] UI中的問題。 (TGT-51805)
* 解決當無法傳遞個人化或目標內容時，部分活動缺乏後援畫面以顯示預設內容的問題。 (TGT-51638)
* 解決無法在[!UICONTROL Offers] UI中正確顯示即時優惠方案和某些資料夾的問題。 (TGT-51628)
* 解決部分URL字串和goURL無法正確當地語系化的問題。 (TGT-35741)
* 修正了無法在[!DNL Target] UI中正確當地語系化角色（[!UICONTROL Approver]、[!UICONTROL Editor]和[!UICONTROL Observer]）的問題。 (TGT-29925)

## [!DNL Target Standard/Premium] 25.3.6 （2025年3月14日）

此版本包含下列修正和更新：

* 解決當多次使用相同的[!UICONTROL ClickTrack]選取器時，[!UICONTROL Visual Experience Composer] (VEC)活動中已啟用[!UICONTROL Click Tracking]的「使用者輸入無效」錯誤。 (TGT-51921)
* 已修正在具有共用位置(例如HEAD選擇器)和相同選件的VEC活動中出現「無效使用者輸入」錯誤。 (TGT-51879)
* 已修正導致體驗修改在對象之間共用的問題。 (TGT-51815)
* 解決建立活動時因區段ID衝突而發生的驗證錯誤。 [!DNL Target]偵測到使用匿名區段的現有活動時發生錯誤。 (TGT-51784)
* 解決[!DNL Target]無法在對象中儲存具有排除規則的活動的問題。 (TGT-51581)
* 已解決導致客戶無法建立、刪除或行動資料夾而無法存取預設工作區的問題。 (TGT-51499)
* 解決在擷取[!DNL Analytics]量度清單時，導致GET要求失敗的問題。 (TGT-51106)

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

---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新、目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 0618d39fc5966c64cceea8f5bcccb625fc243ebb
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 47%

---

# [!DNL Target] 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。 此外，也會隨附 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的發行說明以及其他平台變更 (如適用)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## Target許可權更新（2025年4月22日）

此未來更新加強了組織對[!DNL Target]執行個體設定的控制，防止了可能影響跨各種測試和個人化團隊的活動傳送的意外更新。

自2025年4月22日起，只有[!UICONTROL Product]和[!UICONTROL Solutions]管理員能更新[!UICONTROL Administration]區段中的設定，無論他們在[!DNL Target]工作區中的角色為何。 沒有此許可權的使用者將擁有[!UICONTROL Administration]區段的唯讀存取權。

如需詳細資訊，請參閱[管理Target](/help/main/administrating-target/start-target.md)。

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

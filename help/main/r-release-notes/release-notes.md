---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
hold: true
source-git-commit: 44d9cd4de7ff2064e6005a4d7ece7f37194fbf2f
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 41%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 您需要瞭解的時間性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

針對與[!DNL Adobe Target]和您的實作相關的時效性更新，[!DNL Adobe]會透過[!UICONTROL Experience League]提供詳細的發行說明和檔案。 以下是和您的實作相關的一些重點專案：

### [!DNL Target] UI版本切換為棄用

如需詳細資訊，請參閱[[!DNL Target] UI更新常見問題](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 26.3.2 （2026年3月10日）

**活動**

+++檢視詳細資料

* **體驗中的直接優惠變更未儲存。**&#x200B;此修正解決在活動體驗內對直接優惠方案所做的修改未儲存的問題。 先前，使用者開啟直接選件、進行變更並儲存時，變更似乎會在最初反映但重新開啟選件時遺失。 此修正可確保直接選件的變更會正確儲存，並在重新開啟選件時持續存在。 (TGT-54653)

+++

**實施**

+++檢視詳細資料

* **在[實作]畫面中新增忽隱忽現的管理切換。**&#x200B;已在[!UICONTROL Implementation]畫面中新增切換功能，以控制啟用忽隱忽現管理設定。 此切換可讓管理員直接從「實施」畫面設定忽隱忽現管理。 (TGT-52247)

+++

**概述**

+++檢視詳細資料

* **在概觀頁面中顯示對象和體驗的全名。**&#x200B;此增強功能會更新[!UICONTROL Overview]頁面以顯示對象和體驗的完整名稱。 以前，長名稱會被截斷，而且無法完全顯示，因此使用者必須按三下才能選取所有文字來檢視完整名稱。 此更新可確保看到完整的對象和體驗名稱，讓使用者更容易識別和檢閱活動設定。 (TGT-53323)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++檢視詳細資料

* **VEC變更未反映在使用Shadow DOM (Salesforce Lightning Web Components)的網站上。**&#x200B;此修正解決使用Lightning Web Components (LWC)的Salesforce網站中，Adobe Target所做的變更(例如CTA色彩變更)無法儲存或反映在即時網站上的問題。 CMS不接受來自Target活動的更新，且此問題在A/B測試和其他活動型別中持續發生。 (TGT-54059)

+++

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
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |

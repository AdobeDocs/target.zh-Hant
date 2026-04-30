---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7976d43e43baeabdb68509373f1b0b72bbe723b3
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 49%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 您需要瞭解的時間性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

針對與[!DNL Adobe Target]和您的實作相關的時效性更新，[!DNL Adobe]會透過[!UICONTROL Experience League]提供詳細的發行說明和檔案。 以下是和您的實作相關的一些重點專案：

### [!DNL Target] UI版本切換為棄用

如需詳細資訊，請參閱[[!DNL Target] UI更新常見問題](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 26.4.4 （2026年4月28日）

**活動**

+++檢視詳細資料

* **報表中的對象篩選器發生錯誤。** 修正在&#x200B;**[!UICONTROL Goals & Settings]**&#x200B;內變更對象篩選條件，導致[!DNL Target]使用者介面的「報表」區段發生錯誤的問題。 (TGT-55006)

* **依優先順序排序活動。** 使用&#x200B;**[!UICONTROL Priority]**&#x200B;欄標題在活動清單中新增依優先順序排序，其遞增和遞減順序與其他可排序的欄一致。 (TGT-54948)

* **其他活動屬性在儲存後未保留。** 修正儲存及重新開啟活動後，特定&#x200B;**[!UICONTROL Properties]**&#x200B;選取範圍未持續存在的問題。 (TGT-53889)

+++

**本地化**

+++檢視詳細資料

* [!UICONTROL Page Delivery]規則運運算元的&#x200B;**日文標籤。** 修正日文UI中頁面傳送規則運運算元標籤無法讀取或損毀的字串。 (TGT-53097)

+++

**API**

+++檢視詳細資料

* **報告`segmentId`.**&#x200B;的[!DNL GraphQL] API支援 已新增`segmentId`至報表[!DNL GraphQL] API。 (TGT-55021)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++檢視詳細資料

* **編輯器中錯誤體驗上顯示的修改。** 修正在[!UICONTROL Visual Experience Composer]中的體驗之間切換後，刪除或其他修改可能出現在錯誤體驗的問題。 (TGT-54955)

* **刪除插入HTML時移除的修改。** 修正刪除以&#x200B;**[!UICONTROL Insert before]**&#x200B;或&#x200B;**[!UICONTROL Insert after]**&#x200B;新增的額外&#x200B;**[!UICONTROL HTML]**&#x200B;區塊時，也會移除無CSS選取器的連結修改的問題。 (TGT-54530)

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)




**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

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
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |

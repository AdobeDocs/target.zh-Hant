---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 3fc6930bcff97685e6f3f6dab1a32db05fbfed8a
workflow-type: tm+mt
source-wordcount: 612
ht-degree: 44%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 26.6.5 （2026年6月17日）

**活動**

+++檢視詳細資料

* **活動使用在來源刪除的對象時發生錯誤。** 修正您會看到錯誤訊息，指出活動使用一或多個已從來源刪除的對象的問題。 (TGT-55272)

+++

**[!UICONTROL 目標分析] (A4T)**

+++檢視詳細資料

* **A4T報告不可見。** 修正[!UICONTROL Analytics for Target] (A4T)報告未顯示的問題。 (TGT-55432)

+++

## [!DNL Target Standard/Premium] 26.6.4 （2026年6月16日）

**活動**

+++檢視詳細資料

* 在更新的[!DNL Target] UI中&#x200B;**[!UICONTROL 儲存並關閉]。** 已在更新的[!DNL Target] UI中還原&#x200B;**[!UICONTROL 儲存並關閉]**&#x200B;選項。 (TGT-55152)

* 在更新的[!DNL Target] UI中的&#x200B;**QA URL。** 修正QA URL在更新的[!DNL Target] UI中無法正常運作的問題。 ([TGT-55110](https://jira.corp.adobe.com/browse/TGT-55110))

+++

**本地化**

+++檢視詳細資料

* **活動概觀圖表報表中的未當地語系化百分比格式。** 修正&#x200B;**[!UICONTROL 活動概覽]**&#x200B;頁面上&#x200B;**[!UICONTROL 報表]**&#x200B;索引標籤的&#x200B;**[!UICONTROL 圖表檢視]**&#x200B;中，百分比格式未當地語系化圖表的問題。 (TGT-50100)

* 活動URL中有&#x200B;**個日文字元。** 修正活動URL中的日文字元在&#x200B;**[!UICONTROL 活動概覽]**&#x200B;頁面上以及活動清單中，在您儲存活動後損毀的問題。 (TGT-53459)

* 預設活動名稱中有&#x200B;**未當地語系化的時間戳記。** 修正您在活動建立期間保留預設活動名稱時，活動標題中的時間戳記未當地語系化的問題。 (TGT-53273)

+++

**[!UICONTROL 推薦]**

+++檢視詳細資料

* 建立摘要後URL中有&#x200B;**多位元組字元。** 修正在您建立摘要後URL中多位元組字元似乎損毀的問題。 (TGT-54793)

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)

**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## 您需要瞭解的時間性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

針對與[!DNL Adobe Target]和您的實作相關的時效性更新，[!DNL Adobe]會透過[!UICONTROL Experience League]提供詳細的發行說明和檔案。 以下是和您的實作相關的一些重點專案：

### [!DNL Target] UI版本切換為棄用

如需詳細資訊，請參閱[[!DNL Target] UI更新常見問題](/help/main/c-intro/updated-ui-faq.md)。

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

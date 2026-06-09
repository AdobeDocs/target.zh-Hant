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
source-git-commit: 391653c7a45a48c311c6a6cff358bd077f8c47b7
workflow-type: tm+mt
source-wordcount: 652
ht-degree: 41%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 26.6.1 （2026年6月4日）

**活動**

+++檢視詳細資料

* [!UICONTROL 活動總覽].**上的**&#x200B;不完整的活動URL 修正[!UICONTROL 活動概覽]未顯示活動完整URL的問題。 (TGT-54029)

* **活動報表中有未本地化的日期格式。** 修正從&#x200B;**[!UICONTROL 預設日期範圍]**&#x200B;下拉式清單中選擇&#x200B;**最近X天**&#x200B;選項時，**[!UICONTROL 報表]**&#x200B;索引標籤上未當地語系化日期格式的問題。 (TGT-51637)

* **無法在[!UICONTROL 位置].**&#x200B;中儲存含特定GB18030字元的表單式活動 修正當&#x200B;**[!UICONTROL 位置]**&#x200B;欄位包含特定GB18030字元時，無法儲存表單式活動的問題。 (TGT-46980)

+++

**[!UICONTROL 客群]**

+++檢視詳細資料

* **建立簡體中文和繁體中文受眾流程中未本地化的行事曆。** 修正建立對象流程期間，**[!UICONTROL 時間範圍]**&#x200B;屬性的&#x200B;**[!UICONTROL 開始]**&#x200B;和&#x200B;**[!UICONTROL 結束]**&#x200B;欄位中的行事曆未以簡體中文(CHS)和繁體中文(CHT)語言環境進行當地語系化的問題。 (TGT-50619)

+++

**[!UICONTROL 視覺化體驗撰寫器] (VEC)**

+++檢視詳細資料

* 在更新的活動產生器中&#x200B;**未本地化的工具提示。** 修正更新的[!UICONTROL 視覺化體驗撰寫器]活動產生器中&#x200B;**[!UICONTROL 細分]**&#x200B;和&#x200B;**[!UICONTROL 內容]**&#x200B;資訊工具提示未本地化的本地化問題。 (TGT-53721)

* [!UICONTROL 體驗對象].**中的**&#x200B;未當地語系化的[!UICONTROL 所有訪客] 修正左側邊欄中&#x200B;**[!UICONTROL 體驗對象]**&#x200B;的&#x200B;**[!UICONTROL 所有訪客]**&#x200B;字串未在[!UICONTROL 視覺化體驗撰寫器]中當地語系化的問題。 (TGT-50086)

+++

**[!UICONTROL 報表]**

+++檢視詳細資料

* 在[!UICONTROL 建立預設集]視窗中&#x200B;**未本地化的日期格式。** 修正&#x200B;**[!UICONTROL 建立預設集]**&#x200B;視窗的&#x200B;**[!UICONTROL 日期範圍]**&#x200B;欄位中的日期格式未當地語系化的問題。 (TGT-49239)

+++

**本地化**

+++檢視詳細資料

* 在多個區域顯示&#x200B;**GB18030字元。** 修正部分私人使用區域字元在&#x200B;**[!UICONTROL 對象]** UI、**[!UICONTROL 管理]** > **[!UICONTROL 屬性]**、行動檢視區設定和快顯通知中錯誤顯示為字母的問題。 （TGT-49622、TGT-49623、TGT-49624和TGT-49625）

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
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |

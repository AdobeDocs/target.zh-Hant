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
source-git-commit: f2220f2f01c0bddc96dd7720ff207e1256c13b55
workflow-type: tm+mt
source-wordcount: 633
ht-degree: 42%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)


## 最新更新 — 2026年5月12日

**[!DNL Adobe Target]MCP伺服器（公用Beta）**

[!DNL Adobe Target]現在提供MCP （模型內容通訊協定）伺服器，直接在任何MCP相容應用程式中呈現實驗、個人化和報告作業。 透過這項整合，行銷和技術人員可以檢查A/B測試、分析效能報表、管理對象和選件，以及採取控管動作 — 所有動作都使用自然語言提示，而不是導覽多個UI熒幕或針對[!DNL Adobe Target] REST API撰寫查詢。 此功能目前可在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中使用。

此功能適用於公開Beta中的所有客戶。

如需詳細資訊，請參閱[[!DNL Adobe Target] MCP伺服器](../c-integrating-target-with-mac/mcp/target-mcp.md)。


## [!DNL Target Standard/Premium] 26.5.1 （2026年5月7日）

**整合**

+++檢視詳細資料

* Experimentation Accelerator中的&#x200B;**[!DNL Adobe Target]管理。** 新增將[!DNL Target]工作區指派至Experimentation Accelerator沙箱的支援，讓團隊可以在Experimentation Accelerator中一個位置檢視來自[!DNL Adobe Target]的實驗。 [了解更多](../c-integrating-target-with-mac/experimentation-accelerator.md)

+++

**活動**

+++檢視詳細資料

* **[!UICONTROL Graph View]與資料表和下載不同步。** 修正某些日期範圍的活動報表在&#x200B;**[!UICONTROL Graph View]**&#x200B;中可能顯示缺少或零量度的問題，即使&#x200B;**[!UICONTROL Table View]**&#x200B;且下載的報表仍顯示正確的值。 (TGT-54998)

+++

**[!UICONTROL Audiences]**

+++檢視詳細資料

* **對象使用清單未完全轉譯。** 修正即使有其他活動與該對象相關聯，對象詳細資料中的&#x200B;**[!UICONTROL Usage]**&#x200B;區段仍只能顯示對應活動的子集的問題。 (TGT-55094)

+++

**[!UICONTROL Administration]**

+++檢視詳細資料

* **確認最後一個八位元IP模糊化的效果更清楚。** 當您在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**&#x200B;上將&#x200B;**[!UICONTROL Obfuscate Visitor IP addresses]**&#x200B;變更為&#x200B;**[!UICONTROL Last octet]**&#x200B;時，確認對話方塊現在會說明[!DNL Target]會隱藏訪客IP位址的最後八位元。 (TGT-44821)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++檢視詳細資料

* **使用增強體驗撰寫器(EEC)的空白或不完整頁面。** 修正啟用&#x200B;**[!UICONTROL Enhanced Experience Composer]**&#x200B;時，[!UICONTROL Visual Experience Composer]無法在編輯器中載入網站的問題。 (TGT-54576)

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

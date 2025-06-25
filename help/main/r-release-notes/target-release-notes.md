---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c882a5eb6530f3b3fe44484ee580beadeddaae23
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 29%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年6月25日**

>[!NOTE]
>
>* 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>* 若要檢視目前版本的相關資訊，請參閱[Target發行說明](release-notes.md)。
>
>* 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.6.4 （2025年6月26日）

此版本包含下列修正和更新：

* 已將[!UICONTROL Rearrange]選項新增至更新的[!UICONTROL Visual Experience Composer] (VEC) UI，以符合舊版VEC中可用的功能。 (TGT-46957 和 TGT-52876)
* 修正了[!UICONTROL A/B Test]活動中變體體驗（例如體驗B）的修改未保留的問題。 在體驗之間切換後，對變數的變更將會消失。 此問題不會影響控制體驗。 (TGT-52664)
* 已修正某些客戶無法建立或儲存活動，而其他客戶則可順利執行相同動作的問題。 不同帳戶之間的問題不一致。(TGT-52842)
* 修正擷取[!UICONTROL Automated Personalization] (AP)活動的報告資料時發生Null指標例外狀況。 (TGT-52362)
* 已修正導致選件層級詳細資料無法在[!UICONTROL Automated Personalization] (AP)活動的.CSV檔案中顯示的問題。 (TGT-52675)
* 在更新的VEC中套用修改時，最初會顯示正確的變更，包括預期的[!UICONTROL Experience Fragment]。 不過，在切換體驗或進行其他編輯時，由於選取器問題，某些修改無法套用。 (TGT-52679)
* 修正複製現有活動以建立新活動時，複製活動中的QA連結錯誤地保留原始活動的頁面URL的問題。 (TGT-52775)
* 修正無意中導致[!UICONTROL On-device Decisioning]無法在更新的VEC中使用的問題。 (TGT-52371)
* 修正無法編輯產品[!DNL Recommendations]活動的問題。 嘗試透過Target UI存取VEC時，[!UICONTROL Overview]頁面上出現錯誤，導致無法進行任何編輯。 (TGT-52823)
* 修正當體驗名稱超過50個字元時無法儲存[!DNL Recommendations]活動的問題。 (TGT-52619)
* 修正客戶在新UI中修改條件後無法儲存Recommendations活動的問題。 該問題似乎與許可權相關，並不會影響所有具有類似角色的使用者。 (TGT-52816)
* 修正具有[!UICONTROL Editor]角色的使用者無法編輯[!DNL Recommendations]活動的問題。 嘗試變更設計並儲存活動導致403禁止錯誤，指出「[編輯者]」許可權是必要的，即使使用者已在相關工作區中擁有該角色。 (TGT-52836)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

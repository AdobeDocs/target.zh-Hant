---
keywords: 發行說明；發行；更新；未來發行；增強功能；新功能；修正；更新；發行前；搶先使用
description: 了解  [!DNL Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: fda279c909e2bb35e919d1bb4f4b611401a367cf
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 17%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2025年8月29日**

>[!NOTE]
>
>* 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。本文章中的資訊會經常更新，尤其是在發行版本之前。
>
>* 若要檢視目前版本的相關資訊，請參閱[Target發行說明](release-notes.md)。
>
>* 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 25.8.4 （2025年9月1日）

此版本包含下列更新和修正：

**[!UICONTROL Activities]**

+++檢視詳細資料
* **客戶無法從「[!UICONTROL Activity Overview]**」複製活動或檔名稱：以前，客戶無法直接從「[!UICONTROL Activity Overview]」在更新的活動建立程式中複製活動名稱或相關的優惠方案/檔案。 此限制會影響可用性，尤其是在較小的熒幕上。 客戶現在可以輕鬆複製活動和檔名稱，無需因應措施。 (TGT-51850)
* **在活動建立期間主動擷取已監管的[!DNL Target]客戶資料**：啟用主動收集[!DNL Target]客戶的報告、內容和熒幕擷取畫面，以改善活動建立流程。 此增強功能解決現有使用案例中發現的資料差距，並幫助確保在活動和實驗設定期間獲得更準確的見解。 (TGT-52415)
* **AP活動未擷取[!UICONTROL Reports]區段中**&#x200B;的模型就緒資料：檢視[!UICONTROL Reports]區段中Automated Personalization (AP)活動的客戶無法在報表群組和選件層級看到模型就緒指標。 發生此問題是因為無法從後端正確擷取模型就緒的資料。 功能已還原，且模型就緒的資料現在如預期般顯示。 (TGT-53600 和 TGT-53601)

+++

**[!UICONTROL Recommendations]**

+++檢視詳細資料
* **在[!UICONTROL View Collection]對話方塊中看不到產品清單：**&#x200B;之前，客戶在[!UICONTROL Recommendations]索引標籤中檢視集合時無法看到產品清單。 [!UICONTROL View Collection]對話方塊現在可以正確顯示關聯產品，提高更新後Recommendations UI的透明度和可用性。 (TGT-50531)
* **已修正[!UICONTROL Product Catalog Search]進階搜尋中區分大小寫篩選的問題**： [!UICONTROL Product Catalog Search]頁面中的進階搜尋篩選現在會正確忽略區分大小寫功能，並符合後端和GraphQL服務的行為。 此更新可確保為客戶提供一致且準確的建議結果，無論文字大小寫為何。 (TGT-53585)
* **在更新的[!UICONTROL Product Catalog Search] UI中的進階搜尋未提供建議**：在更新的[!UICONTROL Product Catalog Search] UI中使用進階搜尋功能的客戶必須輸入正確拼字的值，因為沒有顯示任何建議。 這使得難以有效地找到產品。 現在，建議會在進階搜尋輸入期間如預期般顯示。 (TGT-52008)

+++

**[!UICONTROL Reports]**

+++檢視詳細資料
* **由於無效的對象名稱錯誤，無法為案頭對象載入報告**：客戶嘗試在活動建立程式中檢視一個對象的報告時遇到GraphQL錯誤。 系統傳回「無效的對象名稱： XXXXX」訊息，導致無法存取報表資料。 現在，案頭對象的報表可正確載入。 (TGT-53371)
* **在「報表」頁面上切換對象時，導致Target UI發生錯誤**：客戶在更新的Target UI的Reports區段中選取某些對象時遇到錯誤。 此問題是因為後端GraphQL呼叫中的對象處理無效，導致未預期的錯誤和遺失資料所導致。 問題已解決，現在即使沒有可用資料，案頭受眾仍會載入且不會發生錯誤。 (TGT-53370)
+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++檢視詳細資料
* **使用[!UICONTROL Enhanced Experience Composer] (EEC)按一下「接受Cookie」失敗，因為遺失函式**：客戶回報嘗試透過EEC接受Cookie導致主控台錯誤： `handleclickAcceptAllButton is not defined`。 Cookie接受功能現在可如預期運作，確保在更新UI中建立活動期間提供更順暢的體驗。 (TGT-52794)
* **新的EEC UI無法載入舊版UI先前支援的某些頁面**：客戶報告新的EEC無法載入某些頁面，這些頁面可在舊版UI中存取，儘管網站上有防iframe的程式碼。 更新的活動建立流程現在支援載入這些頁面，以恢復活動建立工作流程的相容性。 (TGT-53061)
* **編輯體驗時，VEC顯示空白的白色畫面**：來自特定租使用者的客戶回報，嘗試在更新的VEC中編輯體驗時，VEC畫面變成空白。 此問題會影響新建立和舊的活動，阻礙工作流程的連續性。 VEC現在會正確載入，讓客戶能在不中斷的情況下編輯體驗。 (TGT-53547)
* **載入特定活動時，VEC當機並顯示空白熒幕**：來自特定租使用者的客戶報告VEC無法載入特定活動。 體驗編輯器在當機並顯示空白畫面之前，停留在「套用初始修改」上。 主控台錯誤指出無法讀取未定義的屬性。 編輯器現在會在更新的VEC中載入受影響的活動，而不會發生錯誤。 (TGT-53548)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

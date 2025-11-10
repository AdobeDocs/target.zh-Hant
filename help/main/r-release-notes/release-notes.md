---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5c1dda629a33fc38f51e2e3198a7ea091a369897
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 19%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 您需要瞭解的時間性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

針對與[!DNL Adobe Target]和您的實作相關的時效性更新，[!DNL Adobe]會透過[!UICONTROL Experience League]提供詳細的發行說明和檔案。 以下是和您的實作相關的一些重點專案：

### [!DNL Target] UI版本切換為棄用

如需詳細資訊，請參閱[[!DNL Target] UI更新常見問題](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 25.11.1 （2025年11月10日）


**目標分析 (A4T)**

+++檢視詳細資料
* 在更新的UI中使用&#x200B;**[!UICONTROL Goals & Settings]作為報告來源時出現[!DNL Adobe Analytics]錯誤訊息。**&#x200B;已解決更新[!UICONTROL Overview] UI中，目標區段顯示「發生錯誤」錯誤的問題。 我們無法完成您的要求。 當選取[!DNL Adobe Client Care] (A4T)作為報表來源時，如果問題仍然存在，請聯絡[!DNL Adobe Analytics]。 目標現在可正確顯示為[!UICONTROL Adobe Analytics]量度，以確保跨報告來源的一致可見性。 (TGT-54021)

+++

**客群**

+++檢視詳細資料
* **無法在更新的UI中選取多個報表對象。**&#x200B;解決更新UI中，使用者在編輯活動時無法同時選取多個新建立之報表對象的問題。 現在可以同時指派多個對象，提高報告設定的彈性和效率。 (TGT-53253)

+++

**決策優惠方案**

+++檢視詳細資料
* **無法在更新的UI中編輯或取代決策選件。**&#x200B;解決在更新的UI中，無法透過[!UICONTROL Modifications]面板編輯或取代決策優惠方案，且優惠方案名稱顯示為空白的問題。 決策優惠現在可完全存取及編輯，恢復與舊版UI的同等功能，並確保客戶可直接在活動中管理優惠。 (TGT-53884)

+++

**本地化**

+++檢視詳細資料
* **已修正韓文和日文UI中的數個本地化錯誤。** (TGT-54003、TGT-54004、TGT-54006、TGT-54007和TGT-54018)

+++

**[!UICONTROL Recommendations]**

+++檢視詳細資料
* **具有實體屬性比對的屬性促銷，無法在活動儲存後載入建議索引鍵。**&#x200B;修正規則型別為[!UICONTROL Promotion by Attribute]且型別為[!UICONTROL Entity Attribute Matching]的促銷活動在儲存活動後編輯時未載入建議金鑰的問題。 此問題是因為未透過GraphQL要求`customKeyId`所造成。 現在，建議索引鍵會在升級編輯期間正確載入。 (TGT-53117)
* 從ExpB切換到ExpA時，**建議會持續以視覺化方式顯示。**&#x200B;解決在體驗B中插入建議，然後切換至體驗A，讓建議選件方塊保持可見的問題。 這僅是視覺上的不一致；現在當在體驗之間切換時，修改會正確呈現，以確保準確的UI行為。 (TGT-53911)
* **建議金鑰未載入[!UICONTROL Promotion by Attribute]且符合[!UICONTROL Entity Attribute]。**&#x200B;解決規則型別為[!UICONTROL Promotion by Attribute]且型別為[!UICONTROL Entity Attribute Matching]的促銷活動在儲存活動後編輯時未載入建議金鑰的問題。 現在，可透過GraphQL正確擷取建議金鑰，確保促銷活動如預期般顯示及運作。 (TGT-53917)
* **針對隱藏的HTML元素編輯建議，無法在更新的UI中運作。**&#x200B;解決[!UICONTROL New Create]和VEC UI中，無法編輯套用至隱藏HTML元素的建議活動的問題。 此功能現在可如預期運作，恢復與舊版UI的同等性，並確保不論元素可見度為何，建議均可修改。 (TGT-53953)
* **無法在更新的UI中編輯隱藏HTML元素的建議活動。**&#x200B;已解決更新UI中無法編輯套用至隱藏HTML元素的建議活動的問題。 此功能現在可如預期運作，恢復與舊版UI的同等性，並確保不論元素可見度為何，建議均可修改。 (TGT-53951)
* **建議目錄在更新的UI中間歇性地遺失屬性值。**&#x200B;已解決在更新的[!UICONTROL Recommendations] UI中，目錄搜尋清單間歇性地無法顯示某些屬性值（例如訊息），即使出現在產品摘要中亦然。 屬性值現在會在搜尋結果中持續載入，而不需要重新設定欄，進而改善目錄管理的可靠性和效率。 (TGT-52769)
* 更新的UI中缺少&#x200B;**[!UICONTROL Download Recommendations]活動的[!DNL Recommendations]按鈕。**&#x200B;已解決在更新的[!DNL Recommendations] UI中，使用建議的A/B活動看不到[!UICONTROL Download Recommendations]按鈕的問題。 按鈕現在會正確顯示，可讓使用者如預期匯出建議資料，與舊版UI中的功能一致。 (TGT-53768)
* 更新後的總覽UI中缺少&#x200B;**[!UICONTROL Download Recommendation Data]按鈕。**&#x200B;已解決更新的[!UICONTROL Overview] UI中，包含建議的活動看不到[!UICONTROL Download Recommendation Data]按鈕的問題。 按鈕現在會正確顯示，確保使用者可直接匯出建議資料，而無需切換回舊版UI。 (TGT-53772)
* **編輯活動條件有時會在更新的UI中導致空白熒幕。**&#x200B;已解決更新版UI中按一下「[!UICONTROL Edit Criteria in Experiences]」有時會導致某些活動出現空白畫面的問題。 條件編輯器現在會在所有活動中以可靠的方式載入，確保使用者可以編輯而不會中斷。 (TGT-53961)
* **無法在更新的UI中編輯序列條件。**&#x200B;解決更新版UI中，嘗試編輯[!UICONTROL Sequence Criteria]導致條件快顯視窗在載入時卡住，然後顯示空白畫面的問題。 條件編輯器現在會正確載入，讓使用者可以編輯和更新順序條件而不會中斷。 (TGT-53985)

+++

**[!UICONTROL Reports]**

+++檢視詳細資料
* **[!UICONTROL Multivariate Test] (MVT)位置和圖表報告問題阻止產生報告。**&#x200B;解決MVT活動無法在Target UI中產生[!UICONTROL Location Contribution]和圖表報表的問題，顯示「發生錯誤」錯誤。 我們無法完成您的要求。」 現在，報表可在UI中正確載入，確保完整可見性。 (TGT-53654)
* **MVT報告因為[!UICONTROL Element]貢獻報告錯誤而未載入。**&#x200B;修正Target UI中無法載入MVT活動報表，並顯示「無法擷取元素貢獻報表」錯誤的問題。 現在，報表可正確顯示，以確保元素貢獻的完整可見性。 (TGT-53691)
* **匯出訂單詳細資料至[!UICONTROL Experience Targeting] (XT)活動的CSV問題。**&#x200B;修正XT活動中[!UICONTROL Export Order Details to CSV]選項未正確顯示並傳回空白檔案的問題。 現在僅針對AP活動顯示選項，以確保精確的匯出功能並防止混淆。 (TGT-53798)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++檢視詳細資料
* **[!UICONTROL Delete Modification]按鈕問題無法移除活動修改。**&#x200B;解決[!UICONTROL Delete Modification] UI中的[!DNL Target]按鈕無法運作，導致使用者無法移除活動內的修改的問題。 按鈕現在可如預期運作，允許可靠刪除修改，而不會延遲。 (TGT-53728)
* 更新的UI無法辨識&#x200B;**偏好的選取器。**&#x200B;已解決更新UI中偏好選取器（例如`data-target-component-id`）未出現在VEC內的CSS選取器清單中的問題。 使用者現在可以可靠地選取偏好的屬性，而不是動態產生的類別名稱，以確保在SPA頁面更新中穩定鎖定目標。 (TGT-53908)
* **[!UICONTROL Edit]和[!UICONTROL Overview]頁之間的活動位置對齊方式不符。**&#x200B;解決[!UICONTROL Overview]頁面中的活動位置編號與[!UICONTROL &#x200B; Edit Experience]頁面中的更新不一致的問題。 現在，兩個檢視中的位置會保持一致，以確保精確的對齊並防止位置遺失或編號錯誤。 (TGT-53960 和 TGT-53954)
* **無法在更新的VEC中切換回[!UICONTROL Design]模式。**&#x200B;解決更新的VEC UI中，使用者在[!UICONTROL Design]模式中導覽至新頁面後，無法切換回[!UICONTROL Browse]模式的問題。 [!UICONTROL Design]切換功能現在可以正常運作，讓修改可以順暢地套用至各頁面。 (TGT-53988 和 TGT-53993)
* **查詢引數未顯示在活動概觀中。**&#x200B;已解決更新後UI中，查詢引數未顯示在活動的[!UICONTROL Overview]頁面中，而導致[!UICONTROL Overview]和頁面傳送URL不一致的問題。 現在，查詢引數可正確顯示，以確保活動位置可完全呈現，且在檢視間保持一致。 (TGT-53701)

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

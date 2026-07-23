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
source-git-commit: c74d8b09fba181fcded2f982d99a03f1e7f3a07a
workflow-type: tm+mt
source-wordcount: 927
ht-degree: 29%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 26.7.4 （2026年7月23日）

**報告**

+++檢視詳細資料

* **轉換率圖表不適用於特定行動對象。** 修正未針對特定行動對象呈現[!UICONTROL 轉換率]圖表的問題。 (TGT-55611)

* 從下拉式清單中選取時，**「已檢視mbox」轉換目標無法運作。** 修正從[!UICONTROL 目標與設定]中下拉式清單中為「已檢視mbox」轉換目標選取mbox時，無法正確儲存mbox名稱，導致無法記錄轉換的問題。 (TGT-55588)

+++

**客群**

+++檢視詳細資料

* **對象庫頁面上的版面配置問題。** 修正當側面導覽摺疊時，[!UICONTROL 對象庫]頁面上啟用篩選器時發生的配置問題。 (TGT-55502)

+++

**[!UICONTROL 視覺化體驗撰寫器] (VEC)**

+++檢視詳細資料

* **行動版本未正確載入。** 修正[!UICONTROL 視覺化體驗撰寫器]無法提供重新整理方法，導致行動檢視無法正確載入的問題。 (TGT-54408)

* **編輯或刪除修改動作無法運作。** 修正無法從[!UICONTROL 編輯體驗]檢視中編輯或刪除修改的問題。 (TGT-55250)

* **活動載入後，瀏覽模式無回應。** 修正[!UICONTROL 瀏覽]模式對包含修改的體驗無回應而無法進一步導覽和編寫的問題。 (TGT-55306)

* **無法選取Salesforce LWC （陰影DOM）內的元素。** 修正[!UICONTROL 視覺化體驗撰寫器]無法選取使用Shadow DOM巢狀內嵌Salesforce Lightning Web Components的元素的問題，進而導致「找不到選取器」錯誤。 (TGT-54956)

* **在[!UICONTROL 視覺化體驗撰寫器]中出現重複的選件。** 修正修改和選件在活動編寫UI中間歇性重複顯示的問題。 (TGT-55685)

+++

**管理**

+++檢視詳細資料

* **已將內容產生助理重新命名為[!UICONTROL 產生內容]。** 將「AI助理」內容產生功能重新命名為[!UICONTROL 產生跨[!DNL Target]個UI表面的內容]。 (TGT-55689)

+++

**推薦**

+++檢視詳細資料

* **使用設定檔屬性的熱門程度建議。** [!DNL Target]現在支援依訪客個人資料屬性（例如國家、偏好語言或會員層級）動態地分組熱門程度建議、檢視次數最多和最暢銷商品。 （錐度–7614）

* **建議集合在[!UICONTROL 集合]和活動設定之間不相符。** 修正從活動設定檢視時，[!UICONTROL Recommendations]集合與[!UICONTROL Recommendations] > [!UICONTROL 集合]檢視相比，傳回其他不合格實體的問題。 (TGT-55554)

+++

## [!DNL Target Standard/Premium] 26.7.2 （2026年7月16日）

**活動**

+++檢視詳細資料

* **[!UICONTROL 活動概覽]頁面上的目標資訊不正確。** 修正[!DNL Automated Personalization]活動的[!UICONTROL 活動概覽]頁面顯示其他目標而非最佳化目標的問題。 (TGT-55553)

* 以[!UICONTROL 瀏覽]模式瀏覽頁面時，**畫面無回應。** 修正在[!UICONTROL 瀏覽]模式中瀏覽頁面時，畫面無回應的問題。 (TGT-55565)

+++

**首頁**

+++檢視詳細資料

* [!UICONTROL 最佳執行者]和[!UICONTROL 儲存]的&#x200B;**UI變更。** 更新表現最佳者的UI並儲存體驗。 (TGT-54975)

+++

**客群**

+++檢視詳細資料

* 在[!UICONTROL 建立設定檔指令碼]對話方塊中&#x200B;**未當地語系化的字串。** 修正[!UICONTROL 建立設定檔指令碼]對話方塊中的字串未當地語系化的問題。 (TGT-51527)

+++

## [!DNL Target Standard/Premium] 26.7.1 （2026年7月9日）

**活動**

+++檢視詳細資料

* **在[!UICONTROL 活動]、[!UICONTROL 對象]和[!UICONTROL 選件]頁面間不一致的來源顯示。** 修正來源在[!UICONTROL 活動]、[!UICONTROL 對象]和[!UICONTROL 選件]頁面上顯示不一致的問題。 (TGT-55247)

* **透過UI編輯時活動來源變更。** 修正透過UI編輯活動變更原始活動來源的問題。 (TGT-55248)

+++

**客群**

+++檢視詳細資料

* **編輯對象時預設工作區不正確。** 修正編輯對象後，預設工作區不正確的問題。 (TGT-55510)

+++

**報告**

+++檢視詳細資料

* 5月報告的&#x200B;**CSV下載失敗。** 修正五月下載CSV報表失敗的問題。 (TGT-55524)

+++

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

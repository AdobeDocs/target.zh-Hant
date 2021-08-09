---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 資料庫。
landing-page-description: 了解 [!DNL Adobe Target]目前版本中包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些新功能？
feature: 發行說明
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2d11409e9bab2db5d12c5961c7336040b8544614
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 65%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也包含Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台變更的發行說明（若適用）。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>請遷移至新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 程式庫的最新版本，以避免您的網站出現任何潛在問題。如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## [!DNL Target Standard/Premium] 21.8.1（待定日期）

>[!NOTE]
>
>[!DNL Target Standard/Premium] 21.8.1版本已延遲。 21.8.1版不會在2021年8月4日發行，而是會在未來幾天發行。 詳細資訊（若有）。

此維護髮行包含許多後端增強功能，包括針對客戶的下列變更：

* 修正在[!UICONTROL 表單式體驗撰寫器]中建立之[!UICONTROL 自動個人化]活動的報表，會參照報表中已刪除的選件的問題。 此問題會導致顯示以下錯誤訊息：「擷取此報表的資料時遇到問題。 如果問題仍然存在，請聯絡Adobe客戶服務。」 (TGT-41028)

## [!DNL Target Delivery API] （2021年8月3日）

此版本包含下列增強功能：

* mbox參數限制已提高為100個參數。 先前的限制為50個參數。 (TNT-41717)
* `categoryId`的限制已增加為256個字元。 先前的限制為128個字元。
* 已將下列[!DNL Adobe Audience Manager](AAM)詳細資料新增至傳送API:

   * AAM UUID:用來唯一識別使用者的內部AAM ID。
   * dataPartnerId:資料合作夥伴的ID。
   * dataPartnerUserId:資料合作夥伴提供的使用者ID。

   先前的傳送API僅包含`dcsLocationHint`和`blob`。 (TNT-41644)

## at.js 2.6.0 (2021 年 7 月 27 日)

* 當 at.js 設定 `secureOnly` 設為 `true` 時，為 Cookie 新增安全屬性。
* 現在可以在使用 `triggerView()` 時使用回應 Token。
* 修正了與 `CONTENT_RENDERING_NO_OFFERS` 事件相關的問題。現在，只要沒有從 [!DNL Target] 傳回內容，就會正確觸發此事件。
* 使用 `prefetch` 請求時會正確傳回 [!DNL Anlytics for Target] (A4T) 點擊量度詳細資料。
* UUID 產生不再使用 `Math.random()`，但須依賴 `window.crypto`。
* `sessionId` Cookie 過期在每次網路呼叫時會正確延長。
* [!UICONTROL 單頁應用程式] (SPA) 檢視快取初始化現在可以正確處理並接受 `viewsEnable` 設定。

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | 有關每個版本Platform Web SDK中變更的詳細資訊。 |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 資料庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些發行說明中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 舊版發行說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版發行說明](/help/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 發行說明 | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。如需詳細資訊，請參閱「<br>Creative Cloud 發行說明[」。](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html??lang=zh-Hant) |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 發行說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |

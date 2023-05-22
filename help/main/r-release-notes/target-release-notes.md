---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解  [!DNL Adobe Target] 即將發行的版本所包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發行的  [!DNL Target]  版本將包含哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: f44514c0b5ab643dec35aa230e46b88428f9e42b
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 52%

---

# [!DNL Target] 發行說明 (搶鮮版)

本文包含即將發行的 [!DNL Adobe Target] 版本 (包括 SDK、API 和 JavaScript 程式庫) 的搶鮮版資訊。

**上次更新日期：2023 年 5 月 22 日**

>[!NOTE]
>
>發行日期、功能和其他資訊可能會有所變更，恕不另行通知。
>
>若要檢視目前版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target] Standard/Premium 23.5.1 (2023 年 5 月 23-25 日)

我們將根據以下排程分批發行此版本：

5月23日：歐洲、中東和非洲(EMEA)地區5月24日：5月25日：美洲地區

此版本包含以下新功能、增強功能和修正：

| 功能 | 詳細資料 |
|--- |--- |
| 與 [!DNL Target] 共用 Real-Time CDP 設定檔屬性 | Real-Time CDP 設定檔屬性可與 [!DNL Target] 共用，用於 HTML 選件和 JSON 選件。<P>如需詳細資訊，請參閱[與  [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes) 共用 Real-time CDP 設定檔屬性。 |

* 修復了一個問題，使某些客戶無法使用「大於」或「小於」運算子建立訪問者配置檔案的訪問者。 (TGT-45271)
* 對整個 [!DNL Target] UI 進行了各種本地化修正。
* 在各個位置更新目標UI以進行即將進行的UI刷新（更改在功能標誌後，直到發佈更新）。

## [!DNL Target] Standard/Premium 23.5.2 (2023 年 5 月 31 日)

此版本包含下列增強功能和修正：

* 已修復在生成配置檔案API授權令牌時導致顯示空白頁的問題。 (TGT-45387)
* 已修復阻止在 [!UICONTROL 建立設計] 框（影像名稱包含GB 18030字元）。 (TGT-44614)
* 已修復導致報告的問題 [!UICONTROL 自動個性化] 在分析期間凍結的活動。 (TGT-44820)
* 修復了導致某些客戶的預設工作區的目標UI中未顯示任何活動的問題。 (TGT-45286)
* 已更新「禁止重複項」標誌的行為。 如果排除的重複提供標誌是預設內容提供（對於API v3、v4），則更新其以允許重複提供標誌；如果選項引用預設內容提供且未定義模板，則允許重複選項。 (TNT-46617)
* 修復了將查詢參數添加到URL中導致無法在Visual Experience Composer(VEC)中載入頁面的問題。 (TGT-44873)
* 修復了在「文本/HTML」中錯誤轉義某些字元的問題。 (TGT-44600)

## [!DNL Target] 標準/高級版23.5.3（待定日期）

此版本包含下列增強功能：

| 功能 | 詳細資料 |
|--- |--- |
| [!UICONTROL QA模式] 為 [!UICONTROL Automated Personalization] 活動 | [!DNL Adobe Target] [!UICONTROL QA模式] 現在可供使用 [!UICONTROL Automated Personalization] 活動，替換 [!UICONTROL 預覽連結] 功能。<P>如需詳細資訊，請參閱[活動 QA](/help/main/c-activities/c-activity-qa/activity-qa.md). |

* 效能增強，可禁止重複功能（包括減少負載時間），同時 [管理排除](/help/main/c-activities/t-automated-personalization/managing-exclusions.md#concept_4EF78013F80E48EFA024AE0274C9F037) 在 [!UICONTROL Automated Personalization] 活動。

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 搶鮮版版本資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知，請註冊 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)

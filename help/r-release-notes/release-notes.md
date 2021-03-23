---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強；增強；修正；錯誤修正；更新
description: 了解 Adobe Target 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 資料庫。
title: 目前版本包含哪些新功能？
feature: '  版本說明 '
translation-type: tm+mt
source-git-commit: 9155c487ed078f8af493755a2b4f067eafc8ae68
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 36%

---


# Target 版本說明 (最新)

這些發行說明提供每個[!DNL Adobe Target Standard]和[!DNL Target Premium]版本的功能、增強功能和修正資訊。 此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 將不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## Recommendations饋送處理伺服器的IP位址變更（2021年3月16日）

[!DNL Target Recommendations]饋送處理伺服器IP位址已於2021年3月16日更新。 如需詳細資訊，請參閱Recommendations饋送處理伺服器](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md)所使用的[IP位址。

## Target Standard/Premium 21.2.1 (2021 年 3 月 9 日)

此維護髮行包含下列增強功能、修正和變更。

括號內的問題編號供 [!DNL Adobe] 內部使用。

* 增加允許的選件大小(TGT-38304):

   | 類型 | 上一個限制 | 新限制 |
   | --- | --- | --- |
   | HTML | 256KB | 1024KB |
   | Target UI的視覺化選件 | 64KB | 每個體驗1024 KB |
   | 透過API | 512KB | 1024KB |

* [!UICONTROL 現] 在每 [!UICONTROL 天都會製作Auto-Target] (AT)和 [!UICONTROL Automated Personalization] (AP)活動的個人化洞察報告。您可以選擇提供[!UICONTROL 自動化區段]或[!UICONTROL 重要屬性]的報表，以查看過去15、30和60天。 已移除45天和90天選項，讓其他回顧視窗設定每日執行。 (TGT-39472)
* 修正當客戶在活動的[!UICONTROL 目標與設定]頁面上按一下編輯相依性時，無法顯示目前相依性的問題。 (TGT-39340)
* 修正重新整理工作區的[!UICONTROL 對象庫]時的問題。 在重新整理之前，會顯示目前所選工作區的對象。 重新整理後，會顯示[!UICONTROL 預設工作區]及其觀眾。 目前的工作區及其觀眾現在會在重新整理後持續存在。 (TGT-38871)
* 修正複製[!UICONTROL Recommendations]活動，並稍後變更其准則順序編輯原始活動時的問題。 原始活動中標準序列的更改也錯誤地應用於複製的活動。 (TGT-39155)
* 修正造成[!UICONTROL Recommendations]排除顯示錯誤產品數的問題。 (TGT-39599)

## 其他發行說明和版本詳細資訊

| 資源 | 詳細資料 |
|--- |--- |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 資料庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的版本說明和 Experience Cloud 版本說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些版本注意事項中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版版本說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本說明](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 版本說明 | 檢視 Adobe Experience Cloud 解決方案的最新版本說明。<br>如需詳細資訊，請參閱 [Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)。 |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |

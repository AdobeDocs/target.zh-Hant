---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強；增強；修正；錯誤修正；更新
description: 了解 Adobe Target 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 資料庫。
title: 目前版本包含哪些新功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
translation-type: tm+mt
source-git-commit: dba3044c94502ea9e25b21a3034dc581de10f431
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 35%

---

# Target 版本說明 (最新)

這些發行說明提供每個[!DNL Adobe Target Standard]和[!DNL Target Premium]版本的功能、增強功能和修正資訊。 此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## Target Standard/Premium 21.4.1 (2021 年 4 月 19 日)

此版本包含下列新功能和增強功能。 括號內的問題編號供 [!DNL Adobe] 內部使用。

| 功能 | 詳細資料 |
| --- | --- |
| at.js<br>的裝置上決策支援（要宣佈的日期） | 裝置上決策可讓行銷人員和開發人員在幾乎零延遲的情況下，在使用者的瀏覽器上進行實驗和個人化。<br>如需詳細資訊，請 [參閱at.js的裝置上決策。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) |
| ![實體篩](/help/assets/premium.png) 選規則的PremiumList運算子 | [!DNL Target Recommendations] 支援實體篩選規則的全新清單型運算子。(TGT-39234)<br>新添加的運算子包括：<br><ul><li>包含在清單中</li><li>不包含在清單中</li><li>清單包含</li><li>清單中不包含項目</li><li>清單包含</li><li>清單中不包含</li></ul>如需詳細資訊，請參閱[使用動態和靜態包含規則](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators)中的「可用運算子」。 |

此版本包含下列修正。

* 修正將對象變更為「所有訪客」後，活動無法同步的問題。 (TGT-40259)
* 修正即使啟用「不允許複製」選項，在[!UICONTROL Automated Personalization]活動中的不同位置使用選件時，仍無法複製選件的問題。 (TGT-39567)
* 修正導致[!UICONTROL Administration] > [!UICONTROL Scene7組態]頁面無法正確載入的問題。 (TGT-39918)
* 修正屬性映射至錯誤工作區的問題。 (TGT-39869)
* 修正在建立建議排除時變更環境後，若請求失敗，則造成無限載入的問題。 (TGT-39948)

## at.js 2.5.0版（要宣佈的日期）

此版本的at.js包含下列增強功能和變更：

* [at.js的](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) 裝置上決策支援。
* [預覽](/help/c-activities/c-activity-qa/activity-qa.md) Automated Personalization活動的連結支援。

此版本也移除了對Microsoft Internet Explorer 10及更新版本的支援。

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

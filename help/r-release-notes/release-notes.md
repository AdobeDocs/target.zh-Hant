---
keywords: 發行說明;新功能;發行;更新;更新;發行;增強功能;增強功能;修正;錯誤修正;更新
description: 了解 [!DNL Adobe Target]目前版本中包含的新功能、增強功能和修正，包括SDK、API和JavaScript程式庫。
title: 目前發行的版本包含哪些新功能？
feature: 發行說明
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a63b123ed180a818de5338656781957931abd755
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 83%

---

# Target 發行說明 (最新)

這些發行說明提供每個 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增強功能和修正資訊。此外，也會隨附 Target API、SDK、JavaScript 程式庫 (at.js) 的發行說明，以及其他平台變更 (如適用)。

>[!IMPORTANT]
>
>**mbox.js 生命週期結束**：自 2021 年 3 月 31 日起，[!DNL Adobe Target] 不再支援 mbox.js 程式庫。 自 2021 年 3 月 31 日起，從 mbox.js 進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行 [!DNL Target] 活動的頁面。
>
>移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱「[總覽：為用戶端 Web 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)」。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## ![Adobe Experience Platform Web SDK](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] 版本2.6.0（2021年6月1日）

此版本的[!DNL Platform Web SDK]包含對以下內容的支援：

| 功能 | 詳細資料 |
| --- | --- |
| 透過[!UICONTROL Analytics for Target](A4T)重新導向支援 | 使用[A4T](/help/c-integrating-target-with-mac/a4t/a4t.md)時，Platform Web SDK現在支援[!DNL Target]重新導向。<br>如需詳細資訊，請參閱 [實 [!DNL Target] 作的Analytics](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 |

## at.js版本2.5.0（2021年5月13日）

此 at.js 版本包含下列增強功能和變更：

* [針對 at.js 的裝置上決策](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)支援。
* [預覽連結](/help/c-activities/c-activity-qa/activity-qa.md)對 Automated Personalization 活動的支援

此版本也移除了對Microsoft Internet Explorer 10、Internet Explorer 11和所有舊版的支援。 at.js 2.5.0及更新版本仍持續支援Microsoft Edge。

## Target Standard/Premium 21.4.1 (2021 年 4 月 19 日)

此版本包含下列新功能和增強功能。 括號內的問題編號供 [!DNL Adobe] 內部使用。

| 功能 | 詳細資料 |
| --- | --- |
| 針對 at.js 的裝置上決策支援<br>(日期有待宣佈) | 裝置上決策可讓行銷人員和開發人員以幾乎零延遲的方式，在使用者的瀏覽器上提供測試和個人化。<br>如需詳細資訊，請參閱「[針對 at.js 的裝置上決策](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)」。 |
| ![Premium](/help/assets/premium.png) 實體篩選規則適用的清單型運算子 | [!DNL Target Recommendations] 支援實體篩選規則適用的全新清單型運算子。 (TGT-39234)<br>最近新增的運算子包括：<br><ul><li>包含在清單中</li><li>不包含在清單中</li><li>清單中包含某個項目</li><li>清單中不包含某個項目</li><li>清單中包含所有項目</li><li>清單中不包含所有項目</li></ul>如需詳細資訊，請參閱「[使用動態和靜態包含規則](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators)」中的「可用運算子」。 |

此版本包含下列修正。

* 已修正將對象變更為[!UICONTROL 所有訪客]後導致活動無法同步的問題。 (TGT-40259)
* 已修正在 [!UICONTROL Automated Personalization] 活動中的不同位置使用選件時，導致無法複製選件的問題 (即便已啟用「[!UICONTROL 不允許複製]」選項)。 (TGT-39567)
* 已修正導致「[!UICONTROL 管理] > [!UICONTROL Scene7 設定]」頁面無法正確載入的問題。 (TGT-39918)
* 已修正導致屬性對應到不正確的工作區的問題。 (TGT-39869)
* 已修正在建立建議排除時，要求在變更環境後失敗的情況下造成無限載入的問題。 (TGT-39948)

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有關 [!DNL Adobe Target] at.js JavaScript 資料庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視本指南未包含在這些發行說明中的更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版發行說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版發行說明](/help/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 發行說明 | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。如需詳細資訊，請參閱「<br>Creative Cloud 發行說明[」。](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html??lang=zh-Hant) |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先產品更新 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 發行說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |

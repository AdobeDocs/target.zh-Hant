---
keywords: 發行說明；發行；更新；未來發行；增強；新功能；修正；更新；搶鮮版
description: 瞭解即將發行的Adobe Target版本（包括SDK、API和JavaScript程式庫）中包含的新功能、增強功能和修正。
title: 即將發行的版本包含哪些新功能？
feature: '  版本說明 '
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
translation-type: tm+mt
source-git-commit: 9b6123fd0f9d44e43bd8e6bae1ddd7ef8c00d2e3
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 20%

---

# Target 版本說明 (發行前)

本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**上次更新時間: 2021 年 4 月 16 月**

若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能會相同，視發佈時間而定。 括號內的問題編號供 [!DNL Adobe] 內部使用。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會正常失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>為避免網站出現任何潛在問題，請移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## Target Standard/Premium 21.4.1 (2021 年 4 月 19 日)

此版本包含下列新功能和增強功能。 括號內的問題編號供 [!DNL Adobe] 內部使用。

| 功能 | 詳細資料 |
| --- | --- |
| at.js的裝置上決策支援 | 裝置上決策可讓行銷人員和開發人員在幾乎零延遲的情況下，在使用者的瀏覽器上進行實驗和個人化。<br>如需詳細資訊，請 [參閱at.js的裝置上決策。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) |
| ![實體篩](/help/assets/premium.png) 選規則的PremiumList運算子 | [!DNL Target Recommendations] 支援實體篩選規則的全新清單型運算子。(TGT-39234)<br>新添加的運算子包括：<br><ul><li>包含在清單中</li><li>不包含在清單中</li><li>清單包含</li><li>清單中不包含項目</li><li>清單包含</li><li>清單中不包含</li></ul>如需詳細資訊，請參閱[使用動態和靜態包含規則](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators)中的「可用運算子」。 |

此版本包含下列修正。

* 修正將對象變更為「所有訪客」後，活動無法同步的問題。 (TGT-40259)
* 修正即使啟用「不允許複製」選項，在[!UICONTROL Automated Personalization]活動中的不同位置使用選件時，仍無法複製選件的問題。 (TGT-39567)
* 修正導致[!UICONTROL Administration] > [!UICONTROL Scene7組態]頁面無法正確載入的問題。 (TGT-39918)
* 修正屬性映射至錯誤工作區的問題。 (TGT-39869)
* 修正在建立建議排除時變更環境後，若請求失敗，則造成無限載入的問題。 (TGT-39948)

## at.js 2.5.0版（2021年4月19日）

此版本的at.js包含下列增強功能和變更：

* [at.js的](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) 裝置上決策支援。
* [預覽](/help/c-activities/c-activity-qa/activity-qa.md) Automated Personalization活動的連結支援

此版本也移除了對Microsoft Internet Explorer 10及更新版本的支援。

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

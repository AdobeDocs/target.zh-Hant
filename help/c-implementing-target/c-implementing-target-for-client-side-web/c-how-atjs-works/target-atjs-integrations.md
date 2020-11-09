---
keywords: at.js integration;supported integrations;unsupported integrations;third party integrations
description: 關於與 Target 的常見整合和其對 at.js 支援狀態的資訊。
title: at.js 整合
feature: client-side
topic: Standard
uuid: 19036a1d-941c-4d31-8c7b-f50c86996b1c
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 91%

---


# at.js 整合{#at-js-integrations}

關於與 [!DNL Target] 的常見整合及其對 at.js 支援狀態的資訊。

若您迫切需要此處不支援或未提到的整合，請聯絡您的客戶代表或顧問。

## 支援的整合 {#section_3B44A970D3FB42D1973701452C868B55}

| 整合 | 詳細資料 |
|--- |--- |
| 目標分析 (A4T) | 請參閱 [Adobe Analytics 做為 Adobe Target (A4T) 的報表來源](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)。 |
| 設定檔和對象 (P&amp;A) | 請參 [閱核心](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) 「服務使 *用指南」中的「觀眾」*。 |
| Experience Cloud ID 服務 | 請參閱 [Adobe Experience Cloud ID 服務文件](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 |
| Adobe Launch | Launch 為 Adobe 新一代的標籤管理平台，且為實作 Adobe Target 的推薦方法。Launch 可讓客戶透過簡單的方式部署及管理所有必要的分析、行銷及廣告標籤功能，以便支援相關客戶體驗。請參閱[使用 Adobe Launch 實作 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25)。 |
| 動態標籤管理 (DTM) | See the [Best Practices for Implementing Target Using Dynamic Tag Management guide](https://experienceleague.adobe.com/docs/dtm/implementing/overview.html).   重要須知: [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) 為實作 Target 和 at.js 資料庫最新的推薦方法。如需進行新的 Target 實作，請使用 Launch。下列指南適用於使用 DTM 實作的現有用戶端。使用 DTM 整合時，請考量下列事項: <ul><li>程式庫管理: 透過「自訂」主機選項使用 at.js。目前不支援「自動」管理。 </li></ul> |
| Adobe Experience Manager (AEM) 雲端服務 | AEM 雲端服務能讓您在 AEM 工作流程中，建立 A/B 測試和體驗鎖定目標活動。透過具有 FP-11577 (或更新版本) 的 Adobe Experience Manager 支援 at.js。如需詳細資訊，請參閱[與 Adobe Target 整合](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html)，並選取您的 AEM 版本。 |
| AEM 體驗片段 | Target 活動中之在 AEM 中建立的體驗片段，可讓您運用 AEM 的易用性和強大功能，結合 Target 中強大的自動化智慧 (AI) 和機器學習 (ML) 功能，以大規模測試並個人化體驗。AEM 將您的所有內容和資產集中在一個中央位置，以支援您的個人化策略。AEM 可讓您在一個位置中輕鬆地為桌上型電腦、平板電腦和行動裝置建立內容，不必撰寫程式碼。不需要為每個裝置建立頁面，AEM 會自動根據您的內容來調整每一次體驗。請參閱 [AEM 體驗片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8)。 |

## 不支援的整合 {#section_8EFCAED418DC42E0B07F95924819EAC2}

| 整合 | 詳細資料 |
|--- |--- |
| [!DNL Legacy Target to SiteCatalyst Integration] | 這是透過頁面呼叫將行銷活動和配方 id 傳送至 [!DNL SiteCatalyst] 的整合，讓您能夠在 [!DNL SiteCatalyst] UI 中執行報表。A4T 已取代此功能。 |
| [!DNL Legacy Target to SiteCatalyst Integration] | 這是提出 mobx 呼叫 `"SiteCatalyst: Event"` 和 `"SiteCatalyst: Purchase"` 的整合，讓您能夠根據 evars 和 props 來建立成功量度和使用者設定檔。A4T 和 P&amp;A 已取代此功能。 |
| [!DNL Legacy Audience Manager (AAM) to Target Integration] | 此整合可提出前端 API 呼叫來擷取 AAM 區段，然後在頁面上的每一個 mbox 呼叫上當作 mbox 參數傳送。 |

## 第三方整合 {#section_EE599839CCAD49DD97640E5EDAD9082E}

| 整合 | 詳細資料 |
|--- |--- |
| 其他標記管理員 | at.js 應該可以與非 Adobe 標記管理平台一起使用，但在使用其他廠商所開發的自訂整合功能時請小心。他們的整合可能依賴 at.js 中已不存在的內部 mbox.js 函式。 |
| 第三方資料提供者 (例如，Demandbase、Bluekai、天氣 API) | 可以使用 at.js [資料提供者](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)功能，與許多用於補充 Target 使用者設定檔的第三方資料提供者整合。。 |
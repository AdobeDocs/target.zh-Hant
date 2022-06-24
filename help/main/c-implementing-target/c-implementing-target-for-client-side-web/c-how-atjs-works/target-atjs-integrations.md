---
keywords: at.js 整合;支援的整合;不支援的整合;第三方整合
description: 請參見Adobe支援（且不支援）的整合 [!DNL Target] at.js，包括Analytics for [!DNL Target] (A4T)、Experience CloudID服務等。
title: 什麼整合在.js支援？
feature: at.js
role: Developer
exl-id: 148c744d-2a2b-40f8-964b-c51283ae7d1c
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 75%

---

# at.js 整合

關於與 [!DNL Target] 的常見整合及其對 at.js 支援狀態的資訊。

若您迫切需要此處不支援或未提到的整合，請聯絡您的客戶代表或顧問。

## 支援的整合 {#section_3B44A970D3FB42D1973701452C868B55}

| 整合 | 詳細資料 |
|--- |--- |
| 目標分析 (A4T) | 請參閱 [Adobe Analytics 做為 Adobe Target (A4T) 的報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)。 |
| 設定檔和對象 (P&amp;A) | 請參閱 [觀眾](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html??lang=zh-Hant) 的 *核心服務使用手冊*。 |
| Experience Cloud ID 服務 | 請參閱 [Adobe Experience Cloud ID 服務文件](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 |
| 中的標籤 [!DNL Adobe Experience Platform] | 中的標籤 [!DNL Adobe Experience Platform] 是來自的新一代標籤管理功能 [!DNL Adobe]。 標籤為客戶提供了部署和管理分析、營銷和廣告標籤的簡單方法，這些標籤是為相關客戶體驗提供動力所必需的。 請參閱 [實施 [!DNL Target] 使用 [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank}。 |
| Adobe Experience Manager (AEM) 雲端服務 | AEM 雲端服務能讓您在 AEM 工作流程中，建立 A/B 測試和體驗鎖定目標活動。透過具有 FP-11577 (或更新版本) 的 Adobe Experience Manager 支援 at.js。如需詳細資訊，請參閱[與 Adobe Target 整合](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html)，並選取您的 AEM 版本。 |
| AEM 體驗片段 | Target 活動中之在 AEM 中建立的體驗片段，可讓您運用 AEM 的易用性和強大功能，結合 Target 中強大的自動化智慧 (AI) 和機器學習 (ML) 功能，以大規模測試並個人化體驗。AEM 將您的所有內容和資產集中在一個中央位置，以支援您的個人化策略。AEM 可讓您在一個位置中輕鬆地為桌上型電腦、平板電腦和行動裝置建立內容，不必撰寫程式碼。不需要為每個裝置建立頁面，AEM 會自動根據您的內容來調整每一次體驗。請參閱 [AEM 體驗片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8)。 |

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
| 第三方資料提供者 (例如，Demandbase、Bluekai、天氣 API) | 許多用於補充Target用戶配置的第三方資料提供程式可以使用at.js進行整合 [資料提供程式](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}功能。 |

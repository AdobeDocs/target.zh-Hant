---
keywords: Adobe Experience PlatformWeb SDK;aep Web sdk;web sdk;sdk;adobe體驗雲；平台邊緣網路；adobe體驗平台邊緣網路；邊緣網路；aep邊緣網路
description: 瞭解如何使用Adobe Experience PlatformWeb SDK通過AEP邊緣網路與Adobe Experience Cloud的各種服務進行交互。
title: 如何使用Experience PlatformWeb SDK實現？
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: 636016be6e8a6adc8c4b7fb09af93bb89e28373a
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 5%

---

# Adobe Experience Platform Web SDK

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK)是客戶端JavaScript庫，允許客戶 [!DNL Adobe Experience Cloud] 與該Experience Cloud中的各項服務(包括 [!DNL Target]) [!UICONTROL Adobe Experience Platform邊緣網路]。 除JavaScript庫外，還 [!DNL Adobe Experience Platform] 擴展，幫助您配置Web SDK。

有關詳細資訊，請參閱 *Adobe Experience PlatformWeb SDK* 幫助：

* 有關全面資訊： [什麼是Adobe Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* 有關特定於 [!DNL Target]: [目標概述](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## 教程：利用平台Web SDK實現Adobe Experience Cloud

瞭解如何 [使用Adobe Experience PlatformWeb SDK實現Experience Cloud應用程式](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target=_blank}。 有關特定於目標的資訊，請參見 [使用平台Web SDK設定目標](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-target.html)教程中的{target=_blank}。

## 建議文件

除 [!DNL Platform Web SDK] 上述文檔，本指南中的主題還包含特定於 [!DNL Platform Web SDK] 因為 [!DNL Target] 功能。

| 功能 | 說明/連結 |
| --- | --- |
| [活動 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 在中使用QA URL [!DNL Adobe Target] 通過預覽連結執行輕鬆的端到端活動QA，這些連結永遠不會更改，可選的受眾目標，以及保留與即時活動資料分段的QA報告。 [!UICONTROL 活動QA] 讓您完全test [!DNL Target] 在啟動前進行活動。<br>請參閱 [目標JavaScript庫QA模式相容性](/help/c-activities/c-activity-qa/activity-qa.md#compatibility) 和 [預覽URL](/help/c-activities/c-activity-qa/activity-qa.md#preview)。 |
| [[!UICONTROL Analytics for Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T)是一種跨解決方案整合，允許您根據 [!DNL Analytics] 轉換指標和受眾段。 A4T整合允許您 [!DNL Analytics] 報告以檢查結果。<br>請參閱 [支援的活動類型](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 和 [Adobe Experience PlatformWeb SDK實施步驟](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform)。 |
| [對象](/help/c-target/target.md) | 觀眾 [!DNL Adobe Target] 確定誰在目標活動中看到內容和體驗。<br>請參閱 [使用「受眾」清單](/help/c-target/c-audiences/audiences.md#use-list) 和 [合併多個受眾](/help/c-target/combining-multiple-audiences.md)。 |
| [提供決策](/help/c-integrating-target-with-mac/ajo/offer-decision.md) | 將在Adobe Journey Optimizer建立的優惠決定添加到目標活動(手動A/BTest或體驗目標)中，以確定並提供下一個最佳優惠，供您在Web和移動設備上訪問。 |
| [重新導向選件 - A4T 常見問答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | 重定向功能使訪問者的瀏覽器重定向到新頁面。<br>請參閱 [是否 [!DNL Adobe Experience Platform Web SDK] 支援A4T重定向服務？](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [回應權杖](/help/administrating-target/response-tokens.md) | 響應令牌允許您將目標資料發送到Google Analytics和其他第三方整合。<br>請參閱 [通過平台Web SDK向Google Analytics發送資料](/help/administrating-target/response-tokens.md#platform-web-sdk) 查看如何完成此任務的代碼示例。 |
| [單頁應用程式實現](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/spa-implementation.html?lang=en) 的 *平台Web SDK概述* 的子菜單。 | [!UICONTROL Adobe Experience PlatformWeb SDK] 提供豐富的功能，使您的企業能夠在新一代客戶端技術（如單頁應用程式）上執行個性化SPA化。 |
| [TLS (傳輸層安全性) 加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | TLS（傳輸層安全性）可幫助您維護最高的安全標準並提升客戶資料的安全性。 |

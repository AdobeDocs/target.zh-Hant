---
keywords: Adobe Experience Platform Web SDK;aep web sdk; web sdk; sdk;adobe experience cloud；平台邊緣網路；adobe experience platform邊緣網路；邊緣網路；aep邊緣網路
description: 了解如何使用Adobe Experience Platform Web SDK透過AEP Edge Network與Adobe Experience Cloud中的各種服務互動。
title: 如何使用Experience PlatformWeb SDK實作？
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: 4c18eb0febccf1a93ef0e423c46eeb08f8817b43
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 6%

---

# Adobe Experience Platform Web SDK

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK)是用戶端JavaScript程式庫，可讓 [!DNL Adobe Experience Cloud] 與本Experience Cloud內各種服務互動(包括 [!DNL Target])透過 [!UICONTROL Adobe Experience Platform Edge Network]. 除了JavaScript程式庫，還有 [!DNL Adobe Experience Platform] 擴充功能，協助您進行Web SDK設定。

如需詳細資訊，請參閱 *Adobe Experience Platform Web SDK* 說明：

* 欲知全面資訊： [什麼是Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* 以取得 [!DNL Target]: [Target概述](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## 教學課程：使用Platform Web SDK實作Adobe Experience Cloud

了解如何 [使用Adobe Experience Platform Web SDK實作Experience Cloud應用程式](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target=_blank}。 如需Target的特定資訊，請參閱 [使用Platform Web SDK設定Target](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-target.html)教學課程中的{target=_blank}。

## 建議文件

除了 [!DNL Platform Web SDK] 上述檔案中，本指南中的主題也包含 [!DNL Platform Web SDK] 因為它與 [!DNL Target] 功能。

| 功能 | 說明/連結 |
| --- | --- |
| [活動 QA](/help/c-activities/c-activity-qa/activity-qa.md) | 在中使用QA URL [!DNL Adobe Target] 執行簡易的端對端活動QA，具有永不變更的預覽連結、可選對象鎖定目標，以及與即時活動資料保持分段的QA報表。 [!UICONTROL 活動QA] 可讓您完全測試 [!DNL Target] 活動之後，再啟動它們為「使用中」。<br>請參閱 [Target JavaScript程式庫QA模式相容性](/help/c-activities/c-activity-qa/activity-qa.md#compatibility) 和 [預覽URL](/help/c-activities/c-activity-qa/activity-qa.md#preview). |
| [[!UICONTROL Analytics for Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T)是跨解決方案的整合，可讓您根據 [!DNL Analytics] 轉換量度和受眾區段。 A4T整合可讓您使用 [!DNL Analytics] 報告來檢查結果。<br>請參閱 [支援的活動類型](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 和 [Adobe Experience Platform Web SDK實作的實作步驟](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform). |
| [對象](/help/c-target/target.md) | 中的對象 [!DNL Adobe Target] 決定誰可以看到鎖定目標活動中的內容和體驗。<br>請參閱 [使用對象清單](/help/c-target/c-audiences/audiences.md#use-list) 和 [合併多個對象](/help/c-target/combining-multiple-audiences.md). |
| [重新導向選件 - A4T 常見問答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | 重新導向選件會導致訪客的瀏覽器重新導向至新頁面。<br>請參閱 [是否 [!DNL Adobe Experience Platform Web SDK] 是否支援A4T的重新導向選件？](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [回應權杖](/help/administrating-target/response-tokens.md) | 回應Token可讓您將Target資料傳送至Google Analytics和其他第三方整合。<br>請參閱 [透過Platform Web SDK傳送資料至Google Analytics](/help/administrating-target/response-tokens.md#platform-web-sdk) 以查看如何完成此任務的程式碼範例。 |
| [實作單頁應用程式](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/spa-implementation.html?lang=en) 在 *平台Web SDK概述* 指南。 | [!UICONTROL Adobe Experience Platform Web SDK] 提供豐富的功能，讓貴公司能以新世代用戶端技術(例如單頁應用程式(SPA))為基礎進行個人化。 |
| [TLS (傳輸層安全性) 加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | TLS（傳輸層安全性）可協助您維持最高的安全標準，並提升客戶資料的安全性。 |

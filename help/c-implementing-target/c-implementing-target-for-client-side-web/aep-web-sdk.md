---
keywords: Adobe Experience Platform Web SDK;aep web sdk; web sdk; sdk;adobe experience cloud；平台邊緣網路；adobe experience platform邊緣網路；邊緣網路；aep邊緣網路
description: 了解如何使用Adobe Experience Platform Web SDK透過AEP Edge Network與Adobe Experience Cloud中的各種服務互動。
title: 如何使用Experience PlatformWeb SDK實作？
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: 0cfab8d09b74b3eb0ead33a0c37f9dab68a88305
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 7%

---

# Adobe Experience Platform Web SDK

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK)是用戶端JavaScript程式庫，可讓 [!DNL Adobe Experience Cloud] 的客戶透過Adobe Experience Platform邊緣網路( [!DNL Target]包括 [!UICONTROL )與Experience Cloud中的各種服務互動]。除了JavaScript程式庫，還提供[!DNL Experience Platform Launch]擴充功能，以協助您進行Web SDK設定。

如需詳細資訊，請參閱&#x200B;*Adobe Experience Platform Web SDK*&#x200B;說明中的下列連結：

* 欲知全面資訊：[什麼是Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* 有關[!DNL Target]的特定資訊：[Target概述](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## 本指南中的建議檔案

除了上述[!DNL Platform Web SKD]檔案，本指南中的主題也包含與[!DNL Platform Web SDK]功能相關的特定資訊。[!DNL Target]

| 功能 | 說明/連結 |
| --- | --- |
| [活動問答](/help/c-activities/c-activity-qa/activity-qa.md) | 在[!DNL Adobe Target]中使用QA URL，來執行簡易的端對端活動QA，同時具有永不變更的預覽連結、可選對象鎖定目標，以及與即時活動資料保持分段的QA報表。 [!UICONTROL 活動] QA可讓您在將活動上線啟動 [!DNL Target] 之前，完全測試活動。<br>請參 [閱Target JavaScript程式庫QA模式](/help/c-activities/c-activity-qa/activity-qa.md#compatibility) 相容 [性和預覽URL](/help/c-activities/c-activity-qa/activity-qa.md#preview)。 |
| [Analytics for Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T)是跨解決方案的整合，可讓您根據轉換量度和受 [!DNL Analytics] 眾區段建立活動。A4T整合可讓您使用[!DNL Analytics]報表來檢查結果。<br>請參 [閱Adobe Experience Platform](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)  Web  [SDK實作的支援活動類型和實作步驟](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform)。 |
| [對象](/help/c-target/target.md) | [!DNL Adobe Target]中的對象會決定誰可以看到鎖定目標活動中的內容和體驗。<br>請參 [閱使用對象](/help/c-target/c-audiences/audiences.md#use-list) 清單 [合併多個對象](/help/c-target/combining-multiple-audiences.md)。 |
| [重新導向選件 - A4T 常見問答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | 重新導向選件會導致訪客的瀏覽器重新導向至新頁面。<br>請參 [閱支 [!DNL Adobe Experience Platform Web SDK] 援A4T的重新導向選件嗎？](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [回應權杖](/help/administrating-target/response-tokens.md) | 回應Token可讓您將Target資料傳送至Google Analytics和其他第三方整合。<br>請參 [閱透過Platform Web SDK傳送資料至Google Analytics](/help/administrating-target/response-tokens.md#platform-web-sdk) ，以了解如何完成此工作的程式碼範例。 |
| [TLS (傳輸層安全性) 加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | TLS（傳輸層安全性）可協助您維持最高的安全標準，並提升客戶資料的安全性。 |

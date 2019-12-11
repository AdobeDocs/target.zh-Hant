---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: Adobe Target 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。
title: 預先擷取選件內容
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: 4f877bf6a0bd73e2d29c2d41ab64dc2a39c61a31

---


# 預先擷取選件內容{#prefetch-offer-content}

[!DNL Target] 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。

此程序會減少載入時間，避免多個網路呼叫，並允許通知 [!DNL Target] 行動應用程式使用者造訪哪一個 mbox。預先擷取呼叫期間，會擷取並快取所有內容，而且會從快取中擷取此內容，以供包含指定 mbox 名稱之快取內容的所有未來呼叫使用。

在iOS和Android Mobile SDK中使用預回遷方法時，請考慮下列限制：

* 預先擷取內容不會在跨啟動之間持續有效。只要應用程式仍然存在，或直到呼叫 `clearPrefetchCache()` 方法為止，則會快取預先擷取內容。
* 自動個人化或 [!UICONTROL Recommendations分配活動類型、或在A/B或XT活動中支援Commendations活動，支援Auto-Personalization] 和Auto-Recommendations流量分配方法、Automated Personalization或 [](/help/c-recommendations/recommendations-as-an-offer.md)Recommendations活動或Commendations活動，預取功能不支援。

如需詳細資訊，包括預先提取方法、公用類別和程式碼範例，請參閱:

* **** iOS: 「 [Mobile Services iOS SDK說明」中](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html)*的iOS內容預回遷*。
* **** Android: 在 [Mobile Services Android SDK說明中](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) ，預 *回遷Android選件內容*。

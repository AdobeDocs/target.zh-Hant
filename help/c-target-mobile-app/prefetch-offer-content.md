---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: Adobe Target 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。
title: 預先擷取選件內容
feature: mobile implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 63%

---


# 預先擷取選件內容{#prefetch-offer-content}

[!DNL Target] 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。

此程序會減少載入時間，避免多個網路呼叫，並允許通知 [!DNL Target] 行動應用程式使用者造訪哪一個 mbox。預先擷取呼叫期間，會擷取並快取所有內容，而且會從快取中擷取此內容，以供包含指定 mbox 名稱之快取內容的所有未來呼叫使用。

在iOS和Android Mobile SDK中使用預回遷方法時，請考慮下列限制：

* 預先擷取內容不會在跨啟動之間持續有效。只要應用程式仍然存在，或直到呼叫 `clearPrefetchCache()` 方法為止，則會快取預先擷取內容。
* 自動個人化或 [!UICONTROL Recommendations分配活動類型、或在A/B或XT活動中支援Commendations活動，支援Auto-Personalization] 和Auto-Recommendations流量分配方法、Automated Personalization或 [](/help/c-recommendations/recommendations-as-an-offer.md)Recommendations活動或Commendations活動，都不支援預回遷功能。

如需詳細資訊，包括預先提取方法、公用類別和程式碼範例，請參閱:

* **iOS:** [預回遷iOS中的選件內容](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) ，請參閱 *Mobile Services iOS SDK說明*。
* **Android:** [在Mobile](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) Services Android SDK說明 *中預回遷選件內容*。

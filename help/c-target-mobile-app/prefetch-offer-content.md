---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: 使用iOS和Android Mobile SDK中的Adobe Target預回遷功能，透過快取伺服器回應，盡可能少地擷取選件內容。
title: 我可以預先擷取行動應用程式的選件內容嗎？
feature: Implement Mobile
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 47%

---


# 預先擷取選件內容{#prefetch-offer-content}

[!DNL Target] 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。

此程序會減少載入時間，避免多個網路呼叫，並允許通知 [!DNL Target] 行動應用程式使用者造訪哪一個 mbox。預先擷取呼叫期間，會擷取並快取所有內容，而且會從快取中擷取此內容，以供包含指定 mbox 名稱之快取內容的所有未來呼叫使用。

在iOS和Android Mobile SDK中使用預回遷方法時，請考慮下列限制：

* 預先擷取內容不會在跨啟動之間持續有效。只要應用程式仍然存在，或直到呼叫 `clearPrefetchCache()` 方法為止，則會快取預先擷取內容。
* [!UICONTROL 自動分配]和[!UICONTROL 自動目標]流量分配方法、[!UICONTROL 自動個人化]或[!UICONTROL 建議]活動類型或A/B或XT活動](/help/c-recommendations/recommendations-as-an-offer.md)中的建議不支援預回遷功能。[

如需詳細資訊，包括預先提取方法、公用類別和程式碼範例，請參閱:

* **iOS：在**  [Mobile Services iOS SDK說明](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) 的iOS *中預回遷選件內容*。
* **Android：在**  [Mobile Services Android SDK說明](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) 的 *Android中預回遷選件內容*。

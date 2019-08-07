---
description: Adobe Target 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。
keywords: 選件;預先提取;iOS;android；sdk；行動；mobile sdk
seo-description: Adobe Target 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。
seo-title: 預先擷取選件內容
solution: Target
title: 預先擷取選件內容
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: 95bf4b2070cc2de235ac09ac164f0f9ec48dd6cd

---


# 預先擷取選件內容{#prefetch-offer-content}

[!DNL Target] 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。

此程序會減少載入時間，避免多個網路呼叫，並允許通知 [!DNL Target] 行動應用程式使用者造訪哪一個 mbox。所有內容都會在預先擷取呼叫期間擷取並快取，而且在未來所有呼叫中都會擷取此內容，以便針對指定的mbox名稱包含快取內容。

使用iOS和Android Mobile SDK中的預先擷取方法時，請考慮下列事項：

* 預先擷取內容不會在跨啟動之間持續有效。只要應用程式仍然存在，或直到呼叫 `clearPrefetchCache()` 方法為止，則會快取預先擷取內容。
* 「自動目標」、「自動分配」和「自動個人化」活動類型不支援iOS和Android Mobile SDK中的預先擷取功能。

如需詳細資訊，包括預先提取方法、公用類別和程式碼範例，請參閱:

* **iOS:**[適用於 Experience Cloud 解決方案的 iOS SDK 4.x](https://marketing.adobe.com/resources/help/en_US/mobile/ios/c_mob_target-prefetch_ios.html) 指南中的&#x200B;*在 iOS 中預先提取選件內容*。
* **Android:**[適用於 Experience Cloud 解決方案的 Android SDK 4.x](https://marketing.adobe.com/resources/help/en_US/mobile/android/c_mob_target-prefetch_android.html) 指南中的&#x200B;*在 Android 中預先提取選件內容*。

---
description: Adobe Target 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。
keywords: 選件;預先提取;iOS;android
seo-description: Adobe Target 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。
seo-title: 預先擷取選件內容
solution: Target
title: 預先擷取選件內容
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 預先擷取選件內容{#prefetch-offer-content}

[!DNL Adobe Target] 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。

此程序會減少載入時間，避免多個網路呼叫，並允許通知 [!DNL Target] 行動應用程式使用者造訪哪一個 mbox。預先擷取呼叫期間，會擷取並快取所有內容，而且將從快取中擷取此內容，以供包含指定 mbox 名稱之快取內容的所有未來呼叫使用。

預先擷取內容不會在跨啟動之間持續有效。只要應用程式仍然存在，或直到呼叫 `clearPrefetchCache()` 方法為止，則會快取預先擷取內容。

如需詳細資訊，包括預先提取方法、公用類別和程式碼範例，請參閱:

* **iOS:**「適用於 Experience Cloud 解決方案的 iOS SDK 4.x」指南中的 [iOS 中的預先擷取選件內容](https://marketing.adobe.com/resources/help/zh_TW/mobile/ios/c_mob_target-prefetch_ios.html)。
* **Android:** *適用於 Experience Cloud 解決方案的 Android SDK 4.x* 指南中的 [Android 中的預先擷取選件內容](https://marketing.adobe.com/resources/help/zh_TW/mobile/android/c_mob_target-prefetch_android.html)。
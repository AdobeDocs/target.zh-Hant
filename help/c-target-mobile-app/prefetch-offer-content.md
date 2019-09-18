---
description: Adobe Target 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。
keywords: 選件;預先提取;iOS;android;sdk;mobile;mobile；行動sdk
seo-description: Adobe Target 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。
seo-title: 預先擷取選件內容
solution: Target
title: 預先擷取選件內容
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: ce8a890d0d662c0eec4d7fe254da371694811822

---


# 預先擷取選件內容{#prefetch-offer-content}

[!DNL Target] 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。

此程序會減少載入時間，避免多個網路呼叫，並允許通知 [!DNL Target] 行動應用程式使用者造訪哪一個 mbox。在預回遷呼叫期間會擷取和快取所有內容，而此內容會從快取中擷取，以供日後所有呼叫使用，這些呼叫包含指定mbox名稱的快取內容。

在iOS和Android Mobile SDK中使用預回遷方法時，請考慮以下事項：

* 預先擷取內容不會在跨啟動之間持續有效。只要應用程式仍然存在，或直到呼叫 `clearPrefetchCache()` 方法為止，則會快取預先擷取內容。
* 「自動目標」、「自動分配」和「自動個人化」活動類型不支援iOs和Android行動SDK中的預回遷功能。

如需詳細資訊，包括預先提取方法、公用類別和程式碼範例，請參閱:

* **** iOS: 「 [Mobile Services iOS SDK說明」中](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html)*的iOS內容預回遷*。
* **** Android: 在 [Mobile Services Android SDK說明中](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) ，預 *回遷Android選件內容*。

---
keywords: 提供；預回遷；iOS;android;sdk;mobile sdk
description: 使用Adobe [!DNL Target] iOS和Android移動軟體開發工具包中的預取功能，通過快取伺服器響應來盡可能少地提供內容。
title: 我能否預回遷為移動應用提供內容？
feature: Implement Mobile
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
source-git-commit: e152d3d68eede9c7606e546e30bd3e65bb8bcb9a
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 54%

---

# 預先擷取選件內容

[!DNL Target] 預先擷取功能會使用 iOS 和 Android Mobile SDK，透過快取伺服器回應盡量以最少次數擷取選件。

此程序會減少載入時間，避免多個網路呼叫，並允許通知 [!DNL Target] 行動應用程式使用者造訪哪一個 mbox。預先擷取呼叫期間，會擷取並快取所有內容，而且會從快取中擷取此內容，以供包含指定 mbox 名稱之快取內容的所有未來呼叫使用。

在iOS和Android移動SDK中使用預取方法時，請考慮以下限制：

* 預先擷取內容不會在跨啟動之間持續有效。只要應用程式仍然存在，或直到呼叫 `clearPrefetchCache()` 方法為止，則會快取預先擷取內容。

如需詳細資訊，包括預先提取方法、公用類別和程式碼範例，請參閱:

* **iOS:**  [預回遷服務內容在iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) 的 *移動服務iOSSDK幫助*。
* **Android:**  [Android中的預回遷提供內容](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) 的 *移動服務Android SDK幫助*。

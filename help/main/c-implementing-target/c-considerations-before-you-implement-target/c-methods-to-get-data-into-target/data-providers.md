---
keywords: 實現；實現；設定；設定；資料提供程式
description: 將資料 [!DNL Target] 使用資料提供程式。
title: 如何將資料 [!DNL Target] 是否使用資料提供程式？
feature: Implementation
role: Developer
exl-id: 05fe9190-4d36-43e2-9fc7-c354a6821bfb
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 62%

---

# 資料提供者

資料提供程式是一種功能，使您能夠輕鬆地將資料從第三方傳遞到 [!DNL Adobe Target]。

注：資料提供程式需要at.js 1.3或更高版本。

## 格式

`window.targetGlobalSettings.dataProviders` 設定是資料提供者的陣列。

如需各資料提供者結構的詳細資訊，請參閱[資料提供者](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)一節。

## 示例使用案例

從第三方收集氣象服務、DMP 甚至您自己的網頁服務等資料。接著，您就能使用此資料來建立對象、鎖定內容及擴充訪客設定檔。

## 方法的益處

此設定可讓客戶收集來自第三方資料提供者 (例如 Demandbase、BlueKai 和自訂服務) 的資料，並在全域 mbox 要求中以 mbox 參數的形式傳遞資料至 Target。

它透過非同步和同步要求，以支援來自多個提供者的資料收集。

使用此方法可讓您方便管理預設頁面內容的忽隱忽現情形，同時對每個提供者包含獨立的逾時計算，以限制對頁面效能的影響

## 注意事項

如果資料提供程式已添加到 `window.targetGlobalSettings.dataProviders` 是非同步的，它們是並行執行的。 訪問者API請求與添加到 `window.targetGlobalSettings.dataProviders` 允許最短等待時間。

at.js不嘗試快取資料。 如果資料提供者擷取資料一次，則資料提供者應該確定已將該資料快取，並且當叫用該提供者函數時，可做為第二個叫用的快取資料。

## 代碼示例

[資料提供者](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)中提供許多範例。

## 相關資訊的連結

文件: [資料提供者](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)

## 培訓影片：

* [使用 Adobe Target 中的資料提供者](https://helpx.adobe.com/tw/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [實作 Adobe Target 中的資料提供者](https://helpx.adobe.com/tw/target/kt/using/dataProviders-atjs-technical-video-implement.html)

---
keywords: 實施；實施；設定；設定；資料提供器
description: 使用資料提供者將資料匯入Target。
title: 如何使用資料提供者將資料匯入Target?
feature: Implementation
role: Developer
exl-id: 05fe9190-4d36-43e2-9fc7-c354a6821bfb
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 66%

---

# 資料提供者

資料提供者是可讓您輕鬆將資料從第三方傳遞至[!DNL Adobe Target]的功能。

注意：資料提供者需要at.js 1.3或更新版本。

## 格式

`window.targetGlobalSettings.dataProviders` 設定是資料提供者的陣列。

如需各資料提供者結構的詳細資訊，請參閱[資料提供者](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)一節。

## 範例使用案例

從第三方收集氣象服務、DMP 甚至您自己的網頁服務等資料。接著，您就能使用此資料來建立對象、鎖定內容及擴充訪客設定檔。

## 方法的優點

此設定可讓客戶收集來自第三方資料提供者 (例如 Demandbase、BlueKai 和自訂服務) 的資料，並在全域 mbox 要求中以 mbox 參數的形式傳遞資料至 Target。

它透過非同步和同步要求，以支援來自多個提供者的資料收集。

使用此方法可讓您方便管理預設頁面內容的忽隱忽現情形，同時對每個提供者包含獨立的逾時計算，以限制對頁面效能的影響

## 注意事項

如果添加到`window.targetGlobalSettings.dataProviders`的資料提供器是非同步的，則並行執行它們。 訪客API要求會與新增至`window.targetGlobalSettings.dataProviders`的函式並行執行，以允許最短等待時間。

at.js不會嘗試快取資料。 如果資料提供者擷取資料一次，則資料提供者應該確定已將該資料快取，並且當叫用該提供者函數時，可做為第二個叫用的快取資料。

## 程式碼範例

[資料提供者](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)中提供許多範例。

## 相關資訊的連結

文件: [資料提供者](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

## 訓練影片:

* [使用 Adobe Target 中的資料提供者](https://helpx.adobe.com/tw/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [實作 Adobe Target 中的資料提供者](https://helpx.adobe.com/tw/target/kt/using/dataProviders-atjs-technical-video-implement.html)

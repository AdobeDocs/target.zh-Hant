---
keywords: 伺服器端；伺服器端；sdk;sdks;on device;decitioning;on device;ondevice；零延遲；latency;near-zero;node.js
description: 瞭解如何使用設備上決策來快取 [!DNL Target] 伺服器上的A/B和MVT活動，以在接近零的延遲時執行記憶體內決策。
title: 設備上決策是什麼？
feature: Implement Server-side
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: 3c64945eb1898457a9d6a3e7bbfa64420bf1250a
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 9%

---

# 裝置上決策

設備上決策提供快取 [!DNL Adobe Target] [!UICONTROL A/BTest] 和 [!UICONTROL 體驗目標] (XT)伺服器上的活動，在接近零的延遲下執行記憶體中的決定，而不阻止向 [!DNL Adobe Target] 邊緣網路。

有關詳細資訊，請參閱主題：

* [用於客戶端的設備上決策](https://developer.adobe.com/target/implement/client-side/){target=_blank}
* [用於伺服器端的設備上確定](https://developer.adobe.com/target/implement/server-side/sdk-guides/on-device-decisioning/){target=_blank}

## 網路研討會影片：利用 [!DNL Adobe Target] 的裝置上決策在零延遲的情況下進行個人化和測試

市場人員、產品擁有者和開發人員被要求在網站、應用程式，以及與客戶連結的任何地方最佳化整體客戶體驗，此情況更勝以往。具有資料小倉庫和複雜實施的多種工具是不夠的。

在本錄制的網路研討會中， [!DNL Adobe Target] 產品專家討論如何將關鍵體驗優化決策在設備上本地執行，而延遲接近零，從而開啟新的使用案例的大門，同時提高您客戶的站點效能。

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## 最佳做法

Adobe建議在使用設備上決策時採用以下最佳做法：

### 確定方法為「設備上」時的最佳做法 {#best-practices-on-device}

當使用「設備上」作為判斷方法時，當訪問者第一次載入網頁時下載該偽影。 需要在第一頁載入（無快取）時進行的任何活動限定只在完全下載項目後才發生。 您可以遵循某些最佳做法來確保新匿名訪問者的活動資格快速發生。

* 停用不應位於項目中的「設備上」活動。
* 如果 [!DNL Target Premium]，您可以使用 [屬性/工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 建立不同工作區的不同對象檔案。
* 如果項目檔案由於合法原因變得非常大，則可以使用「混合」決策方法。 此方法允許您並行下載項目，並且 [!DNL Target] API調用會通過電線，直到項目下載。 閱讀最佳 [&quot;混合&quot;決策模式實踐一節](#best-practices-hybrid) 以下內容瞭解有關此方法的詳細資訊。
* 如果您有單頁應用程式(SPA), [!DNL Adobe] 建議在第一頁載入期間在載入應用程式的主JavaScript檔案之前載入和初始化at.js。 該方法較早地啟動了工件下載，提供了更快的體驗呈現。

### 當決策方法為「混合」時的最佳做法 {#best-practices-hybrid}

當使用&quot;混合&quot;作為判定方法時，並行下載該偽影。 在下載該藏物之前 [!DNL Target] 即使「位置」在設備上支援，API調用也會通過電線。 此行為是所有 `getOffers()` 在大多數情況下提供最佳效能。 如果更改的預設行為 `getOffers()` 設定 `decisioningMethod` 至 `on-device`，請遵循這些最佳做法以避免錯誤並確保最佳效能。

* 如果你決定打電話 `getOffers()` 與 `decisioningMethod` 如 `on-device` 首次載入頁面時，必須在at.js事件處理程式的&quot;ARTIFACT_DOWNLOAD_SUCCEEDED&quot;中執行此操作，以避免出錯。 如果您的項目很大，則使用此方法的任何「位置」都只在項目完全下載後才會呈現，這會延遲體驗呈現。 [!DNL Adobe] 建議您很少使用此方法。 按照最佳做法在 [「設備上」最佳實踐部分](#best-practices-on-device) 上。

## 教程：設備上決策

[!DNL Adobe Target] 設備上決策支援接近零的延遲內容傳遞。

這段7分鐘的視頻：

* 介紹設備上決策，包括與其他方法的比較 [!DNL Target] 實施
* 演示如何在中啟用設備上決策 [!DNL Target]
* 檢查已配置JSON內容的基於表單的編寫器活動示例
* 顯示包含設備上決策所需密鑰配置的示例Node.JS SDK代碼
* 在瀏覽器中演示結果

>[!VIDEO](https://video.tv.adobe.com/v/329032)

有關更多視頻和教程，請參見 [Adobe TargetTutorials](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html) 的子菜單。

## Adobe科技部落格 — 第1部分：運行 [!DNL Adobe Target] NodeJS SDK，用於邊緣平台（Akamai邊緣工作程式）上的實驗和個性化

[按一下這裡訪問部落格](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9)。

## Adobe 技術部落格 - 第 2 部分：在 Edge 平台上執行 [!DNL Adobe Target] NodeJS SDK 以進行測試和個人化 (AWS Lambda@Edge)

[按一下這裡訪問部落格](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563)。
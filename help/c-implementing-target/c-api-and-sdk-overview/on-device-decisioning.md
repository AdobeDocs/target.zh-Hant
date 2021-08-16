---
keywords: 伺服器端；伺服器端；sdk;sdk;sdk；裝置上；決策；裝置上；裝置上；零延遲；延遲；接近零；node.js
description: 了解如何使用裝置決策功能來快取伺服器上的 [!DNL Target] A/B和MVT活動，以在接近零的延遲時執行記憶體內決策。
title: 什麼是裝置上決策？
feature: 實作伺服器端
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: fe70f357e2298f1656d713aae5fae800e6775d64
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 10%

---

# 裝置上決策

裝置決策功能可讓您在伺服器上快取您的[!DNL Adobe Target] [!UICONTROL A/B測試]和[!UICONTROL 體驗鎖定目標](XT)活動，並在接近零的延遲下執行記憶體內決策，而不會封鎖對[!DNL Adobe Target]邊緣網路的網路要求。

如需詳細資訊，請參閱&#x200B;*[Adobe Target SDK檔案](https://adobetarget-sdks.gitbook.io/docs/)*&#x200B;中的[裝置上決策簡介](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning)。

## 網路研討會影片：「利用 的裝置上決策在零延遲的情況下進行個人化和測試。[!DNL Adobe Target]

市場人員、產品擁有者和開發人員被要求在網站、應用程式，以及與客戶連結的任何地方最佳化整體客戶體驗，此情況更勝以往。多種工具具有資料孤島和複雜的實施是不夠的。

在此錄制的網路研討會中，[!DNL Adobe Target]產品專家討論了如何在設備上將關鍵體驗最佳化決策移動到本地執行，同時在接近零的延遲時開啟新的使用案例的大門，同時提高客戶的網站效能。

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## 最佳實務

Adobe建議使用裝置上決策時採用下列最佳實務：

### 決策方法為「裝置上」時的最佳實務 {#best-practices-on-device}

使用「裝置上」作為決策方法時，當訪客首次載入網頁時，就會下載工件。 需要在第一個頁面載入（無快取）上發生的任何活動資格，只有在工件完全下載後才會發生。 您可以遵循某些最佳實務，以確保新匿名訪客的活動資格能快速發生。

* 停用不應位於工件中的支援「設備上」的活動。
* 如果您有[!DNL Target Premium]，則可以使用[properties/workspaces](/help/administrating-target/c-user-management/property-channel/property-channel.md)為不同的工作區建立不同的成品檔案。
* 如果您的成品檔案因合法原因而變得非常大，則可以使用「混合」決策方法。 此方法可讓您並行下載工件，所有[!DNL Target] API呼叫會通過線路，直到工件下載為止。 請閱讀下方「混合」決策模式](#best-practices-hybrid)的最佳[實務小節，深入了解此方法。
* 如果您有單頁應用程式(SPA),[!DNL Adobe]建議您在第一個頁面載入期間，先載入及初始化at.js，再載入應用程式的主要JavaScript檔案。 此方法會較早啟動工件下載，提供更快速的體驗轉譯。

### 決策方法為「混合」時的最佳實務 {#best-practices-hybrid}

當使用「混合」作為決策方法時，工件會並行下載。 在下載工件之前，任何[!DNL Target] API調用都會通過線路，即使「locations」在設備上可用。 此行為是所有`getOffers()`呼叫的預設值，在大多數情況下提供最佳效能。 如果通過將`decisioningMethod`設定為`on-device`來更改`getOffers()`的預設行為，請遵循這些最佳實踐以避免錯誤並確保最佳效能。

* 如果您決定在首次載入頁面時，以`decisioningMethod`作為`on-device`呼叫`getOffers()`，則必須在「ARTIFACT_DOWNLOAD_SUCCEEDED」 at.js事件處理常式內呼叫，以避免發生錯誤。 如果您的工件很大，則使用此方法的任何「位置」只有在工件完全下載後才會呈現，這可能會延遲體驗呈現。 [!DNL Adobe] 建議您很少使用此方法。使用此方法時，請遵循上述[&quot;On Device&quot;最佳實務區段](#best-practices-on-device)下的最佳實務以減少工件大小。

## 教學課程：裝置上決策

[!DNL Adobe Target] 裝置上決策功能可讓延遲內容傳送接近於零。

這段7分鐘的視頻：

* 說明裝置上的決策，包括與[!DNL Target]實作其他方法的比較
* 示範如何在[!DNL Target]中啟用裝置上決策功能
* 檢查已設定JSON內容的範例表單式撰寫器活動
* 顯示範例Node.JS SDK程式碼，其中包含裝置上決策所需的關鍵設定
* 在瀏覽器中演示結果

>[!VIDEO](https://video.tv.adobe.com/v/329032)

如需更多影片和教學課程，請參閱[Adobe TargetTutorials](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html??lang=zh-Hant)指南。

## Adobe技術部落格 — 第1部分：執行[!DNL Adobe Target] NodeJS SDK，在邊緣平台（Akamai邊緣背景工作）上試驗和個人化

[按一下這裡以存取部落格文章](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9)。

## Adobe 技術部落格 - 第 2 部分：在 Edge 平台上執行 [!DNL Adobe Target] NodeJS SDK 以進行測試和個人化 (AWS Lambda@Edge)

[按一下這裡以存取部落格文章](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563)。
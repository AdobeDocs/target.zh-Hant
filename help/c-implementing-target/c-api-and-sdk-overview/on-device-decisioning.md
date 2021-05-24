---
keywords: 伺服器端；伺服器端；sdk;sdk;sdk；裝置上；決策；裝置上；裝置上；零延遲；延遲；接近零；node.js
description: 了解如何使用裝置決策功能來快取伺服器上的 [!DNL Target] A/B和MVT活動，以在接近零的延遲時執行記憶體內決策。
title: 什麼是裝置上決策？
feature: 實作伺服器端
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: ed4e6715c120fe692c7f3f84f6b869b5ad9bd1b7
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 20%

---

# 裝置上決策

裝置決策功能可讓您在伺服器上快取您的[!DNL Adobe Target] [!UICONTROL A/B測試]和[!UICONTROL 體驗鎖定目標](XT)活動，並在接近零的延遲下執行記憶體內決策，而不會封鎖對[!DNL Adobe Target]邊緣網路的網路要求。

如需詳細資訊，請參閱&#x200B;*[Adobe Target SDK檔案](https://adobetarget-sdks.gitbook.io/docs/)*&#x200B;中的[裝置上決策簡介](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning)。

## 網路研討會影片：「利用 Adobe Target 的裝置上決策在零延遲的情況下進行個人化和測試。

市場人員、產品擁有者和開發人員被要求在網站、應用程式，以及與客戶連結的任何地方最佳化整體客戶體驗，此情況更勝以往。多種具有資料獨立單位和複雜實施的工具無法做到。

在此錄制的網路研討會中，[!DNL Adobe Target]產品專家討論了如何在設備上將關鍵體驗最佳化決策移動到本地執行，同時在接近零的延遲時開啟新的使用案例的大門，同時提高客戶的網站效能。

>[!VIDEO](https://video.tv.adobe.com/v/328148)

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

## Adobe技術部落格 — 第2部分：執行[!DNL Adobe Target] NodeJS SDK以在邊緣平台上進行實驗和個人化(AWS Lambda@Edge)

[按一下這裡以存取部落格文章](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563)。
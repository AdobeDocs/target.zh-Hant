---
keywords: at.js;non-production;non production;deploy
description: 關於如何安全地將 at.js 部署至非生產環境的資訊。
title: 將at.js部署至非生產環境
feature: at.js
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 90%

---


# 將at.js部署至非生產環境

安全將 at.js 部署到非生產環境的技術相關資訊。

## 部署至 DTM 測試

如果您使用 DTM，可以輕鬆將 at.js 儲存在您的 Adobe Target Tool 組態中。

儲存資料庫之後，使用 DTM Switch 工具來對生產程式碼測試它。這也將讓您的 Adobe 顧問易於支援您。

如需詳細資訊，請參閱&#x200B;*《使用動態標籤管理來實施 Adobe Target 的最佳作法》*&#x200B;指南中的[選項 3: 使用 DTM 託管的 Target JavaScript 資料庫手動實施 Target](https://experienceleague.adobe.com/docs/dtm/implementing/target/add-target/t-implementing-target-manually-js-hosted-dtm.html)。

## 使用 &quot;Requestly&quot; Chrome 擴充功能來對應至另一個檔案

>[!NOTE]
>
>除了下列資訊外，您還可以使用適用於 Google Chrome 的 [Adobe Target VEC Helper 瀏覽器擴充功能](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

[Requestly](https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=en) 為免費的 Chrome 擴充功能，可讓您將要求重新導向至替代的 URL。

您可以將 at.js 部署至某個 URL，然後使用 Requestly 將您目前的 mbox.js 檔案 URL 對應至新的 at.js URL。然後，每當您的網站嘗試載入 mbox.js 時，它會改為載入 at.js。此方法也讓 Adobe 易於提供支援。

## 部署至開發、測試或 QA 環境

如果您在程式碼基底中託管 mbox.js，並且可以輕鬆對您的程式碼環境進行更新，請將 at.js 部署至您的其中一個較低環境。

為了從 Adobe 獲得較好的支援，請將檔案部署至 Adobe 可存取的環境。

## 使用 Charles 或 Fiddler 來對應至本機檔案

[Charles Web Debugging Proxy](https://www.charlesproxy.com/) 是一項可供 Mac 和 Windows 使用的應用程式，其 Map Local 功能可用來將您的生產 mbox.js 檔案的載入對應至 at.js 的本機複本。Mac 和 Windows 適用的免費試用版可供下載。

[Fiddler](https://www.telerik.com/fiddler) 是類似的工具，以 Windows 適用的免費下載方式提供。

## 部署至另一個標記管理程式環境

如果您使用另一個標記管理程式，則可能有方式來安全地部署 at.js 而不會影響您的生產流量。
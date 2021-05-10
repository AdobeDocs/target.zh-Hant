---
keywords: at.js；非生產；非生產；部署
description: 瞭解Adobe Target的舊版mbox.js實作。 移轉至Adobe Experience Platform網頁SDK（AEP網頁SDK）或最新版的at.js。
title: 如何將at.js部署至非生產環境？
feature: at.js
role: Developer
exl-id: 607b2b5b-bb2a-4443-abc0-452b421fc009
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 80%

---

# 將at.js部署至非生產環境

安全將 at.js 部署到非生產環境的技術相關資訊。

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

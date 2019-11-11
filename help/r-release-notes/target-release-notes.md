---
keywords: 發行說明；發行；更新；未來發行；增強；新功能；修正
description: 提供最新或即將發行的DNL Adobe target版本功能、增強功能和修正資訊的發行說明。
title: Adobe target搶鮮版注意事項
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: af0434a14bf9a816366941b9e2108fb8ba7c9d24

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新: 2019 年 10 月 31 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
>
>括號內的問題編號供 [!DNL Adobe] 內部使用。

## 目標Java SDK 1.0.1版（2019年11月11日）

1.0.1版中已修正下列問題：

* 即使沒有訪客API cookie存在，仍可在Target請求中傳送補充資料ID。

如需詳細資訊，請參 [閱版本注意事項——目標Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)。

## 目標平台（2019年10月31日）

| 功能/增強功能 | 說明 |
| --- | --- |
| Java SDK | Java [!DNL Target] SDK可讓您部署 [!DNL Target] 伺服器端。 此Java SDK可協助您輕鬆 [!DNL Target] 地與其 [!DNL Adobe Experience Cloud] 他解決方案整 [!DNL Adobe Experience Cloud Identity Service]合， [!DNL Adobe Analytics]例如 [!DNL Adobe Audience Manager]。<br>Java SDK透過我們的傳送API與整合時引入最佳實務並免除複雜性， [!DNL Target] 讓您的工程團隊能夠專注在商業邏輯上。 以下是我們在最新版本中推出的主要功能：<ul><li>支援預取和通知，讓您透過快取最佳化效能。</li><li>支援在網頁和伺服器端混合整 [!DNL Target] 合時最佳化效能。 我們將引入由 `serverState` 透過伺服器端擷取的體驗填入的設定，如此at.js 2.2就不會再進行額外的伺服器呼叫來擷取體驗。 此方法可最佳化頁面載入效能。</li><li>支援透過Java SDK擷取VEC建立的活動，此為全新的傳送API所提供。</li><li>開放來源，讓您的開發人員可以為 [Target Java SDK貢獻心力](https://github.com/adobe/target-java-sdk)。</li></ul>如需詳細資訊，請參 [閱版本注意事項——目標Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)。<br>透過全新的Target Java SDK，在Adobe技術部落格——伺服器 [端最佳化中進一步瞭解Target Java SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)。 |

## Target Standard/Premium 19.10.2 (2019 年 10 月 31 日)

| 功能/增強功能 | 說明 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) 搭配多值屬性使用 | 有時，您想要使用多值欄位。 考量下列範例:<ul><li>您提供影片給使用者。 某部電影有多位演員。</li><li>你賣音樂會的票。 給定用戶有多個喜愛的樂隊。</li><li>你賣衣服。 T恤衫有多種尺寸。</li></ul>若要處理這些案例中的建議，您可以將多值資料傳遞至Target Recommendations，並使用特殊的多值運算子。 |

## Target Standard/Premium 20.1.1

Target Standard/Premium 20.1.1版將於2020年1月推出。 其確切日期、功能和增強功能將會在此公佈。

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

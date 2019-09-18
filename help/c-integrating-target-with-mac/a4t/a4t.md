---
description: Adobe "Analytics for Target" (A4T) 是交叉解決方案的整合，可讓您根據 Analytics 轉換量度和對象區段來建立活動。這個整合可讓您使用 Analytics 報表來檢查您的結果。如果您使用 Analytics 做為活動的報表來源，則該活動的所有報表和區段都會根據 Analytics 資料收集。
keywords: a4t;analytics;analytics for target;analytics 報表來源;adobe analytics 作為 target 的報表來源
seo-description: Adobe "Analytics for Target" (A4T) 是交叉解決方案的整合，可讓您根據 Analytics 轉換量度和對象區段來建立活動。這個整合可讓您使用 Analytics 報表來檢查您的結果。如果您使用 Analytics 做為活動的報表來源，則該活動的所有報表和區段都會根據 Analytics 資料收集。
seo-title: Adobe Analytics 作為 Adobe Target (A4T) 的報表來源
solution: Target
subtopic: 多變數測試
title: Adobe Analytics 作為 Adobe Target (A4T) 的報表來源
topic: Standard
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Adobe Analytics 作為 Adobe Target (A4T) 的報表來源{#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

Adobe "Analytics for Target" (A4T) 是交叉解決方案的整合，可讓您根據 Analytics 轉換量度和對象區段來建立活動。A4T 整合可讓您使用 Analytics 報表來檢查成果。如果您使用 Analytics 做為活動的報表來源，則該活動的所有報表和區段都會根據 Analytics 資料收集。

## A4T 概覽 {#section_92B66069210C40DBA937790E8CC596CF}

Analytics 與 Target 之間的 Analytics for Target 整合為您的最佳化程式提供強大的分析與省時工具。

在 Target 中使用 Analytics 資料的三大優點如下:

* 市場行銷人員可隨時動態地將 Analytics 成功量度或報表區段套用至 Target 活動報表: 執行活動之前完全不需要指定。
* 單一資料來源可排除在兩個不同系統中收集資料時發生不一致的情況。
* 您現有的 Adobe Analytics 實作會收集所有必要的資料。不需要只為了收集報表的資料而在頁面上實作 Mbox。儘管如此，仍建議您為「自動個人化 (AP)」活動實作訂單確認 Mbox。

>[!IMPORTANT]
>
>開始使用 A4T 之前，您必須要求針對整合佈建您的帳戶。使用[此表單](https://www.adobe.com/go/audiences)來要求佈建帳戶。
>
>此整合可讓 Adobe Analytics 成為 Adobe Target (A4T) 的資料來源，象徵新一代的 Test&amp;Target 至 SiteCatalyst 外掛程式。此外掛程式已淘汰，但仍支援原本已使用的客戶。

如果您使用 Analytics 作為活動的報表來源，則該活動的報表和分段會完全根據 Analytics。

所有 Analytics 量度 (包括計算量度) 皆可在 Target Standard/Premium 中及 Analytics 的 Target 活動報表中使用。同樣地，Analytics 中可用的任何區段皆可套用至這兩個解決方案。在 Target Standard/Premium 中，您可以在測試開始後，甚至在測試完成後，將量度或對象套用至報表。

每個量度皆包含在內，包括 Analytics 內建的任何客戶量度或計算量度。

分類期過後，從網站收集完資料的大約一小時後，資料就會出現在這些報表中。報表中的所有量度、區段和值，來自於您設定活動時所選取的報表套裝。

考慮使用 A4T 時，請謹記下列重點:

* 若要使用 Adobe Analytics 作為 Adobe Target 的報表來源，您與公司皆必須具備 Adobe Analytics 和 Adobe Target 的存取權。[如果您需要任一解決方案，請聯絡客戶代表](../../cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。
* 每個活動皆會設定報表來源。Target 會持續收集資料供報表使用，如果您偏好以 Target 收集的資料作為活動的基礎，則 Target 資料仍然可用。
* 您必須使用這兩個報表來源的其中一個。您無法同時從這兩個來源收集單一活動的資料。
* 使用 A4T 時，活動可用的所有成功量度皆為 Analytics 量度。不過，目標量度可以根據 Mbox 呼叫。例如，您可以搭配 A4T 使用 Target 內建的點擊追蹤功能，而不必實作 Analytics 點擊追蹤程式碼。
* 在 Target UI 中檢視 A4T 活動的報表時，實際上是檢視 Analytics 資料。例如，如果您在 Target 中使用「訪客」量度，實際上是使用 Analytics 訪客量度，而非 Target 訪客量度 (現在稱為「加入者」)。對於基本流量量度 (訪客、造訪、頁面檢視) 和轉換量度，此差異尤其重要。
* 任何現有 Target 活動會繼續使用 Target 資料集合，不因為啟用 A4T 而受影響。
* 使用 Analytics 作為報表來源時，僅允許一個 Mbox 型量度。
* 從 Target 至 Analytics 的伺服器對伺服器呼叫會將活動和體驗資訊傳送至 Analytics。此整合不會對 Target 或 Analytics 產生額外的伺服器呼叫。

   在某些情況下，從Target到Analytics的分類呼叫可能會失敗，而活動不會在Analytics中顯示資料。 如果發生此情況，請 [參閱「疑難排解Analytics與Target整合(A4T)」](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)。 您也可以聯 [絡Client Care](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) ，以取得進一步協助。

## 支援的活動類型 {#section_F487896214BF4803AF78C552EF1669AA}

下表顯示哪些活動類型支援將 Analytics 作為報表來源 (A4T):

| 活動類型 | A4T 相容? | 備註 (若適用) |
|--- |--- |--- |
| 手動分割流量的 A//B 活動 | 是 |  |
| 自動分配的 A/B 活動 | 無 |  |
| 自動鎖定目標的 A/B 活動 | 無 |  |
| 體驗鎖定目標 (XT) | 是 |  |
| 多變數測試 (MVT) | 是 | 需要 Mbox 型目標量度目標才能取得「元素貢獻」報表。「元素貢獻報表」目前不支援 Analytics 量度。 |
| 自動個人化 (AP) 活動 | 無 |  |
| Recommendations 活動 | 是 |  |
| 行動應用程式 | 是 | 支援行動服務 SDK 4.13.1 版或更新版本。如需詳細資訊，請參閱[行動服務文件](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)。 |
| 電子郵件 | 無 |  |
| 伺服器端傳送 API | 是 | 如需詳細資訊，請參閱[伺服器端: 實作 Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| NodeJS SDK | 是 | 如需詳細資訊，請參閱[伺服器端: 實作 Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| AEM 6.1 (或更舊) 雲端服務整合 | 無 |  |
| AEM 6.2 (或更新) 雲端服務整合 | 是 | 如需詳細資訊，請參閱 Adobe Experience Manager 6.2 文件中的[與 Adobe Target 整合](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html)。 |
| 使用重新導向選件的任何活動 | 是 | 搭配 A4T 使用重新導向選件時，最低需求較嚴格。如需詳細資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。 |
| Node.JS | 是 |  |

因為所有活動類型尚未支援 A4T，建議您保留或實作重要的轉換 Mbox，例如 "orderConfirmPage" Mbox。

## A4T 報表的範例 {#section_F0A43A1CB2F04E8282B909E4D7034361}

若要在 [!DNL Target] 中檢視 A4T 報表，請按一下&#x200B;**[!UICONTROL 「活動」]**，從清單中選取所需的活動 (使用 [!DNL Analytics] 作為報表來源)，然後按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。

>[!NOTE]
>
>您可以使用[!UICONTROL 「活動」]頁面頂端的[!UICONTROL 「報表來源」]下拉式清單，指定只顯示使用 [!DNL Analytics] 作為報表來源的活動。

您可以按一下報表右上方適當的圖示，在「表格檢視」和[!UICONTROL 「圖表檢視」]之間切換。

下圖顯示 A4T 報表的[!UICONTROL 「圖表檢視」]，其中[!UICONTROL 「報表量度」]下拉式清單顯示可用的 [!DNL Analytics] 目標量度:

![](assets/a4t_report_graph1.png)

下圖顯示 A4T 報表的[!UICONTROL 「圖表檢視」]，其中[!UICONTROL 「對象」]下拉式清單顯示可用的 [!DNL Analytics] 對象:

![](assets/a4t_report_graph2.png)

下圖顯示 A4T 報表的[!UICONTROL 「表格檢視」]:

![](assets/a4t_report_table.png)

若要在 [!DNL Analytics] 中檢視報表，而非在 [!DNL Target] 中，請按一下報表頂端的&#x200B;**在 Analytics 中檢視**。

## Analytics 與 Target: Analysis 最佳實務教學課程 {#section_3438E6E77A464424B717A4FD333B84B2}

開啟由 Adobe Experience League 所提供的 [Analytics 與 Target: Analysis 最佳實務](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)教學課程。

## 訓練影片:

以下影片含有本文章探討之概念的詳細資訊。

### Analytics for Target (A4T) (4:32)

此影片說明如何使用 Adobe Analytics 做為 Adobe Target 中的報表來源，以推動最佳化程式的分析。

* 說明何謂 A4T 以及為何您會使用它
* 說明 A4T 的運作方式
* 瞭解使用 A4T 之前所需的先決條件

>[!VIDEO](https://video.tv.adobe.com/v/17384?captions=chi_hant)

### Analytics/Target 整合 (A4T) (40:33)

這支影片記錄了「[營業時間](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」，這是一項 Adobe 客戶服務團隊主導的計劃。

* 如何設定並驗證整合項目成功運作
* 整合項目的運作原理
* 瞭解適合用於 Analytics 的報表
* 回答有關 A4T 的常見問題

[Analytics/Target整合(A4T)辦公時間](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)
---
keywords: a4t;analytics;analytics for target;analytics 報告來源;adobe analytics 當作 target 的報告來源;atjs;at.js;adobe experience platform web sdk;platform web sdk;platform sdk
description: 使用 [!DNL Analytics] for [!DNL Target] (A4T) 可根據 [!DNL Analytics] 轉換量度和受眾區段建立活動，並使用 [!DNL Analytics] 報表來檢查結果。
title: 什麼是 [!DNL Analytics] for [!DNL Target] (A4T)？
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: ht
source-wordcount: '1125'
ht-degree: 100%

---

# [!DNL Adobe Analytics] 當作 [!DNL Adobe Target] (A4T) 的報告來源

[!DNL Adobe Analytics for Target] (A4T) 是一種跨解決方案的整合，可讓您根據 [!DNL Analytics] 轉換量度和受眾區段來建立活動。 A4T 整合可讓您使用 [!DNL Analytics] 報表來檢查您的結果。 如果您使用 [!DNL Analytics] 當作活動的報告來源，則該活動的所有報告和區段都會根據 [!DNL Analytics] 資料收集。

## 總覽 {#section_92B66069210C40DBA937790E8CC596CF}

[!DNL Analytics] 與 [!DNL Target] 之間的 [!DNL Analytics for Target] 整合為您的最佳化程式提供強大的分析與省時的工具。

在 [!DNL Target] 中使用 [!DNL Analytics] 資料的三大優點包括：

* 行銷人員可隨時動態地將 [!DNL Analytics] 成功量度或報告區段套用至 [!DNL Target] 活動報表。 執行活動之前完全不需要指定。
* 單一資料來源可排除在兩個不同系統中收集資料時發生不一致的情況。
* 您現有的 [!DNL Analytics] 實作會收集所有必要的資料。 不需要僅為了收集報表的資料而在頁面上實作 Mbox。

如果您使用 [!DNL Analytics] 當作活動的報告來源，則該活動的所有報告和區段都會根據 [!DNL Analytics]。

所有 [!DNL Analytics] 量度 (包括計算量度) 在 [!DNL Target] 及 [!DNL Analytics] 的 [!UICONTROL Target 活動]報表中都有提供，但有一個例外狀況。 不支援[!UICONTROL 提升度和信賴度]的計算量度。 同樣地，[!DNL Analytics] 中提供的任何區段皆可套用至這兩個解決方案。 在 [!DNL Target] 中，您可以在活動開始後，或甚至在活動完成後，將量度或受眾套用至報表。

每個量度皆包含在內，包括 [!DNL Analytics] 內建的任何自訂量度或計算量度。

分類期過後，從網站收集完資料的大約一小時後，資料就會出現在這些報表中。報表中的所有量度、區段和值，來自於您設定活動時所選取的報表套裝。

考慮使用 A4T 時，請謹記下列重點:

* 若要使用 [!DNL Analytics] 作為 [!DNL Target] 的報告來源，您與貴公司皆必須擁有 [!DNL Analytics] 和 [!DNL Target] 的存取權。 [如果您需要任一解決方案，請聯絡客戶代表](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。
* 每個活動皆會設定報告來源。 [!DNL Target] 會持續收集資料以供報告使用，如果您偏好以 [!DNL Target] 收集的資料作為活動的基礎，還是可以使用 [!DNL Target] 資料。
* 使用某個報告來源或其他報告來源。 您無法同時從這兩個來源收集單一活動的資料。
* 使用 A4T 時，活動可用的所有成功量度皆為 [!DNL Analytics] 量度。 不過，如果使用 at.js，則目標量度可以根據 Mbox 呼叫。 例如，您可以搭配 A4T 使用 Target 現成的點擊追蹤功能，而不必實作 [!DNL Analytics] 點擊追蹤程式碼。
* 在 [!DNL Target] UI 中檢視 A4T 活動的報告時，您實際上是檢視 [!DNL Analytics] 資料。 例如，如果您在 [!DNL Target] 中使用[!UICONTROL 訪客]量度，您實際上是使用 [!DNL Analytics] [!UICONTROL 訪客]量度，而非 [!DNL Target] [!UICONTROL 訪客]量度 (現在稱為[!UICONTROL 加入者])。 對於基本流量量度 ([!UICONTROL 訪客數]、[!UICONTROL 造訪次數]、[!UICONTROL 頁面瀏覽數]) 和轉換量度，此差異尤其重要。
* 任何現有 [!DNL Target] 活動都會繼續使用 [!DNL Target] 資料收集，不因為啟用 A4T 而受到影響。
* 在使用 A4T 時，只允許一個 mbox 型量度。
* 從 [!DNL Target] 到 [!DNL Analytics] 的伺服器對伺服器呼叫會將活動和體驗資訊傳送至 [!DNL Analytics]。 此整合不會對 [!DNL Target] 或 [!DNL Analytics] 產生額外的伺服器呼叫。

   在某些情況下，從 [!DNL Target] 到 [!DNL Analytics] 的分類會失敗，而且活動不會在 [!DNL Analytics] 中顯示資料。 請參閱[針對 Analytics 和 Target 整合 (A4T) 進行疑難排解](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)。 如需進一步協助，您也可以[聯絡客戶服務](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。

## 實作 A4T

如需使用 at.js 和 [!DNL Adobe Experience Platform Web SDK] 實作 A4T 的相關資訊，請參閱 [Analytics for [!DNL Target] 實作](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)。

## 支援的活動類型 {#section_F487896214BF4803AF78C552EF1669AA}

以下幾節包含在使用 [!DNL Adobe Experience Platform Web SDK] 或 at.js 時支援的活動類型的相關資訊：

| 活動類型 | A4T 相容? | 備註 (若適用) |
|--- |--- |--- |
| [使用手動流量分割的 A/B 活動](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |  |
| [使用自動分配的 A/B 活動](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 是 | 請參閱[自動分配和自動鎖定目標活動的 A4T 支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| [使用自動鎖定目標的 A/B 活動](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 是 | 請參閱[自動分配和自動鎖定目標活動的 A4T 支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。 |
| [體驗鎖定 (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | 是 |  |
| [多變數測試 (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | 是 | 需要 Mbox 型目標量度目標才能取得[!UICONTROL 元素貢獻]報表。 [!UICONTROL 元素貢獻]報表目前不支援 [!DNL Analytics] 量度。 |
| [Automated Personalization (AP) 活動](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | 否 |  |
| [Recommendations 活動](/help/main/c-recommendations/recommendations.md) | 是 |  |
| [任何使用重新導向選件的活動](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | 是 |

由於所有活動類型都尚未支援 A4T，建議您保留或實作重要的轉換 Mbox，例如 `orderConfirmPage` Mbox。

## A4T 報表的範例 {#section_F0A43A1CB2F04E8282B909E4D7034361}

若要在 [!DNL Target] 中檢視 A4T 報表，請按一下&#x200B;**[!UICONTROL 活動]**，從清單中按一下所需的活動 (該活動使用 [!DNL Analytics] 作為其報告來源)，然後按一下&#x200B;**[!UICONTROL 報表]**&#x200B;索引標籤。

>[!NOTE]
>
>您可以使用[!UICONTROL 活動]頁面頂端的[!UICONTROL 報告來源]下拉式清單，只顯示使用 A4T 的活動。

您可以按一下報表右上方的適當圖示，在報表的[!UICONTROL 表格檢視]與[!UICONTROL 圖表檢視]之間切換。

下圖顯示 A4T 報表的[!UICONTROL 「圖表檢視」]，其中[!UICONTROL 「報表量度」]下拉式清單顯示可用的 [!DNL Analytics] 目標量度:

![](assets/a4t_report_graph1.png)

下圖顯示 A4T 報表的[!UICONTROL 「圖表檢視」]，其中[!UICONTROL 「受眾」]下拉式清單顯示可用的 [!DNL Analytics] 受眾:

![](assets/a4t_report_graph2.png)

下圖顯示 A4T 報表的[!UICONTROL 「表格檢視」]:

![](assets/a4t_report_table.png)

若要在 [!DNL Analytics] 中檢視報表，而非在 [!DNL Target] 中，請按一下報表頂端的&#x200B;**[!UICONTROL 在 Analytics 中檢視]**。

## Analytics 與 Target：分析最佳做法教學課程 {#section_3438E6E77A464424B717A4FD333B84B2}

開啟 [!DNL Adobe Experience League] 提供的 [Analytics 與 Target：分析最佳做法](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)教學課程。

## 培訓影片：

以下影片包含有關本主題探討之概念的詳細資訊。

### Analytics for Adobe Target (A4T) (4:32) ![總覽徽章](/help/main/assets/overview.png)

此影片說明如何使用 [!DNL Analytics] 作為 [!DNL Target] 中的報告來源，以推動最佳化程式的分析。

* 說明何謂 A4T 以及為何您會使用它
* 說明 A4T 的運作方式
* 瞭解使用 A4T 之前所需的先決條件

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics / Adobe Target 整合 (A4T) (40:33) ![教學課程徽章](/help/main/assets/tutorial.png)

這支影片記錄了「[辦公時間](/help/main/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」，「辦公時間」是一項由 Adobe 客戶服務團隊主導的計劃。

* 如何設定並驗證整合項目成功運作
* 整合項目的運作原理
* 瞭解適合用於 Analytics 的報表
* 回答有關 A4T 的常見問題

[Analytics/Target 整合 (A4T) 辦公時間](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [Analytics for [!DNL Target] 實作](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)：包含 at.js 和 Platform Web SDK 的實作資訊。
>* [重新導向選件 - A4T 常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
>* [什麼是 Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)：包含有關 Platform Web SDK 的總覽資訊。
>* [Target 總覽](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)：包含 [!DNL Target] 和 [!DNL Platform Web SDK] 特有的資訊。


---
keywords: a4t;analytics;analytics;analytics for target;analytics reporting source;adobe analytics作為目標的報告來源；atjs;at.js;adobe體驗平台web sdk；平台web sdk；平台sdk
description: 使用 [!DNL Analytics] 為 [!DNL Target] (A4T)建立基於 [!DNL Analytics] 轉換度量和受眾段，使用 [!DNL Analytics] 報告以檢查結果。
title: 什麼是 [!DNL Analytics] 為 [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 30%

---

# [!DNL Adobe Analytics] 作為 [!DNL Adobe Target] (A4T)

[!DNL Adobe Analytics for Target] (A4T)是一種跨解決方案整合，允許您根據 [!DNL Analytics] 轉換指標和受眾段。 A4T整合允許您 [!DNL Analytics] 報告以檢查結果。 如果您使用 [!DNL Analytics] 作為活動的報告源，該活動的所有報告和細分都基於 [!DNL Analytics] 資料收集。

## 總覽 {#section_92B66069210C40DBA937790E8CC596CF}

的 [!DNL Analytics for Target] 整合 [!DNL Analytics] 和 [!DNL Target] 為優化程式提供了功能強大的分析和節省時間的工具。

使用的三大優勢 [!DNL Analytics] 資料 [!DNL Target] 為：

* 營銷人員可以動態應用 [!DNL Analytics] 成功度量或報告段 [!DNL Target] 活動報告。 執行活動之前完全不需要指定。
* 單一資料來源可排除在兩個不同系統中收集資料時發生不一致的情況。
* 您的現有 [!DNL Analytics] 實現會收集所有所需資料。 不需要只為了收集報表的資料而在頁面上實作 Mbox。

如果您使用 [!DNL Analytics] 作為活動的報告源，該活動的所有報告和細分都基於 [!DNL Analytics]。

全部 [!DNL Analytics] 度量，包括計算度量，可在 [!DNL Target] 和 [!UICONTROL 目標活動] 報告 [!DNL Analytics]，但有一個例外。 計算的度量 [!UICONTROL 提升和信心] 不支援。 同樣， [!DNL Analytics] 可以應用於兩種解決方案。 您可以將度量或受眾應用於中的報告 [!DNL Target] 在活動啟動後，甚至在活動完成後。

包括每個度量，包括任何內置的自定義或計算度量 [!DNL Analytics]。

分類期過後，從網站收集完資料的大約一小時後，資料就會出現在這些報表中。報表中的所有量度、區段和值，來自於您設定活動時所選取的報表套裝。

考慮使用 A4T 時，請謹記下列重點:

* 要使用 [!DNL Analytics] 作為 [!DNL Target]，您和您的公司必須有權訪問 [!DNL Analytics] 和 [!DNL Target]。 [如果您需要任一解決方案，請聯絡客戶代表](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。
* 每個活動皆會設定報表來源。[!DNL Target] 繼續收集要用於報告和 [!DNL Target] 如果您希望根據收集的資料來生成活動，則仍可使用資料 [!DNL Target]。
* 使用一個報告源或另一個報告源。 您無法同時從這兩個來源收集單一活動的資料。
* 使用A4T時，您的活動可用的所有成功度量都是 [!DNL Analytics] 度量。 但是，如果使用at.js，則目標度量可以基於mbox調用。 例如，您可以將Target的現成點擊跟蹤功能與A4T配合使用，而不必實施 [!DNL Analytics] 按一下跟蹤代碼。
* 在中查看A4T活動的報告時 [!DNL Target] UI，您正在查看 [!DNL Analytics] 資料。 例如，如果 [!UICONTROL 訪問者] 度量 [!DNL Target]，您正在使用 [!DNL Analytics] [!UICONTROL 訪問者] 度量，不是 [!DNL Target] [!UICONTROL 訪問者] 度量，現在稱為 [!UICONTROL 新入者]。 這一差異對於基本流量指標([!UICONTROL 訪問者]。 [!UICONTROL 訪問]。 [!UICONTROL 頁面視圖])和轉換度量。
* 任何現有 [!DNL Target] 活動繼續使用 [!DNL Target] 不受啟用A4T的影響。
* 使用A4T時，僅允許使用一個基於框的度量。
* 從伺服器到伺服器的呼叫 [!DNL Target] 至 [!DNL Analytics] 將活動和經驗資訊發送到 [!DNL Analytics]。 此整合不會導致額外伺服器調用 [!DNL Target] 或 [!DNL Analytics]。

   在某些情況下， [!DNL Target] 至 [!DNL Analytics] 失敗，活動不顯示資料 [!DNL Analytics]。 請參閱 [對分析和目標整合進行故障排除(A4T)](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)。 您也可以 [聯繫客戶保護](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) 尋求進一步幫助。

## 實施A4T

有關使用at.js和 [!DNL Adobe Experience Platform Web SDK]，請參閱 [分析 [!DNL Target] 實施](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)。

## 支援的活動類型 {#section_F487896214BF4803AF78C552EF1669AA}

以下各節包含有關使用 [!DNL Adobe Experience Platform Web SDK] 或at.js:

| 活動類型 | A4T 相容? | 備註 (若適用) |
|--- |--- |--- |
| [手動分割流量的 A//B 活動](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |  |
| [自動分配的 A/B 活動](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 是 | 請參閱 [A4T支援自動分配和自動目標活動](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| [自動鎖定目標的 A/B 活動](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 是 | 請參閱 [A4T支援自動分配和自動目標活動](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)。 |
| [體驗鎖定 (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | 是 |  |
| [多變數測試 (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | 是 | 需要基於框的目標度量目標來獲取 [!UICONTROL 要素貢獻] 報告。 的 [!UICONTROL 要素貢獻] 報告當前不支援 [!DNL Analytics] 度量。 |
| [自動個人化 (AP) 活動](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | 無 |  |
| [Recommendations 活動](/help/main/c-recommendations/recommendations.md) | 是 |  |
| [使用重定向服務的任何活動](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | 是 |

由於所有活動類型都不支援A4T，因此建議您保留或實施重要的轉換框，如 `orderConfirmPage` 的子菜單。

## A4T報告示例 {#section_F0A43A1CB2F04E8282B909E4D7034361}

查看A4T報告 [!DNL Target]按一下 **[!UICONTROL 活動]**，從使用 [!DNL Analytics] 作為報告源，然後按一下 **[!UICONTROL 報告]** 頁籤。

>[!NOTE]
>
>您可以使用 [!UICONTROL 報告源] 清單 [!UICONTROL 活動] 頁面，僅顯示使用A4T的活動。

可以在 [!UICONTROL 表視圖] 和 [!UICONTROL 圖形視圖] 的子菜單。

下圖顯示 A4T 報表的[!UICONTROL 「圖表檢視」]，其中[!UICONTROL 「報表量度」]下拉式清單顯示可用的 [!DNL Analytics] 目標量度:

![](assets/a4t_report_graph1.png)

下圖顯示 A4T 報表的[!UICONTROL 「圖表檢視」]，其中[!UICONTROL 「對象」]下拉式清單顯示可用的 [!DNL Analytics] 對象:

![](assets/a4t_report_graph2.png)

下圖顯示 A4T 報表的[!UICONTROL 「表格檢視」]:

![](assets/a4t_report_table.png)

若要在 [!DNL Analytics] 中檢視報表，而非在 [!DNL Target] 中，請按一下報表頂端的&#x200B;****&#x200B;在 Analytics 中檢視。

## Analytics 與 Target: Analysis 最佳實務教學課程 {#section_3438E6E77A464424B717A4FD333B84B2}

開啟 [分析和目標：分析的最佳做法](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) 教程，提供者 [!DNL Adobe Experience League]。

## 訓練影片:

以下視頻包含有關本主題中討論的概念的詳細資訊。

### Adobe Target分析(A4T)(4:32) ![概述徽章](/help/main/assets/overview.png)

此視頻說明如何使用 [!DNL Analytics] 作為中的報告源 [!DNL Target] 來驅動優化程式的分析。

* 說明何謂 A4T 以及為何您會使用它
* 說明 A4T 的運作方式
* 瞭解使用 A4T 之前所需的先決條件

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### 分析/Adobe Target整合(A4T)(40:33) ![教程徽章](/help/main/assets/tutorial.png)

這支影片記錄了「[營業時間](/help/main/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」，這是一項 Adobe 客戶服務團隊主導的計劃。

* 如何設定並驗證整合項目成功運作
* 整合項目的運作原理
* 瞭解適合用於 Analytics 的報表
* 回答有關 A4T 的常見問題

[分析/目標整合(A4T)辦公時間](https://helpx.adobe.com/tw/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [分析 [!DNL Target] 實施](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md):包含at.js和平台Web SDK的實現資訊。
>* [重新導向選件 - A4T 常見問答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
>* [什麼是Adobe Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html):包含有關平台Web SDK的概述資訊。
>* [目標概述](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html):包含特定於 [!DNL Target] 和 [!DNL Platform Web SDK]。


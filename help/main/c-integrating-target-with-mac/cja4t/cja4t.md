---
keywords: cja4t；customer journey analytics；customer journey analytics for target；customer journey analytics報告來源；customer journey analytics作為target的報告來源
description: 使用 [!DNL Adobe Customer Journey Analytics] for [!DNL Target] (A4T) 可根據 [!DNL Customer Journey Analytics] 轉換量度和受眾區段建立活動，並使用 [!DNL Customer Journey Analytics] 報表來檢查結果。
title: 什麼是 [!DNL Adobe Customer Journey Analytics] 的 [!DNL Target] (CJA4T)？
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 79d4bfa7bbdaea6b779ab548b80fbcf732635ba5
workflow-type: tm+mt
source-wordcount: '1001'
ht-degree: 16%

---

# [!DNL Adobe Customer Journey Analytics] 做為的報表來源 [!DNL Adobe Target] (CJA4T)

[!DNL Customer Journey Analytics for Target] (CJA4T)是一種跨解決方案的整合，可讓您根據以下專案建立活動： [Customer Journey Analytics(CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html){target=_blank} 轉換量度。 CJA4T整合可讓您使用 [!DNL Customer Journey Analytics] 報告以檢查您的結果。 如果您使用 [!DNL Customer Journey Analytics] 做為活動的報表來源，該活動的所有報表都以下列專案為基礎 [!DNL Customer Journey Analytics] 資料彙集。

## 總覽

[!DNL Customer Journey Analytics] 與 [!DNL Target] 之間的 [!DNL Customer Journey Analytics for Target] 整合為您的最佳化程式提供強大的分析與省時的工具。

在 [!DNL Target] 中使用 [!DNL Customer Journey Analytics] 資料的三大優點包括：

* 行銷人員可隨時動態地將 [!DNL Customer Journey Analytics] 成功量度或報告區段套用至 [!DNL Target] 活動報表。 執行活動之前完全不需要指定。
* 單一資料來源可在兩個獨立系統中收集資料時，將發生的差異降至最低。
* 您現有的 [!DNL Customer Journey Analytics] 實施會收集所有必要的資料。 不需要僅為了收集報表的資料而在頁面上實作 Mbox。

考慮使用CJA4T時，請記住以下幾點：

* 若要使用 [!DNL Customer Journey Analytics] 作為 [!DNL Target] 的報告來源，您與貴公司皆必須擁有 [!DNL Customer Journey Analytics] 和 [!DNL Target] 的存取權。 如果您需要存取任一解決方案，請聯絡貴組織的管理員或帳戶代表。
* 建立 [!DNL Target] 活動 [!DNL Customer Journey Analytics] 報告，您必須擁有&quot;[!UICONTROL 核准者]&quot;或&#39;[!UICONTROL 編輯者]「」角色位於 [!DNL Target].
   * 如果您擁有 [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) 帳戶，請參閱 [指定角色和許可權](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) 在 *使用者*.
   * 如果您擁有 [Target Premium](/help/main/c-intro/intro.md#premium) 帳戶，請參閱 [角色和許可權](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) 在 *企業使用者許可權*.

* 根據您的設定，可依活動或組織層級變更報告。 另請參閱 [Reporting Cloud解決方案](/help/main/administrating-target/reporting.md#solution) 在 *在Target中設定報告*.
* 使用某個報告來源或其他報告來源。 您無法將單一活動的資料收集到多個報表來源。
* 當您設定 [!DNL Customer Journey Analytics] 作為您的報告來源，系統會提示您指定報告的沙箱。 在設定期間，您只會看到您有權存取的沙箱。
* 任何現有 [!DNL Target] 活動繼續使用 [!DNL Target] 和不受啟用CJA4T的影響。
* CJA4T僅在您有 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html){target=_blank} and [!DNL Target] implemented through the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}. 未來預計將會支援Analytics Data Connector。
* 有關時間的任何問題，請參閱 [延遲的考量事項](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#latency){target=_blank} 在 *常見問題* 在 *Adobe Customer Analytics指南*.

## 支援的活動類型

使用時，支援下列活動型別 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} or [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank}：

| 活動類型 | CJA4T相容？ |
|--- |--- |
| [使用手動流量分割的 A/B 活動](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |
| [使用自動分配的 A/B 活動](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 否 |
| [使用自動鎖定目標的 A/B 活動](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 否 |
| [體驗鎖定 (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | 是 |
| [多變數測試 (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | 是 |
| [Automated Personalization (AP) 活動](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | 否 |
| [Recommendations 活動](/help/main/c-recommendations/recommendations.md) | 是 |

## 建立使用下列專案的活動： [!DNL Customer Journey Analytics] 作為報表來源

建立 [!DNL Target] 使用的活動 [!DNL Customer Journey Analytics] 由於報表來源類似於設定一般 [!DNL Target] 活動。

1. 從 **[!UICONTROL 活動]** 清單，按一下 **[!UICONTROL 建立活動]**，然後選取活動型別（根據上方支援的活動圖表）並開始設定活動。
1. 當您前往 **[!UICONTROL 目標與設定]** 三部分活動建立工作流程的頁面，選取 **[!DNL Customer Journey Analytics]** 作為報表來源。

   ![Customer Journey Analytics作為報表來源選項](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >在之後無法變更報表來源 [!DNL Target] 活動上線。

1. 選取沙箱.

   在此下拉式清單中，您只能看見您有權存取的沙箱。 如果清單中遺失一或多個您有存取權的沙箱，請確認您有沙箱的存取權。 連絡人 [客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 如果您持續看到問題。

   ![選取沙箱選項](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. 指定活動目標。

   您必須選取成功量度，以用作每個活動的目標。 您可以選擇 [!DNL Target] 轉換量度或使用 [!DNL Customer Journey Analytics] 量度。

   ![使用「目標量度」下的「Customer Journey Analytics」量度選項](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. 按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

## 設定 [!DNL Customer Journey Analytics] 連線

之後 [!DNL Target] 活動已建立，您必須在中建立連線 [!DNL Customer Journey Analytics]. 如果您已設定連線，則可以使用現有的連線，並跳至下面的步驟4。 連線允許 [!DNL Customer Journey Analytics] 以開始從資料集中提取資料以供報告。

1. 在 [!DNL Customer Journey Analytics]，位於 **[!UICONTROL 連線]** 頁面，按一下 **[!UICONTROL 建立新連線]**.

   ![在Customer Journey Analytics中建立新的連線連結](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. 設定您的 [連線和資料設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html){target=_blank} 含正確資訊。
1. 新增您在設定資料流時使用的事件資料集。
1. 新增 **[!UICONTROL Adobe Target分類事件]** 查詢資料集，然後按一下 **[!UICONTROL 下一個]**.

   ![以Customer Journey Analytics新增資料集對話方塊](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. 設定您的事件資料集。

   如需詳細資訊，請參閱 [新增和設定資料集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#add-dataset){target=_blank} 在 *建立連線* 在 *Adobe Customer Journey Analytics指南*.

1. 將查詢資料集的「索引鍵」欄位設為「key」，並將「相符索引鍵」欄位設為，路徑如下：

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics中的Adobe Target分類事件對話方塊](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. 按一下 **[!UICONTROL 新增資料集]**，然後按一下 **[!UICONTROL 儲存]** 在下一個畫面中完成連線。

## 設定資料檢視

在中設定資料檢視 [!DNL Customer Journey Analytics]. 資料檢視可確保來自您連線的資料得到正確使用。

1. 設定您的資料檢視，並確保檢視會指向您在上面建立的連線。

   如需詳細資訊，請參閱 [建立或編輯資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html){target=_blank} 在 *Adobe Customer Journey Analytics指南*.

1. 若要正確檢視您的 [!DNL Target] 資料輸入 [!DNL Customer Journey Analytics]，您必須從查詢資料集中新增下列欄位作為維度：

   * 體驗名稱
   * 體驗 ID
   * 活動名稱
   * 活動 ID

   ![Customer Journey Analytics中的名稱和ID選項](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. 完成設定任何其他欄位，然後按一下 **[!UICONTROL 儲存並繼續]** 完成時。

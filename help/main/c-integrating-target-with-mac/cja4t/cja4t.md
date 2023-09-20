---
keywords: cja4t；Customer Journey Analytics；Customer Journey Analytics for Target；Customer Journey Analytics 報告來源；Customer Journey Analytics 作為 Target 的報告來源
description: 使用 [!DNL Adobe Customer Journey Analytics] for [!DNL Target] (A4T) 可根據 [!DNL Customer Journey Analytics] 轉換量度和受眾區段建立活動，並使用 [!DNL Customer Journey Analytics] 報告來檢查結果。
title: 什麼是 [!DNL Adobe Customer Journey Analytics] for [!DNL Target] (CJA4T)？
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 1e130d616c7042b61a12594eb1d9d57970d6a409
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 95%

---

# [!DNL Adobe Customer Journey Analytics] 作為 [!DNL Adobe Target] (CJA4T) 的報告來源

[Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html){target=_blank} 與 [!DNL Target] 之間的 [!DNL Customer Journey Analytics for Target] (CJA4T) 整合，為您的最佳化程式提供強大的分析與省時的工具。

在 [!DNL Target] 中使用 [!DNL Customer Journey Analytics] 資料的主要優點如下：

* 市場行銷人員可隨時動態地將 [!DNL Customer Journey Analytics] 成功量度套用至 [!DNL Target] 活動報告。執行活動之前完全不需要指定。
* 單一資料來源可盡量減少在兩個不同系統中收集資料時發生不一致的情況。

## 考量事項

使用 CJA4T 整合之前請考量以下資訊：

* 若要使用 [!DNL Customer Journey Analytics] 作為 [!DNL Target] 的報告來源，您與貴公司皆必須擁有 [!DNL Customer Journey Analytics] 和 [!DNL Target] 的存取權。如果您需要任一解決方案的存取權，請聯繫您組織的管理員或您的帳戶代表。
* 要使用 [!DNL Customer Journey Analytics] 報告建立 [!DNL Target] 活動，您必須在 [!DNL Target] 中具有「[!UICONTROL 核准者]」或「[!UICONTROL 編輯者]」的角色。
   * 如果您擁有 [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) 的帳戶，請參閱&#x200B;*使用者*&#x200B;中的[指定其角色和權限](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。
   * 如果您擁有 [Target Premium](/help/main/c-intro/intro.md#premium) 的帳戶，請參閱&#x200B;*企業使用者權限*&#x200B;中的[角色與權限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions)。

* 您必須是中角色的一部分 [!DNL Adobe Experience Platform] 以設定 [!DNL Target] 活動 [!DNL Customer Journey Analytics] 作為報表來源。 如需詳細資訊，請參閱 [在中新增角色 [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions.html){target=_blank} 在 *設定許可權* 在 *資料架構師與工程師教學課程。*
* 根據您的設定，可以依據活動或組織層級來變更報告。請參閱&#x200B;*在 Target 中設定報告*&#x200B;中的 [Reporting Cloud 解決方案](/help/main/administrating-target/reporting.md#solution)。
* 使用某個報告來源或其他報告來源。您無法收集單一活動的資料至多個報告來源。
* 當您設定 [!DNL Customer Journey Analytics] 作為報告來源時，系統會提示您指定用於報告的沙箱。設定時，您只會看到您擁有存取權的沙箱。
* 任何現有 [!DNL Target] 活動都會繼續使用 [!DNL Target] 資料收集，不會因為啟用 CJA4T 而受到影響。
* 您需要擁有 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html){target=_blank} and [!DNL Target] implemented through the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} 才可以使用 CJA4T。未來預計會支援 [!DNL Analytics Data Connector]。
* 任何關於時程的問題，請參閱 *Adobe Customer Analytics 指南*&#x200B;中&#x200B;*常見問題*&#x200B;的[延遲的注意事項](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#latency){target=_blank}。

## 支援的活動類型 {#supported-activities}

使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} JavaScript 程式庫時，可支援以下活動類型：

| 活動類型 | 是否與 CJA4T 相容？ |
|--- |--- |
| [使用手動流量分割的 A/B 活動](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |
| [使用自動分配的 A/B 活動](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 否 |
| [使用自動鎖定目標的 A/B 活動](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 否 |
| [體驗鎖定 (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | 是 |
| [多變數測試 (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | 是 |
| [Automated Personalization (AP) 活動](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | 否 |
| [Recommendations 活動](/help/main/c-recommendations/recommendations.md) | 是 |

## 建立使用 [!DNL Customer Journey Analytics] 作為報告來源的活動

建立使用 [!DNL Customer Journey Analytics] 作為報告來源的 [!DNL Target] 活動與設定一般的 [!DNL Target] 活動類似。

1. 從「**[!UICONTROL 活動]**」清單，按一下「**[!UICONTROL 建立活動]**」，接著選取活動類型 (根據[上方支援的活動圖表](#supported-activities)) 並開始設定活動。
1. 在三個部分活動建立工作流程中，當您進入「**[!UICONTROL 目標與設定]**」頁面後，請選取 **[!DNL Customer Journey Analytics]** 作為報告來源。

   ![Customer Journey Analytics 作為報告來源的選項](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >[!DNL Target] 活動上線後，報告來源無法再變更。

1. 選取沙箱。

   在此下拉式清單中，您只能看到您擁有存取權的沙箱。如果清單中缺少一個或多個您擁有存取權的沙箱，請驗證您是否擁有該沙箱的存取權。如果您持續遇到問題，請聯絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

   ![選取沙箱的選項](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. 指定活動目標。

   為各項活動選取一個成功量度作為目標。您可以選擇其中一項 [!DNL Target] 轉換量度或使用 [!DNL Customer Journey Analytics] 量度。

   ![使用目標量度下的 Customer Journey Analytics metric 選項](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. 按一下「**[!UICONTROL 儲存並關閉]**」。

## 設定 [!DNL Customer Journey Analytics] 連線

在建立一個 [!DNL Target] 活動後，您必須在 [!DNL Customer Journey Analytics] 中建立連線。如果您已設定過連線，您可以使用現有的連線並跳到下方的步驟 4。連線以後，[!DNL Customer Journey Analytics] 就可以開始從資料集中提取資料，以用於報告。

1. 在 [!DNL Customer Journey Analytics] 中的「**[!UICONTROL 連線]**」頁面，按一下「**[!UICONTROL 建立新連線]**」。

   ![在 Customer Journey Analytics 中建立新連線連結](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. 使用正確的資訊設定您的[連線和資料設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html){target=_blank}。
1. 設定資料流時，新增您使用過的事件資料集。
1. 新增「**[!UICONTROL Adobe Target 分類事件]**」查詢資料集，然後按一下「**[!UICONTROL 下一步]**」。

   ![Customer Journey Analytics 中的「新增資料集」對話框](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. 設定您的事件資料集。

   如需詳細資訊，請參閱 *Adobe Customer Journey Analytics 指南*&#x200B;中&#x200B;*建立連線*&#x200B;的[新增及設定資料集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant#add-dataset){target=_blank}。

1. 使用「[!UICONTROL 索引鍵]」欄位作為「索引」來設定您的查詢資料集，且「對應索引鍵欄位」含有以下路徑：

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics 中的「Adobe Target 分類事件」對話框](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. 按一下「**[!UICONTROL 新增資料集]**」，接著在下一個畫面按一下「**[!UICONTROL 儲存]**」以完成連線。

## 設定資料檢視

在 [!DNL Customer Journey Analytics] 中設定資料檢視資料檢視可確保連線中的資料可以正確使用。

1. 設定資料檢視，並確認其指向到您上方所建立的連線。

   如需詳細資訊，請參閱 *Adobe Customer Journey Analytics 指南*&#x200B;中的[建立或編輯資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html){target=_blank}。

1. 為了正確檢視您在 [!DNL Customer Journey Analytics] 中的 [!DNL Target] 資料，您必須從查詢資料集中新增以下欄位作為維度：

   * 體驗名稱
   * 體驗 ID
   * 活動名稱
   * 活動 ID

   ![Customer Journey Analytics 中的名稱和 ID 選項](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. 完成任何其他欄位的設定，完成後按一下「**[!UICONTROL 儲存並繼續]**」。

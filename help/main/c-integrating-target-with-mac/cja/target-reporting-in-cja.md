---
keywords: customer journey analytics；customer journey analytics for target；customer journey analytics報告來源；customer journey analytics作為target的報告來源；cja中的目標報告；Customer Journey Analytics中的目標報告
description: 在 [!DNL Target] 中使用 [!DNL Adobe Customer Journey Analytics] 報告功能建立以 [!DNL Customer Journey Analytics] 轉換量度和對象區段為基礎的活動，並使用 [!DNL Customer Journey Analytics] 報告功能來檢查結果。
title: 什麼是 [!DNL Target] 中的 [!DNL Adobe Customer Journey Analytics]報告？
feature: Integrations
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 05a4358e0115d7bfd13ec715a0e7eb96f1f2265b
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 40%

---

# 在[!DNL Target]中進行[!DNL Adobe Customer Journey Analytics]報告

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank}與[!DNL Target]之間的整合為您的最佳化程式提供強大的分析與省時的工具。

使用 [!DNL Customer Journey Analytics] 作為 [!DNL Target] 的報告來源的主要優點如下：

* 市場行銷人員可隨時動態地將 [!DNL Customer Journey Analytics] 成功量度套用至 [!DNL Target] 活動報告。執行活動之前完全不需要指定。
* 行銷人員可利用[!DNL Customer Journey Analytics]功能（例如[Experimentation面板](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}）來進一步分析其網站個人化。
* 行銷人員可以有[!DNL Adobe Journey Optimizer]和[!DNL Target]的單一報表來源。 兩種個人化產品都可以連接到 [!DNL Customer Journey Analytics] 以更全面地了解您的網頁個人化。

## 考量事項

使用[!DNL Customer Journey Analytics]與[!DNL Target]整合前，請先考慮下列資訊：

>[!IMPORTANT]
>
>此整合與[[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)不同。 實作和支援的活動型別不同。 請確定您閱讀完整本文，然後再將此整合用於您的[!DNL Target]活動。

* 若要使用 [!DNL Customer Journey Analytics] 作為 [!DNL Target] 的報告來源，您與貴公司皆必須擁有 [!DNL Customer Journey Analytics] 和 [!DNL Target] 的存取權。如果您需要任一解決方案的存取權，請聯繫您組織的管理員或您的帳戶代表。
* 若要建立具有[!DNL Target]報告的[!DNL Customer Journey Analytics]活動，您必須在[!UICONTROL Approver]中擁有&quot;[!UICONTROL Editor]&quot;或&quot;[!DNL Target]&quot;角色。
   * 如果您擁有 [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) 的帳戶，請參閱&#x200B;*使用者*&#x200B;中的[指定其角色和權限](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。
   * 如果您擁有 [Target Premium](/help/main/c-intro/intro.md#premium) 的帳戶，請參閱&#x200B;*企業使用者權限*&#x200B;中的[角色與權限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions)。

* 成為[!DNL Adobe Experience Platform]中角色的一部分，以設定以[!DNL Target]作為報告來源的[!DNL Customer Journey Analytics]活動。 如需詳細資訊，請參閱[資料架構師和工程師教學課程中 [!DNL Adobe Experience Platform]設定許可權](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank}的&#x200B;*在**中新增角色。*
* 根據您的設定，可以依據活動或組織層級來變更報告。請參閱&#x200B;*在 Target 中設定報告*&#x200B;中的 [Reporting Cloud 解決方案](/help/main/administrating-target/reporting.md#solution)。
* 使用某個報告來源或其他報告來源。您無法收集單一活動的資料至多個報告來源。
* 當您設定 [!DNL Customer Journey Analytics] 作為報告來源時，系統會提示您指定用於報告的沙箱。設定時，您只會看到您擁有存取權的沙箱。
* 任何現有的[!DNL Target]活動會繼續使用[!DNL Target]資料集合，且不受啟用此整合的影響。
* 若要使用此整合，慣用的實作方法是透過[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/experience-platform){target=_blank}實作[!DNL Target][[!DNL Adobe Experience Platform Web SDK]和](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}。

  如果您目前尚未實作[!DNL Adobe Experience Platform Web SDK]，您也可以建立[[!DNL Adobe Analytics] 來源連線](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)以將資料匯入[!DNL Adobe Experience Platform]。 如果您計畫使用此方法，則必須選取與[!DNL Analytics]搭配使用的[!DNL Adobe Experience Platform]沙箱旁的[!DNL Customer Journey Analytics]報告套裝。

  ![報告設定對話方塊中的沙箱選項](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >如果您使用[!DNL Adobe Analytics]來源連線，[!DNL Adobe Analytics]和[!DNL Customer Journey Analytics]中都有報告。 不過，由於這兩個解決方案之間的演演算法不同，結果不太可能相符。

* 如需關於時間的任何問題，請參閱[指南](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank}中&#x200B;*常見問題*&#x200B;的&#x200B;*[!DNL Adobe Customer Analytics]延遲考量事項*。

## 支援的活動類型 {#supported-activities}

使用[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}或[at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank} JavaScript資料庫時，支援下列活動型別：

| 活動類型 | 支援? |
|--- |--- |
| [使用手動流量分割的 A/B 活動](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |
| [使用自動分配的 A/B 活動](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 否 |
| [使用自動鎖定目標的 A/B 活動](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 否 |
| [體驗鎖定 (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | 是 |
| [多變數測試 (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | 是 |
| [Automated Personalization (AP) 活動](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | 否 |
| [推薦活動](/help/main/c-recommendations/recommendations.md) | 是 |

## 建立使用 [!DNL Customer Journey Analytics] 作為報告來源的活動

建立使用 [!DNL Customer Journey Analytics] 作為報告來源的 [!DNL Target] 活動與設定一般的 [!DNL Target] 活動類似。

>[!TIP]
>
>您也可以指定[!DNL Target]在[!DNL Customer Journey Analytics]中對您帳戶中建立的所有活動(**[!UICONTROL Administration]** > **[!UICONTROL Reporting]** > **[!UICONTROL Reporting Experience Cloud Solution]**)使用報告。 如需詳細資訊，請參閱&#x200B;*在*&#x200B;中設定報告[報告雲端解決方案 [!DNL Target]](/help/main/administrating-target/reporting.md#solution)。

1. 從&#x200B;**[!UICONTROL Activities]**&#x200B;清單中，按一下&#x200B;**[!UICONTROL Create Activity]**，然後選取活動型別（根據上方[支援的活動圖表](#supported-activities)）並開始設定活動。
1. 當您進入三部分活動建立工作流程的&#x200B;**[!UICONTROL Goals & Settings]**&#x200B;頁面時，請選取&#x200B;**[!DNL Customer Journey Analytics]**&#x200B;作為報告來源。

   ![Customer Journey Analytics 作為報告來源的選項](/help/main/c-integrating-target-with-mac/cja/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >[!DNL Target] 活動上線後，報告來源無法再變更。

1. 選取沙箱。

   在此下拉式清單中，您只會看到您有權存取的沙箱。 如果清單中缺少一個或多個您擁有存取權的沙箱，請驗證您是否擁有該沙箱的存取權。如果您持續遇到問題，請聯絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

   ![選取沙箱的選項](/help/main/c-integrating-target-with-mac/cja/assets/sandbox.png)

1. 指定活動目標。

   為各項活動選取一個成功量度作為目標。您可以選擇其中一項 [!DNL Target] 轉換量度或使用 [!DNL Customer Journey Analytics] 量度。

   ![使用目標量度下的 Customer Journey Analytics metric 選項](/help/main/c-integrating-target-with-mac/cja/assets/goal-metric.png)

1. 按一下 **[!UICONTROL Save & Close]**。

## 設定 [!DNL Customer Journey Analytics] 連線

在建立一個 [!DNL Target] 活動後，您必須在 [!DNL Customer Journey Analytics] 中建立連線。如果您已設定過連線，您可以使用現有的連線並跳到下方的步驟 4。連線以後，[!DNL Customer Journey Analytics] 就可以開始從資料集中提取資料，以用於報告。

1. 在[!DNL Customer Journey Analytics]的&#x200B;**[!UICONTROL Connections]**&#x200B;頁面上，按一下&#x200B;**[!UICONTROL Create a new connection]**。

   ![在[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png)中建立新的連線連結

1. 使用正確的資訊設定您的[連線與資料設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview){target=_blank}。
1. 設定資料流時，新增您使用過的事件資料集。
1. 新增&#x200B;**[!UICONTROL Adobe Target Classification Events]**&#x200B;查詢資料集，然後按一下&#x200B;**[!UICONTROL Next]**。

   ![Customer Journey Analytics 中的「新增資料集」對話框](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. 設定您的事件資料集。

   如需詳細資訊，請參閱[指南](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank}中&#x200B;*建立連線*&#x200B;中的&#x200B;*[!DNL Adobe Customer Journey Analytics]新增並設定資料集*。

1. 使用[!UICONTROL Key]欄位設定您的查詢資料集，將其設為「key」，並使用[!UICONTROL Matching]索引鍵欄位設定為下列路徑：

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics 中的「Adobe Target 分類事件」對話框](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. 按一下&#x200B;**[!UICONTROL Add datasets]**，然後在下一個畫面中按一下&#x200B;**[!UICONTROL Save]**&#x200B;以完成連線。

## 設定資料檢視

在 [!DNL Customer Journey Analytics] 中設定資料檢視資料檢視可確保連線中的資料可以正確使用。

1. 設定資料檢視，並確認其指向到您上方所建立的連線。

   如需詳細資訊，請參閱[指南](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank}中的&#x200B;*[!DNL Adobe Customer Journey Analytics]建立或編輯資料檢視*。

1. 為了正確檢視您在 [!DNL Customer Journey Analytics] 中的 [!DNL Target] 資料，您必須從查詢資料集中新增以下欄位作為維度：

   * [!UICONTROL Experience Name]
   * [!UICONTROL Experience ID]
   * [!UICONTROL Activity Name]
   * [!UICONTROL Activity ID]

   ![Customer Journey Analytics 中的名稱和 ID 選項](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. 若要在[!DNL Target]面板中使用[!UICONTROL Experimentation]維度，請設定下列內容標籤：

   * 對於[!UICONTROL Activity Name]，請使用「實驗中的實驗」。
   * [!UICONTROL Experience Name]，使用「實驗中的變體」。

   ![實驗面板中的內容標籤](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. 完成設定任何其他欄位，完成後按一下&#x200B;**[!UICONTROL Save and continue]**。

## 在[!DNL Customer Journey Analytics]中建立和檢視活動報告

完成設定後，請透過[!DNL Customer Journey Analytics]或活動在[!DNL Adobe Experience Cloud]中的[!UICONTROL Reports]索引標籤進行[!DNL Target]。

報告標籤有&#x200B;**[!UICONTROL View in Customer Journey Analytics]**&#x200B;連結。 目前，此連結會將您重新導向至[!DNL Customer Journey Analytics]首頁登陸頁面。

![CJA報告連結](/help/main/c-integrating-target-with-mac/cja/assets/report-link.png)

>[!NOTE]
>
>此整合與[!UICONTROL Adobe Analytics for Target] (A4T)不同。
>
>* [!DNL Target]/[!DNL Customer Journey Analytics]整合不包含預先建立的報表，例如A4T。 活動報告必須在[!DNL Customer Journey Analytics]中建置。
>
>* 如果選取[!UICONTROL Use a CJA Metric]作為活動的目標量度，則此選項可讓您靈活地決定何時必須定義特定的成功量度。 設定[!UICONTROL Experimentation]面板時會選取成功量度。 提升度和可信度是根據所選CJA量度來計算。

1. 在[!DNL Customer Journey Analytics]中，建立Experimentation面板，然後從&#x200B;**[!UICONTROL Experiment]**&#x200B;下拉式功能表中選取活動。

   如需詳細資訊，請參閱[指南中](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation?lang=en#use){target=_blank}實驗面板&#x200B;*下的*&#x200B;實驗面板&#x200B;*[!DNL Customer Journey Analytics]*。

   Customer Journey Analytics中的![實驗面板](/help/main/c-integrating-target-with-mac/cja/assets/experimentation-panel.png)

   >[!IMPORTANT]
   >
   >如果活動未出現在[!UICONTROL Experiment]下拉式清單中，請確認已選取正確的資料檢視，且[!DNL Target]維度包含必要的內容標籤（請參閱[設定資料檢視](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja#set-up-data-views){target=_blank}中的步驟3）。

1. 按一下 **[!UICONTROL Build]**。

   [!UICONTROL Experimentation]面板會傳回一組豐富的資料和視覺效果，協助您更清楚瞭解實驗的執行情況。 如需詳細資訊，請參閱[[!UICONTROL Panel output]指南中](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation#panel-output){target=_blank}實驗面板&#x200B;*下的**[!DNL Customer Journey Analytics]*。

   ![實驗中](/help/main/c-integrating-target-with-mac/cja/assets/experimentation.png)
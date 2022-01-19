---
keywords: 經驗；json;aem;adobe經驗管理器；導出到adobe目標；經驗片段；片段；XF
description: 瞭解如何使用 [!DNL Adobe Experience Manager] 體驗片段 [!DNL Adobe Target] 活動。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM)經驗碎片？
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: b4c64f3fbc266b86cfffa6e5526a074b76b8b6ee
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 22%

---

# AEM 體驗片段

使用在中建立的經驗片段 [!DNL Adobe Experience Manager] (AEM在) [!DNL Target] 幫助優化或個性化的活動。

>[!NOTE]
>
>此功能要求您是 [!DNL Adobe Experience Manager] (AEM)客戶。 有關詳細資訊，請參見 [要求](#section_AE6F0971E1574B3AA324003599B96E5A) 下。

使用在中建立的經驗片段 [!DNL AEM] 在 [!DNL Target] 活動可讓您將易用性和 [!DNL AEM] 具有強大的人工智慧和機器學習功能 [!DNL Target] test和個性化體驗。

[!DNL AEM] 將您的所有內容和資產集中在一個中央位置，以支援您的個人化策略。[!DNL AEM] 可讓您在一個位置中輕鬆地為桌上型電腦、平板電腦和行動裝置建立內容，不必撰寫程式碼。不需要為每個設備建立頁。 [!DNL AEM] 自動使用內容調整每個體驗。

[!DNL Target] 可讓您根據一組包含行為、情境和離線變數的規則型和 AI 驅動型機器學習方法，以大規模實現個人化體驗。與 [!DNL Target]，您可以輕鬆設定和運行 [A/BTest](/help/c-activities/t-test-ab/test-ab.md) 和 [多元](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT)活動，以確定最佳優惠、內容和體驗。

經驗片段代表了向前邁出的一大步，可將內容/經驗建立者和經理與優化和個性化專業人員聯繫起來，這些專業人員正在使用 [!DNL Target]。

## 要求 {#section_AE6F0971E1574B3AA324003599B96E5A}

您必須使用中的體驗片段功能進行預配 [!DNL Target]。 此外，您必須使用 [!DNL AEM] 6.3，包含相應的Service Pack或 [!DNL AEM] 6.4（或更高版本）。 您的客戶代表可協助確認您是否符合使用此功能的要求。

* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* [!DNL Adobe Experience Manager] 6.3 SP2（或更高版本）。
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帳戶。

聯繫人 [Adobe Target客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 啟用整合併提供驗證詳細資訊。

## 在中建立和配置體驗片段 [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

為了使用 [!DNL AEM] 體驗片段 [!DNL Target]，必須執行以下步驟：

### 步驟1:整合 [!DNL AEM] 與 [!DNL Target]

如需詳細資訊，請參閱:

* **Adobe I/O**: [使用AdobeI/0與Adobe Target整合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html) 的 _管理使用手冊_ 文檔。
* **[!DNL AEM]6.3**: [選擇Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) 的 _Adobe Experience Manager6.3_ 文檔。
* **[!DNL AEM]6.4**: [選擇Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) 的 _Adobe Experience Manager6.4_ 文檔。
* **[!DNL AEM]6.5**: [選擇Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en) 的 *Adobe Experience Manager6.5* 文檔。

### 步驟 2: 建立體驗片段

在中建立體驗片段 [!DNL AEM]。 如需詳細資訊，請參閱:

* **[!DNL AEM]6.3**: [體驗片段](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) 的 *Adobe Experience Manager6.3* 文檔。
* **[!DNL AEM]6.4**: [體驗片段](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=en) 的 *Adobe Experience Manager6.4* 文檔。
* **[!DNL AEM]6.5**: [體驗片段](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=en) 的 *Adobe Experience Manager6.5* 文檔。

### 第3步：配置 [!DNL AEM] 分享經驗片段 [!DNL Target]

1. 從 [!DNL AEM]，選擇所需的體驗片段或其包含的資料夾，然後按一下 **[!UICONTROL 屬性]**。
2. 按一下&#x200B;**[!UICONTROL 「雲端服務」]**&#x200B;標籤，然後從&#x200B;**[!UICONTROL 「雲端服務組態」]**&#x200B;下拉式清單中，選取 **[!UICONTROL Adobe Target]**。

   >[!NOTE]
   >
   >上一步假定組織中的某人已建立 [!DNL Adobe Target] 配置。

3. 按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

### 步驟 4: 發佈體驗片段並將其匯出至 [!DNL Target]

取決於您 [!DNL AEM] 版本，請參閱以下連結以瞭解逐步說明：

* **[!DNL AEM]6.3**: [將體驗片段導出到目標](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) 的 *Adobe Experience Manager6.3* 文檔。
* **[!DNL AEM]6.4**: [將體驗片段導出到目標](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html) 的 *Adobe Experience Manager6.4* 文檔。
* **[!DNL AEM]6.5**: [將體驗片段導出到目標](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en) 的 *Adobe Experience Manager6.5* 文檔。

## 在中使用經驗片段 [!DNL Target] 活動 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行上述任務後，體驗片段顯示在 [!UICONTROL 優惠] 頁面 [!DNL Target]。

>[!NOTE]
>
>* [!DNL Target] 目前每十分鐘會尋找要匯入的體驗片段。導入的經驗片段應在中提供 [!DNL Target] 10分鐘內，但這個時間段應該會縮短。
>
>* 將體驗片段導入 [!DNL Target] 作為HTML。 該體驗片段「主」版本仍保留在 [!DNL AEM]。 無法在中編輯體驗片段 [!DNL Target]。


您可以懸停在清單中的體驗片段上，然後按一下 [!UICONTROL 視圖] 表徵圖 ![「查看」表徵圖](assets/icon_info.png) 查看有關體驗片段的其他資訊，包括其公開發售交付URL及其 [!DNL AEM] 路徑。

您可以在 [!DNL Target] 使用 [視覺體驗作曲家](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)或 [基於表單的體驗作曲家](/help/c-experiences/form-experience-composer.md)。

>[!NOTE]
>
>要充分利用 [!DNL Target] AI和ML功能，您可以選擇 [自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) 或 [自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) 建立A/BTest。

**要使用VEC使用體驗片段，請執行以下操作：**

1. 在 [!DNL Target]，在建立或編輯體驗時 [視覺體驗作曲家](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)，按一下要插入的頁面上的位置 [!DNL AEM] 內容，然後選擇要顯示 [!UICONTROL 選擇體驗片段] 清單框。

   * [!UICONTROL 插入在前]
   * [!UICONTROL 插入在後]
   * [!UICONTROL 換用體驗片段]

   的 [!UICONTROL 體驗片段] 清單顯示在中建立的內容 [!DNL AEM] 現在可以從內部 [!DNL Target]。

   >[!NOTE]
   >
   >[!UICONTROL 「交換體驗片段」]選項不適用於影像。如果您想將此選項用於影像，請按一下包含所需影像的容器元素。

   ![](assets/experience_fragment_list.png)

1. 選擇所需的體驗片段，然後按一下 **[!UICONTROL 完成]**。
1. 完成活動的設定。

   如需有關設定各種活動類型的詳細資訊，請參閱下列主題:

   * **A/B 測試:** [建立 A/B 測試](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動分配:** [自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動目標：** [自動目標](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):**[建立 Automated Personalization 活動](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **體驗鎖定目標 (XT):** [建立體驗鎖定目標活動](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多變數測試 (MVT):** [建立多變數測試](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **建議:** [建立建議活動](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**要使用基於表單的經驗編寫器來使用經驗片段，請執行以下操作：**

1. 在 [!DNL Target]，在建立或編輯體驗時 [基於表單的體驗作曲家](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)，在要插入的頁面上選擇位置 [!DNL AEM] 內容，然後選擇 **[!UICONTROL 更改體驗片段]** 顯示 [!UICONTROL 選擇體驗片段] 清單框。

   ![](assets/experience_fragment_list.png)

   的 [!UICONTROL 體驗片段] 清單顯示在中建立的內容 [!DNL AEM] 現在可以從內部 [!DNL Target]。

1. 選取需要的體驗片段，然後按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 完成活動的設定。

## 考量事項 {#considerations}

* [!DNL Target] 目前每十分鐘會尋找要匯入的體驗片段。導入的經驗片段應在中提供 [!DNL Target] 10分鐘內，但這個時間段應該會縮短。
* 將體驗片段導入 [!DNL Target] 作為HTML。 體驗片段「主」版本仍在 [!DNL AEM]。 無法在中編輯體驗片段 [!DNL Target]。
* 無法使用 [!DNL Adobe I/O]。 如上所述，使AEM用建立體驗片段。

## 培訓視頻：使用AEM經驗片段 [!DNL Adobe Target]

以下視頻顯示了如何設定和使用體驗片段：

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>的 [!DNL AEM] 4時54分討論的deeplink功能已刪除。

有關詳細資訊，請參見 [使用經驗片段與Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) 的 *AEM Sites視頻和Tutorials* 的子菜單。

---
description: 在 Target 活動中使用在 Adobe Experience Manager (AEM) 中建立的體驗片段，以輔助最佳化或個人化的相關資訊。
keywords: 體驗；json；aem；adobe experience manager；匯出至adobe目標；體驗片段；片段；XF
seo-description: 使用Adobe Experience Manager中建立的體驗片段(AEM)在Adobe Target活動中建立的體驗片段，以協助最佳化或個人化。
seo-title: Adobe Target中的Adobe Experience Manager(AEM)體驗片段
solution: Target
title: AEM 體驗片段
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# AEM 體驗片段{#aem-experience-fragments}

Information about using experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization.

>[!NOTE]
>
>This feature requires that you are an [!DNL Adobe Experience Manager] (AEM) customer. 如需詳細資訊，請參閱以下的[需求](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)。

## 概述 {#section_95A91830530F493B81C5C9CDB9B783EA}

Using experience fragments created in AEM in [!DNL Target] activities lets you combine the ease-of-use and power of AEM with powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in [!DNL Target] to test and personalize experiences at scale.

AEM 將您的所有內容和資產集中在一個中央位置，以支援您的個人化策略。AEM 可讓您在一個位置中輕鬆地為桌上型電腦、平板電腦和行動裝置建立內容，不必撰寫程式碼。無需為每個裝置建立頁面。AEM會自動使用您的內容調整每個體驗。

[!DNL Target] 可讓您根據一組包含行為、情境和離線變數的規則型和 AI 驅動型機器學習方法，以大規模實現個人化體驗。With [!DNL Target] you can easily set up and run [A/B Test](/help/c-activities/t-test-ab/test-ab.md) and [Multivariate](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) activities to determine the best offers, content, and experiences.

Experience fragments represent a huge step forward to link the content/experience creators and managers to the optimization and personalization professionals who are driving business outcomes using [!DNL Target].

## 要求 {#section_AE6F0971E1574B3AA324003599B96E5A}

You must be provisioned with the experience fragments functionality within [!DNl Target]. 此外，您必須使用 AEM 6.3 版搭配對應的 Service Pack，或 6.4 版 (或更新版本)。您的客戶代表可協助確認您是否符合使用此功能的要求。

* Adobe Experience Manager 6.4 (或更新版本)。
* Adobe Experience Manager 6.3 SP2 (或更新版本)。
* Adobe Target Standard 或 Adobe Target Premium 帳戶。
* Contact [Adobe Target Customer Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to enable the integration and to provide you with authentication details.

## 在 AEM 中建立和設定體驗片段 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

In order to use AEM experience fragments in [!DNL Target], you must perform the following steps:

### 步驟 1: 整合 AEM 與 Target

如需詳細資訊，請參閱:

* **AEM6.3**： [在Adobe Experience](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) _Manager6.3_ 文件中選擇加入Adobe Analytics和Adobe Target。
* **AEM6.4**： [在Adobe Experience](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) _Manager6.4_ 文件中選擇加入Adobe Analytics和Adobe Target。
* **AEM6.5**： [在Adobe Experience](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) *Manager6.5* 文件中選擇加入Adobe Analytics和Adobe Target。

### 步驟 2: 建立體驗片段

體驗片段是在 AEM 中建立。如需詳細資訊，請參閱:

* **AEM6.3**： [Adobe Experience](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) *Manager6.3* 文件中的體驗片段。
* **AEM6.4**： [Adobe Experience](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) *Manager6.4* 文件中的體驗片段。
* **AEM6.5**： [Adobe Experience](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) *Manager6.5* 文件中的體驗片段。

### 步驟 3: 設定 AEM 讓 Target 共用體驗片段

1. From within AEM, select the desired experience fragment or its containing folder, then click **[!UICONTROL Properties]**.
2. Click the **[!UICONTROL Cloud Services]** tab, then from the **[!UICONTROL Cloud Service Configuration]** drop-down list, select **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >The previous step assumes that someone in your organization has created the [!DNL Adobe Target] configuration.

3. 按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

### 步驟 4: 發佈體驗片段並將其匯出至 Target

視您的AEM版本而定，請參閱下列連結以取得逐步指示：

* **AEM6.3**： [將Experience片段匯出至Adobe](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) Experience *Manager6.3* 文件中的Target。
* **AEM6.4**： [將Experience片段匯出至Adobe](https://docs.adobe.com/content/help/en/experience-manager-64/administering/integration/experience-fragments-target.html) Experience *Manager6.4* 文件中的Target。
* **AEM6.5**： [將Experience片段匯出至Adobe](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) Experience *Manager6.5* 文件中的Target。

## 在 Target 活動中使用體驗片段 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行先前的工作之後，體驗片段會顯示在 Target 的[!UICONTROL 「選件」]頁面中。

>[!NOTE]
>
>[!DNL Target] 目前每十分鐘會尋找要匯入的體驗片段。The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.

>[!IMPORTANT]
>
>The experience fragment is currently imported into [!DNL Target] as an HTML offer. 請注意，體驗片段「主要」版本會保留在 AEM 中。您無法在 Target 中編輯體驗片段。

You can hover over an experience fragment in the list, then click the View icon ![View icon](assets/icon_info.png) to see additional information about the experience fragment, including its public offer delivery URL, its AEM path, and a deep link to open the experience fragment inside of AEM.

You can consume Experience Fragments in [!DNL Target] activities using the [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) or the [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>To fully utilize the [!DNL Target] AI and ML functionality, you can select [Auto-Allocate](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) or [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) while creating an A/B Test.

**使用 VEC 來取用體驗片段:**

1. 在 [!DNL Target]「 [Visual Experience Composer](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)」中建立或編輯體驗時，按一下您要插入AEM內容的頁面上的位置，然後選取所要的選項以顯示 [!UICONTROL 「選擇體驗片段] 」清單。

   * [!UICONTROL 插入在前]
   * [!UICONTROL 插入在後]
   * [!UICONTROL 使用體驗片段交換]
   [!UICONTROL 「體驗片段] 」清單會顯示在AEM中建立的所有內容，現在可從內部 [!DNL Target]取得。

   >[!NOTE]
   >
   >[!UICONTROL 「交換體驗片段」]選項不適用於影像。如果您想將此選項用於影像，請按一下包含所需影像的容器元素。

   ![](assets/experience_fragment_list.png)

1. Select the desired experience fragment, then click **[!UICONTROL Done]**.
1. 完成活動的設定。

   如需有關設定各種活動類型的詳細資訊，請參閱下列主題:

   * **A/B 測試:** [建立 A/B 測試](../../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
   * **自動分配:** [自動分配](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動鎖定目標** [針對個人化體驗自動鎖定目標](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)
   * **Automated Personalization (AP):**[建立 Automated Personalization 活動](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **體驗鎖定目標 (XT):** [建立體驗鎖定目標活動](../../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多變數測試 (MVT):** [建立多變數測試](../../c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **建議:** [建立建議活動](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**使用表單式體驗撰寫器來取用體驗片段:**

1. 在 [!DN「表單型]體驗撰寫器 [](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)」中建立或編輯體驗時，選取您要插入AEM內容的頁面上的位置，然後選取 **[!UICONTROL 「變更體驗片段]** 」以顯示 [!UICONTROL 「選擇體驗片段] 」清單。

   ![](assets/experience_fragment_list.png)

   [!UICONTROL 「體驗片段] 」清單會顯示在AEM中建立的所有內容，現在可從內部 [!DNL Target]取得。

1. 選取需要的體驗片段，然後按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 完成活動的設定。

## 考量事項 {#considerations}

* [!DNL Target] 目前每十分鐘會尋找要匯入的體驗片段。The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.
* The experience fragment is currently imported into [!DNL Target] as an HTML offer. 請注意，體驗片段「主要」版本會保留在 AEM 中。You cannot edit the experience fragment in [!DNL Target].
* 您可以將JSON選件匯入為體驗片段 [!DNL Target]。不過，這些選件會匯入為HTML選件。[!DNL Target] UI目前並不完全支援JSON選件(體驗片段)。

## 訓練影片: 將 AEM 體驗片段用於 Adobe Target {#section_C0EDC54063464F41A182492D2045BC64}

下列影片會示範如何設定並使用體驗片段: [搭配 Adobe Target 使用 AEM 體驗片段](https://helpx.adobe.com/experience-manager/kt/sites/using/experience-fragment-target-feature-video-use.html)。

---
keywords: 體驗； JSON; AEM;Adobe Experience Manager；匯出至Adobe Target；體驗片段；片段； XF
description: 了解如何使用 [!DNL Adobe Experience Manager] 體驗片段 [!DNL Adobe Target] 活動。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM)體驗片段？
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 18%

---

# AEM 體驗片段

使用中建立的體驗片段 [!DNL Adobe Experience Manager] (AEM) [!DNL Target] 活動來協助最佳化或個人化。

>[!NOTE]
>
>此功能需要您 [!DNL Adobe Experience Manager] (AEM)客戶。 如需詳細資訊，請參閱 [需求](#section_AE6F0971E1574B3AA324003599B96E5A) 下方。

使用中建立的體驗片段 [!DNL AEM] in [!DNL Target] 活動可讓您結合的易用性和強大功能 [!DNL AEM] 在 [!DNL Target] 大規模測試並個人化體驗。

[!DNL AEM] 將您的所有內容和資產集中在一個中央位置，以支援您的個人化策略。[!DNL AEM] 可讓您在一個位置中輕鬆地為桌上型電腦、平板電腦和行動裝置建立內容，不必撰寫程式碼。不需要為每個裝置建立頁面。 [!DNL AEM] 會使用您的內容自動調整每個體驗。

[!DNL Target] 可讓您根據一組包含行為、情境和離線變數的規則型和 AI 驅動型機器學習方法，以大規模實現個人化體驗。使用 [!DNL Target]，您可以輕鬆設定和執行 [A/B測試](/help/main/c-activities/t-test-ab/test-ab.md) 和 [多變數](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT)活動，以決定最佳選件、內容和體驗。

體驗片段代表將內容/體驗建立者和經理連結至最佳化和個人化專業人員的一大步，這些專業人員正使用 [!DNL Target].

## 要求 {#section_AE6F0971E1574B3AA324003599B96E5A}

您必須布建內的體驗片段功能 [!DNL Target]. 此外，您必須使用 [!DNL AEM] as a Cloud Service或 [!DNL AEM] 6.4（或更新版本）。 您的客戶代表可協助確認您是否符合使用此功能的要求。

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5。
* [!DNL Adobe Experience Manager] 6.4。
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帳戶。

>[!NOTE]
>
>[!DNL Adobe Experience Manager] 6.3和6.4已結束生命週期，不再提供支援（購買延長支援的客戶除外）。

連絡人 [Adobe Target客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 啟用整合併提供驗證詳細資料。

## 在中建立和設定體驗片段 [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

為了使用 [!DNL AEM] 體驗片段 [!DNL Target]，您必須執行下列步驟：

### 步驟1:整合 [!DNL AEM] with [!DNL Target]

如需詳細資訊，請參閱：

* **AEMas a Cloud Service**: [與Adobe Target整合](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank}，位於 *Experience Manageras a Cloud Service* 指南。
* **Adobe I/O**: [使用Adobe Target I/0與Adobe整合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html){target=_blank}，位於 *管理使用手冊* 檔案。
* **[!DNL AEM]6.5**: [選擇使用Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en){target=_blank}，位於 *Adobe Experience Manager 6.5* 檔案。
* **[!DNL AEM]6.4**: [選擇使用Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank}，位於 *Adobe Experience Manager 6.4* 檔案。

### 步驟 2: 建立體驗片段

體驗片段是在中建立 [!DNL AEM]. 如需詳細資訊，請參閱：

* **AEMas a Cloud Service**: [體驗片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank}，位於 *Experience Manageras a Cloud Service* 指南。
* **[!DNL AEM]6.5**: [體驗片段](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=en){target=_blank}，位於 *Adobe Experience Manager 6.5* 檔案。
* **[!DNL AEM]6.4**: [體驗片段](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=en){target=_blank}，位於 *Adobe Experience Manager 6.4* 檔案。

### 步驟3:設定 [!DNL AEM] 要與共用體驗片段 [!DNL Target]

1. 從內 [!DNL AEM]，選取所需的體驗片段或其容納資料夾，然後按一下 **[!UICONTROL 屬性]**.
2. 按一下&#x200B;**[!UICONTROL 「雲端服務」]**&#x200B;標籤，然後從&#x200B;**[!UICONTROL 「雲端服務組態」]**&#x200B;下拉式清單中，選取 **[!UICONTROL Adobe Target]**。

   >[!NOTE]
   >
   >上一步假設組織中的某人已建立 [!DNL Adobe Target] 設定。

3. 按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

### 步驟 4: 發佈體驗片段並將其匯出至 [!DNL Target]

視您的 [!DNL AEM] 版本，請參閱下列連結以取得逐步指示：

* **AEMas a Cloud Service**: [將體驗片段匯出至Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank}，位於 *Experience Manageras a Cloud Service* 指南。
* **[!DNL AEM]6.5**: [將體驗片段匯出至Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank}，位於 *Adobe Experience Manager 6.5* 檔案。
* **[!DNL AEM]6.4**: [將體驗片段匯出至Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank}，位於 *Adobe Experience Manager 6.4* 檔案。

## 在中使用體驗片段 [!DNL Target] 活動 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行先前的工作後，體驗片段會顯示在 [!UICONTROL 選件] 頁面 [!DNL Target].

>[!NOTE]
>
>* [!DNL Target] 目前每十分鐘會尋找要匯入的體驗片段。匯入的體驗片段應可在 [!DNL Target] 10分鐘內，但此時間範圍會日後縮短。
>
>* 體驗片段會匯入至 [!DNL Target] 作為HTML或JSON選件。 體驗片段「主要」版本仍保留在 [!DNL AEM]. 您無法在中編輯體驗片段 [!DNL Target].


您可以暫留在清單中的體驗片段上，然後按一下 [!UICONTROL 檢視] 圖示 ![檢視圖示](assets/icon_info.png) 若要查看體驗片段的其他相關資訊，包括其公開選件傳送URL及其 [!DNL AEM] 路徑。

您可以在 [!DNL Target] 活動使用 [可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)或 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>若要充分使用 [!DNL Target] AI和ML功能，您可以選取 [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) 或 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 建立A/B測試時。
>
>不支援體驗片段 [!DNL Recommendations] 活動。 不過，若要將體驗片段用於建議，您可以建立 [!UICONTROL A/B測試] 活動(包括 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標])或 [!UICONTROL 體驗鎖定] (XT)活動和 [將建議納入選件](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

**若要使用VEC使用體驗片段：**

1. 在 [!DNL Target]，在中建立或編輯體驗時 [可視化體驗撰寫器](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)，按一下您要插入的頁面上的位置 [!DNL AEM] 內容，然後選取要顯示 [!UICONTROL 選擇體驗片段] 清單。

   * [!UICONTROL 插入在前]
   * [!UICONTROL 插入在後]
   * [!UICONTROL 交換體驗片段]

   此 [!UICONTROL 體驗片段] 清單顯示中建立的內容 [!DNL AEM] 現在可從內取得原生功能 [!DNL Target].

   >[!NOTE]
   >
   >[!UICONTROL 「交換體驗片段」]選項不適用於影像。如果您想將此選項用於影像，請按一下包含所需影像的容器元素。

   ![experience_fragment_list影像](assets/experience_fragment_list.png)

1. 選取所需的體驗片段，然後按一下 **[!UICONTROL 完成]**.
1. 完成活動的設定。

   如需有關設定各種活動類型的詳細資訊，請參閱下列主題:

   * **A/B 測試:** [建立 A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動分配:** [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動鎖定目標：** [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):**[建立 Automated Personalization 活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **體驗鎖定目標 (XT):** [建立體驗鎖定目標活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多變數測試 (MVT):** [建立多變數測試](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **建議:** [建立建議活動](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

>[!NOTE]
>
>在中匯出為JSON的體驗片段 [!DNL Target] 無法用於使用VEC建立的活動；VEC型活動僅支援HTML體驗片段。 如果您想要使用JSON體驗片段，請在使用 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md).

**若要使用表單式體驗撰寫器來使用體驗片段：**

1. 在 [!DNL Target]，在中建立或編輯體驗時 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)，請在頁面上選取您要插入的位置 [!DNL AEM] 內容，然後選取 **[!UICONTROL 變更體驗片段]** 顯示 [!UICONTROL 選擇體驗片段] 清單。

   ![experience_fragment_list影像](assets/experience_fragment_list.png)

   此 [!UICONTROL 體驗片段] 清單顯示中建立的內容 [!DNL AEM] 現在可從內取得原生功能 [!DNL Target].

1. 選取需要的體驗片段，然後按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 完成活動的設定。

## 考量事項 {#considerations}

* [!DNL Target] 目前每十分鐘會尋找要匯入的體驗片段。匯入的體驗片段應可在 [!DNL Target] 10分鐘內，但此時間範圍會日後縮短。
* 體驗片段會匯入至 [!DNL Target] 作為HTML或JSON選件。 體驗片段「主要」版本仍保留在 [!DNL AEM]. 您無法在中編輯體驗片段 [!DNL Target].
* 您無法使用 [!DNL Adobe I/O]. 使用AEM建立體驗片段，如上所述。
* 如果您在AEM中更新體驗片段，則體驗片段必須發佈並匯出至 [!DNL Target] aw [!DNL Target] 可使用最新變更。

## 從匯出至 Target 的體驗片段中移除 ClientLib 和無關的 HTML

搭配使用體驗片段選件時 [!DNL Target] 在AEM傳送的頁面上，目標頁面已包含所有必要的用戶端程式庫。 另請注意，選件中也不需要無關的HTML元素。

有時整個HTML頁面會包住體驗片段並造成問題。 請確定體驗片段是一小段HTML，而非包含HTML、HEAD、BODY等的完整HTML頁面。

如需詳細資訊，請參閱下列部落格文章： [AEM 6.5:從匯出至Target的體驗片段中移除ClientLib](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}。

## 訓練影片：搭配使用AEM體驗片段 [!DNL Adobe Target]

下列影片會示範如何設定和使用體驗片段：

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>此 [!DNL AEM] 4:54處討論的deeplink功能已移除。

如需詳細資訊，請參閱 [搭配使用體驗片段Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) 在 *AEM Sites影片和Tutorials* 頁面。

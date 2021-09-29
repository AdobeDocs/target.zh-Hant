---
keywords: 體驗； JSON; AEM;Adobe Experience Manager；匯出至Adobe Target；體驗片段；片段； XF
description: 了解如何在Adobe [!DNL Target] 活動中使用AEM體驗片段。 將AEM的易用性和強大功能與 [!DNL Target]中的強大AI和ML功能結合。
title: 如何使用Adobe Experience Manager(AEM)體驗片段？
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 0d5d31a421acb595702e6420c74e969124cc3daf
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 22%

---

# AEM 體驗片段

在[!DNL Target]活動中使用在[!DNL Adobe Experience Manager](AEM)中建立的體驗片段，以輔助最佳化或個人化的相關資訊。

>[!NOTE]
>
>此功能要求您是[!DNL Adobe Experience Manager]([!DNL AEM])客戶。 如需詳細資訊，請參閱以下的[需求](/help/c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)。

## 總覽 {#section_95A91830530F493B81C5C9CDB9B783EA}

在[!DNL Target]活動中使用在[!DNL AEM]中建立的體驗片段，可讓您結合[!DNL AEM]的易用性和威力，以及[!DNL Target]中強大的自動化智慧(AI)和機器學習(ML)功能，以大規模測試並個人化體驗。

[!DNL AEM] 將您的所有內容和資產集中在一個中央位置，以支援您的個人化策略。[!DNL AEM] 可讓您在一個位置中輕鬆地為桌上型電腦、平板電腦和行動裝置建立內容，不必撰寫程式碼。不需要為每個裝置建立頁面。 [!DNL AEM] 會使用您的內容自動調整每個體驗。

[!DNL Target] 可讓您根據一組包含行為、情境和離線變數的規則型和 AI 驅動型機器學習方法，以大規模實現個人化體驗。透過[!DNL Target]，您可以輕鬆設定並執行[A/B測試](/help/c-activities/t-test-ab/test-ab.md)和[多變數](/help/c-activities/c-multivariate-testing/multivariate-testing.md)(MVT)活動，以決定最佳選件、內容和體驗。

體驗片段代表將內容/體驗建立者和經理與使用[!DNL Target]推動業務成果的最佳化和個人化專業人員連結的一大步。

## 要求 {#section_AE6F0971E1574B3AA324003599B96E5A}

您必須在[!DNL Target]中布建體驗片段功能。 此外，您必須搭配適當的Service Pack或[!DNL AEM] 6.4（或更新版本）使用[!DNL AEM] 6.3。 您的客戶代表可協助確認您是否符合使用此功能的要求。

* [!DNL Adobe Experience Manager] 6.4（或更新版本）。
* [!DNL Adobe Experience Manager] 6.3 SP2（或更高版本）。
* [!DNL Adobe Target Standard] 或帳 [!DNL Adobe Target Premium] 戶。
* 請連絡[Adobe Target客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以啟用整合併提供驗證詳細資訊。

## 在[!DNL AEM]中建立和設定體驗片段 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

若要在[!DNL Target]中使用[!DNL AEM]體驗片段，您必須執行下列步驟：

### 步驟1:將[!DNL AEM]與[!DNL Target]整合

如需詳細資訊，請參閱:

* **Adobe I/O**: [使用管理使用者指南檔案中的AdobeI/](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html) 與Adobe Target _整_ 合。
* **[!DNL AEM]6.3**: [選擇使用Adobe Analytics和](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) Adobe鎖定 _Adobe Experience Manager 6.3_ 檔案。
* **[!DNL AEM]6.4**: [選擇使用Adobe Analytics和](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) Adobe鎖定 _Adobe Experience Manager 6.4_ 檔案。
* **[!DNL AEM]6.5**: [選擇使用Adobe Analytics和](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en) Adobe鎖定 *Adobe Experience Manager 6.5* 檔案。

### 步驟 2: 建立體驗片段

體驗片段是在[!DNL AEM]中建立。 如需詳細資訊，請參閱:

* **[!DNL AEM]6.3**: [Adobe Experience Manager ](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) 6.3檔 *案中的體驗* 片段。
* **[!DNL AEM]6.4**: [Adobe Experience Manager ](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=en) 6.4檔 *案中的體驗* 片段。
* **[!DNL AEM]6.5**: [Adobe Experience Manager ](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) 6.5檔 *案中的體驗* 片段。

### 步驟3:設定[!DNL AEM]以與[!DNL Target]共用體驗片段

1. 從[!DNL AEM]內，選取所需的體驗片段或其容納資料夾，然後按一下&#x200B;**[!UICONTROL 屬性]**。
2. 按一下&#x200B;**[!UICONTROL 「雲端服務」]**&#x200B;標籤，然後從&#x200B;**[!UICONTROL 「雲端服務組態」]**&#x200B;下拉式清單中，選取 **[!UICONTROL Adobe Target]**。

   >[!NOTE]
   >
   >上一步假設組織中的某人已建立[!DNL Adobe Target]設定。

3. 按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

### 步驟 4: 發佈體驗片段並將其匯出至 [!DNL Target]

視您的[!DNL AEM]版本而定，請參閱下列連結以取得逐步指示：

* **[!DNL AEM]6.3**: [在Adobe Experience Manager 6.3](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) 檔案中 *將體驗片段匯出* 至Target。
* **[!DNL AEM]6.4**: [在Adobe Experience Manager 6.4](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html) 檔案中 *將體驗片段匯出* 至Target。
* **[!DNL AEM]6.5**: [在Adobe Experience Manager 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) 檔案中 *將體驗片段匯出* 至Target。

## 在[!DNL Target]活動中使用體驗片段 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行先前的工作後，體驗片段會顯示在[!DNL Target]的[!UICONTROL 選件]頁面上。

>[!NOTE]
>
>[!DNL Target] 目前每十分鐘會尋找要匯入的體驗片段。10分鐘內應可在[!DNL Target]中使用匯入的體驗片段，但此時間範圍日後應會縮短。

>[!IMPORTANT]
>
>體驗片段目前是以HTML選件的形式匯入[!DNL Target]。 請注意，體驗片段「primary」版本仍保留在[!DNL AEM]中。 您無法編輯[!DNL Target]中的體驗片段。

您可以暫留在清單中的體驗片段上，然後按一下[!UICONTROL View]圖示![View icon](assets/icon_info.png) ，以查看關於體驗片段的其他資訊，包括其公開選件傳送URL及其[!DNL AEM]路徑。

您可以使用[可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)(VEC)或[表單式體驗撰寫器](/help/c-experiences/form-experience-composer.md)來在[!DNL Target]活動中使用體驗片段。

>[!NOTE]
>
>若要充分利用[!DNL Target] AI和ML功能，您可以在建立A/B測試時選取[自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。

**若要使用VEC使用體驗片段：**

1. 在[!DNL Target]中，在[可視化體驗撰寫器](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中建立或編輯體驗時，按一下您要插入[!DNL AEM]內容的頁面位置，然後選取所需選項以顯示[!UICONTROL 選擇體驗片段]清單。

   * [!UICONTROL 插入在前]
   * [!UICONTROL 插入在後]
   * [!UICONTROL 交換體驗片段]

   [!UICONTROL 體驗片段]清單會顯示在[!DNL AEM]中建立的所有內容，現在可從[!DNL Target]內取得原生清單。

   >[!NOTE]
   >
   >[!UICONTROL 「交換體驗片段」]選項不適用於影像。如果您想將此選項用於影像，請按一下包含所需影像的容器元素。

   ![](assets/experience_fragment_list.png)

1. 選取所需的體驗片段，然後按一下&#x200B;**[!UICONTROL Done]**。
1. 完成活動的設定。

   如需有關設定各種活動類型的詳細資訊，請參閱下列主題:

   * **A/B 測試:** [建立 A/B 測試](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動分配:** [自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動鎖定目標：** [自動鎖定目標](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):**[建立 Automated Personalization 活動](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **體驗鎖定目標 (XT):** [建立體驗鎖定目標活動](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多變數測試 (MVT):** [建立多變數測試](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **建議:** [建立建議活動](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**若要使用表單式體驗撰寫器來使用體驗片段：**

1. 在[!DNL Target]中，在[表單式體驗撰寫器](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中建立或編輯體驗時，請在頁面上選取您要插入[!DNL AEM]內容的位置，然後選取&#x200B;**[!UICONTROL 變更體驗片段]**&#x200B;以顯示[!UICONTROL 選擇體驗片段]清單。

   ![](assets/experience_fragment_list.png)

   [!UICONTROL 體驗片段]清單會顯示在[!DNL AEM]中建立的所有內容，現在可從[!DNL Target]內取得原生清單。

1. 選取需要的體驗片段，然後按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 完成活動的設定。

## 考量事項 {#considerations}

* [!DNL Target] 目前每十分鐘會尋找要匯入的體驗片段。10分鐘內應可在[!DNL Target]中使用匯入的體驗片段，但此時間範圍日後應會縮短。
* 體驗片段目前是以HTML選件的形式匯入[!DNL Target]。 請注意，體驗片段「primary」版本仍保留在[!DNL AEM]中。 您無法編輯[!DNL Target]中的體驗片段。
* 您無法使用AdobeIO建立體驗片段。 您必須使用AEM建立體驗片段，如上所述。

## 訓練影片：搭配Adobe Target ![教學課程徽章](/help/assets/overview.png)使用AEM體驗片段 {#section_C0EDC54063464F41A182492D2045BC64}

下列影片會示範如何設定和使用體驗片段：

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>已移除4:54處討論的[!DNL AEM]深層連結功能。

如需詳細資訊，請參閱&#x200B;*AEM Sites影片和Tutorials*&#x200B;頁面上的[搭配Adobe Target使用體驗片段](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html)。

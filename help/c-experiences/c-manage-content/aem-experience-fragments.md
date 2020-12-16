---
keywords: experience;json;aem;adobe experience manager;export to adobe target;experience fragments;fragments;XF
description: 有關在Adobe Target活動中使用在Adobe Experience Manager(AEM)中建立的體驗片段以協助最佳化或個人化的資訊。
title: Adobe Target中的Adobe Experience Manager(AEM)體驗片段
feature: aem
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 22%

---


# AEM 體驗片段{#aem-experience-fragments}

有關在[!DNL Target]活動中使用[!DNL Adobe Experience Manager](AEM)中建立的體驗片段以協助最佳化或個人化的資訊。

>[!NOTE]
>
>此功能要求您是[!DNL Adobe Experience Manager]([!DNL AEM])客戶。 如需詳細資訊，請參閱以下的[需求](/help/c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)。

## 概述 {#section_95A91830530F493B81C5C9CDB9B783EA}

使用[!DNL Target]活動中[!DNL AEM]建立的體驗片段，您可結合[!DNL AEM]的易用性和強大功能，以及[!DNL Target]中強大的自動智慧(AI)和機器學習(ML)功能，以大規模測試和個人化體驗。

[!DNL AEM] 將您的所有內容和資產集中在一個中央位置，以支援您的個人化策略。[!DNL AEM] 可讓您在一個位置中輕鬆地為桌上型電腦、平板電腦和行動裝置建立內容，不必撰寫程式碼。您不需要為每個裝置建立頁面。 [!DNL AEM] 使用您的內容自動調整每個體驗。

[!DNL Target] 可讓您根據一組包含行為、情境和離線變數的規則型和 AI 驅動型機器學習方法，以大規模實現個人化體驗。使用[!DNL Target]，您可輕鬆設定並執行[A/B測試](/help/c-activities/t-test-ab/test-ab.md)和[多變數](/help/c-activities/c-multivariate-testing/multivariate-testing.md)(MVT)活動，以決定最佳選件、內容和體驗。

體驗片段是將內容／體驗建立者和經理人連結至最佳化和個人化專業人員的一大步，這些專業人員使用[!DNL Target]推動業務成果。

## 要求 {#section_AE6F0971E1574B3AA324003599B96E5A}

您必須在[!DNL Target]中布建體驗片段功能。 此外，您必須使用[!DNL AEM] 6.3搭配適當的Service Pack或[!DNL AEM] 6.4（或更新版本）。 您的客戶代表可協助確認您是否符合使用此功能的要求。

* [!DNL Adobe Experience Manager] 6.4（或更新版本）。
* [!DNL Adobe Experience Manager] 6.3 SP2（或更新版本）。
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帳戶。
* 請聯絡[Adobe Target客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以啟用整合併提供驗證詳細資訊。

## 在[!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}中建立和設定體驗片段

若要在[!DNL Target]中使用[!DNL AEM]體驗片段，您必須執行下列步驟：

### 步驟1:將[!DNL AEM]與[!DNL Target]整合

如需詳細資訊，請參閱:

* **[!DNL AEM]6.3**: [選擇Adobe Analytics和Adobe ](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) Targeting  _Adobe Experience Manager 6.3文_ 件。
* **[!DNL AEM]6.4**: [選擇Adobe Analytics和Adobe ](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) Targeting  _Adobe Experience Manager 6.4文_ 件。
* **[!DNL AEM]6.5**: [選擇Adobe Analytics和Adobe ](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) Targeting  *Adobe Experience Manager 6.5文* 件。

### 步驟 2: 建立體驗片段

體驗片段是在[!DNL AEM]中建立的。 如需詳細資訊，請參閱:

* **[!DNL AEM]6.3**: [在](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) Adobe Experience Manager 6.3檔案中體驗 ** 片段。
* **[!DNL AEM]6.4**: [在](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) Adobe Experience Manager 6.4檔案中體驗 ** 片段。
* **[!DNL AEM]6.5**: [在](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) Adobe Experience Manager 6.5檔案中體驗 ** 片段。

### 步驟3:設定[!DNL AEM]與[!DNL Target]共用體驗片段

1. 在[!DNL AEM]中，選擇所需的體驗片段或其包含資料夾，然後按一下「屬性」****。
2. 按一下&#x200B;**[!UICONTROL 「雲端服務」]**&#x200B;標籤，然後從&#x200B;**[!UICONTROL 「雲端服務組態」]**&#x200B;下拉式清單中，選取 **[!UICONTROL Adobe Target]**。

   >[!NOTE]
   >
   >上一步驟假設您組織中的某人已建立[!DNL Adobe Target]組態。

3. 按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

### 步驟 4: 發佈體驗片段並將其匯出至 [!DNL Target]

視您的[!DNL AEM]版本而定，請參閱下列連結以取得逐步指示：

* **[!DNL AEM]6.3**: [將體驗片段匯出](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) 至 *Adobe Experience Manager 6.3檔案的* 定位。
* **[!DNL AEM]6.4**: [將體驗片段匯出](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html) 至 *Adobe Experience Manager 6.4檔案的* 定位。
* **[!DNL AEM]6.5**: [將體驗片段匯出](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) 至 *Adobe Experience Manager 6.5檔案的* 定位。

## 在Target活動{#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}中使用體驗片段

執行上述任務後，體驗片段會顯示在[!DNL Target]的[!UICONTROL 選件]頁面上。

>[!NOTE]
>
>[!DNL Target] 目前每十分鐘會尋找要匯入的體驗片段。匯入的體驗片段應在10分鐘內於[!DNL Target]提供，但此時間範圍應會縮短。

>[!IMPORTANT]
>
>體驗片段目前會以HTML選件的形式匯入至[!DNL Target]。 請注意，體驗片段「primary」版本仍保留在[!DNL AEM]中。 您無法在[!DNL Target]中編輯體驗片段。

您可以將滑鼠指標暫留在清單中的體驗片段上，然後按一下「檢視」圖示「檢視」圖示「[!UICONTROL 檢視」圖示「]」，以檢視體驗片段的其他資訊，包括其公開選件傳送URL及其![路徑。](assets/icon_info.png)[!DNL AEM]

您可以使用[Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)(VEC)或[表單型體驗撰寫器](/help/c-experiences/form-experience-composer.md)來使用[!DNL Target]活動中的體驗片段。

>[!NOTE]
>
>要充分利用[!DNL Target] AI和ML功能，可以在建立A/B測試時選擇[自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。

**若要使用VEC使用體驗片段：**

1. 在[!DNL Target]中，在[Visual Experience Composer](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中建立或編輯體驗時，按一下您要插入[!DNL AEM]內容之頁面上的位置，然後選取想要的選項以顯示[!UICONTROL 選擇體驗片段]清單。

   * [!UICONTROL 插入在前]
   * [!UICONTROL 插入在後]
   * [!UICONTROL 與體驗片段交換]

   [!UICONTROL 體驗片段]清單會顯示在[!DNL AEM]中建立的所有內容，現在可從[!DNL Target]內取得。

   >[!NOTE]
   >
   >[!UICONTROL 「交換體驗片段」]選項不適用於影像。如果您想將此選項用於影像，請按一下包含所需影像的容器元素。

   ![](assets/experience_fragment_list.png)

1. 選取所需的體驗片段，然後按一下「完成」。****
1. 完成活動的設定。

   如需有關設定各種活動類型的詳細資訊，請參閱下列主題:

   * **A/B 測試:** [建立 A/B 測試](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動分配:** [自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動定位：** [自動定位](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):**[建立 Automated Personalization 活動](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **體驗鎖定目標 (XT):** [建立體驗鎖定目標活動](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多變數測試 (MVT):** [建立多變數測試](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **建議:** [建立建議活動](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**若要使用表單型體驗撰寫器來使用體驗片段：**

1. 在[!DNL Target]中，在[表單型體驗撰寫器](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中建立或編輯體驗時，選取您要插入[!DNL AEM]內容的頁面位置，然後選取&#x200B;**[!UICONTROL 變更體驗片段]**&#x200B;以顯示[!UICONTROL 選擇體驗片段]清單。

   ![](assets/experience_fragment_list.png)

   [!UICONTROL 體驗片段]清單會顯示在[!DNL AEM]中建立的所有內容，現在可從[!DNL Target]內取得。

1. 選取需要的體驗片段，然後按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 完成活動的設定。

## 考量事項 {#considerations}

* [!DNL Target] 目前每十分鐘會尋找要匯入的體驗片段。匯入的體驗片段應在10分鐘內於[!DNL Target]提供，但此時間範圍應會縮短。
* 體驗片段目前會以HTML選件的形式匯入至[!DNL Target]。 請注意，體驗片段「primary」版本仍保留在[!DNL AEM]中。 您無法在[!DNL Target]中編輯體驗片段。
* 您可以將JSON選件匯入為體驗片段至[!DNL Target]。 不過，這些選件會匯入為HTML選件。 [!DNL Target] UI目前未完全支援JSON選件（體驗片段）。
* 您無法使用Adobe IO建立體驗片段。 您必須使用AEM建立體驗片段，如上所述。

## 訓練影片：將AEM體驗片段與Adobe Target ![教學課程標章](/help/assets/overview.png) {#section_C0EDC54063464F41A182492D2045BC64}搭配使用

以下影片將示範如何設定和使用體驗片段：

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>已移除4:54討論的[!DNL AEM]深層連結功能。

如需詳細資訊，請參閱[AEM網站影片和教學課程](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html)頁面上的「搭配Adobe Target使用體驗片段」。**

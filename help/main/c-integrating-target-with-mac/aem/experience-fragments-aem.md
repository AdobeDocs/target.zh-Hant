---
keywords: 體驗； JSON; AEM;Adobe Experience Manager；匯出至Adobe Target；體驗片段；片段； XF
description: 了解如何使用 [!DNL Adobe Experience Manager] [!UICONTROL 體驗片段] in [!DNL Adobe Target] 活動。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 體驗片段]?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 10%

---

# AEM [!UICONTROL 體驗片段]

使用 [!UICONTROL 體驗片段] (XF)建立於 [!DNL Adobe Experience Manager] (AEM) [!DNL Target] 活動來協助最佳化或個人化。

>[!NOTE]
>
>使用AEM時，請考量下列事項 [!UICONTROL 體驗片段] in [!DNL Target]:
> 
>* 此功能需要您 [!DNL Adobe Experience Manager] (AEM)客戶。 如需詳細資訊，請參閱 [需求](#section_AE6F0971E1574B3AA324003599B96E5A) 下方。
>* 此功能適用於下列活動類型： [!UICONTROL A/B測試], [!UICONTROL 自動分配], [!UICONTROL 自動鎖定目標], [!UICONTROL Automated Personalization] （美聯社）和 [!UICONTROL 體驗鎖定] (XT)。 此功能在 [!UICONTROL 多變數測試] (MVT)和 [!UICONTROL Recommendations] 活動。
>
>* 您可以 [!UICONTROL 體驗片段] in [!DNL Target] 活動使用 [可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)或 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md).


深入了解AEM [!UICONTROL 體驗片段] 和內容片段，請參閱 [AEM [!UICONTROL 體驗片段] 和內容片段概觀](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## 要求 {#requirements}

您必須布建 [!UICONTROL 體驗片段] 功能 [!DNL Target]. 此外，您必須使用 [!DNL AEM] as a Cloud Service或 [!DNL AEM] 6.4（或更新版本）。 您的客戶代表可協助確認您是否符合使用此功能的要求。

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帳戶。

[!DNL Adobe Experience Manager] 6.3和6.4已結束生命週期，不再提供支援（購買延長支援的客戶除外）。

連絡人 [Adobe Target客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 啟用整合併提供驗證詳細資料。

## 建立和設定 [!UICONTROL 體驗片段] in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

為了使用 [!DNL AEM] [!UICONTROL 體驗片段] in [!DNL Target]，您必須執行下列步驟：

### 步驟1:整合 [!DNL AEM] with [!DNL Target]

如需詳細資訊，請參閱：

* **AEMas a Cloud Service**: [與Adobe Target整合](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} 在 *Experience Manageras a Cloud Service* 指南。
* **Adobe I/O**: [使用Adobe Target I/0與Adobe整合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html){target=_blank} 在 *管理使用手冊* 檔案。
* **[!DNL AEM]6.5**: [選擇使用Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en){target=_blank} 在 *Adobe Experience Manager 6.5* 檔案。
* **[!DNL AEM]6.4**: [選擇使用Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank} 在 *Adobe Experience Manager 6.4* 檔案。

### 步驟2:建立體驗片段

[!UICONTROL 體驗片段] 在中建立 [!DNL AEM]. 如需詳細資訊，請參閱：

* **AEMas a Cloud Service**: [[!UICONTROL 體驗片段]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} 在 *Experience Manageras a Cloud Service* 指南。
* **[!DNL AEM]6.5**: [[!UICONTROL 體驗片段]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=en){target=_blank} 在 *Adobe Experience Manager 6.5* 檔案。
* **[!DNL AEM]6.4**: [[!UICONTROL 體驗片段]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=en){target=_blank} 在 *Adobe Experience Manager 6.4* 檔案。

### 步驟3:設定 [!DNL AEM] 共用體驗片段的方式 [!DNL Target]

1. 從內 [!DNL AEM]，請選取所需的體驗片段或其容納資料夾，然後按一下 **[!UICONTROL 屬性]**.
2. 按一下&#x200B;**[!UICONTROL 「雲端服務」]**&#x200B;標籤，然後從&#x200B;**[!UICONTROL 「雲端服務組態」]**&#x200B;下拉式清單中，選取 **[!UICONTROL Adobe Target]**。

   上一步假設組織中的某人已建立 [!DNL Adobe Target] 設定。

3. 按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

### 步驟4:發佈體驗片段並匯出至 [!DNL Target]

視您的 [!DNL AEM] 版本，請參閱下列連結以取得逐步指示：

* **AEMas a Cloud Service**: [匯出 [!UICONTROL 體驗片段] 到Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} 在 *Experience Manageras a Cloud Service* 指南。
* **[!DNL AEM]6.5**: [將體驗片段匯出至Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} 在 *Adobe Experience Manager 6.5* 檔案。
* **[!DNL AEM]6.4**: [將體驗片段匯出至Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank} 在 *Adobe Experience Manager 6.4* 檔案。

## 使用 [!UICONTROL 體驗片段] in [!DNL Target] 活動 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行先前的工作後，體驗片段會顯示在 [!UICONTROL 選件] 頁面 [!DNL Target].

[!DNL Target] 當前查找 [!UICONTROL 體驗片段] 每十分鐘匯入一次。 匯入的體驗片段應可在 [!DNL Target] 10分鐘內，但此時間範圍會日後縮短。

體驗片段會匯入至 [!DNL Target] 作為HTML或JSON選件。 體驗片段「主要」版本仍保留在 [!DNL AEM]. 您無法在中編輯體驗片段 [!DNL Target].

您可以依 [!UICONTROL HTMLXF] 和 [!UICONTROL JSON XF] 可協助您區分匯出至的體驗片段類型 [!DNL Target].

![依體驗片段類型篩選：HTML或JSON（在Target UI中）](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以暫留在清單中的體驗片段上，然後按一下 [!UICONTROL 檢視] 圖示 ![資訊圖示](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) 若要查看體驗片段的其他相關資訊，包括 [!UICONTROL 名稱], [!UICONTROL 類型], [!UICONTROL 選件ID], [!UICONTROL 選件路徑]、和上次修改資訊。 按一下 [!UICONTROL 優惠方案使用量] 索引標籤來查看參考此選件的活動。

![體驗片段資訊快顯視窗](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

您可以 [!UICONTROL 體驗片段] in [!DNL Target] 活動使用 [可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)或 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md).


>[!TIP]
>
>搭配使用人工智慧、機器學習和建議 [!UICONTROL 體驗片段]:
>
>* 若要充分使用 [!DNL Target] AI和ML功能，您可以選取 [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) 或 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 建立A/B測試時。
>
>* [!UICONTROL 體驗片段] 不支援 [!DNL Recommendations] 活動。 不過，若要使用 [!UICONTROL 體驗片段] 您可以為建議建立 [!UICONTROL A/B測試] 活動(包括 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標])或 [!UICONTROL 體驗鎖定] (XT)活動和 [將建議納入選件](/help/main/c-recommendations/recommendations-as-an-offer.md).


**使用 VEC 來取用體驗片段:**

1. 在 [!DNL Target]，在中建立或編輯體驗時 [可視化體驗撰寫器](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)，按一下您要插入的頁面上的位置 [!DNL AEM] 內容，然後選取要顯示 [!UICONTROL 選擇體驗片段] 清單。

   * [!UICONTROL 插入在前]
   * [!UICONTROL 插入在後]
   * [!UICONTROL 交換體驗片段]

   此 [!UICONTROL 體驗片段] 清單顯示中建立的內容 [!DNL AEM] 現在可從內取得原生功能 [!DNL Target].

   >[!NOTE]
   >
   >[!UICONTROL 「交換體驗片段」]選項不適用於影像。如果您想將此選項用於影像，請按一下包含所需影像的容器元素。

   ![experience_fragment_list影像](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 選取所需的體驗片段，然後按一下 **[!UICONTROL 完成]**.
1. 完成活動的設定。

   如需有關設定各種活動類型的詳細資訊，請參閱下列主題:

   * **A/B 測試:** [建立 A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動分配:** [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動鎖定目標：** [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):**[建立 Automated Personalization 活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **體驗鎖定目標 (XT):** [建立體驗鎖定目標活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommendations（A/B測試或XT活動）:** [Recommendations作為優惠方案](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL 體驗片段] 匯出為JSON，於 [!DNL Target] 無法用於使用VEC建立的活動；僅HTML [!UICONTROL 體驗片段] 在VEC型活動中受支援。 如果您想使用JSON [!UICONTROL 體驗片段]，請在使用 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md).

**使用表單式體驗撰寫器來取用體驗片段:**

1. 在 [!DNL Target]，在中建立或編輯體驗時 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)，請在頁面上選取您要插入的位置 [!DNL AEM] 內容，然後選取 **[!UICONTROL 變更體驗片段]** 顯示 [!UICONTROL 選擇體驗片段] 清單。

   ![experience_fragment_list影像](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   此 [!UICONTROL 體驗片段] 清單顯示中建立的內容 [!DNL AEM] 現在可從內取得原生功能 [!DNL Target].

1. 選取所需的體驗片段，然後按一下 **[!UICONTROL 儲存]**.
1. 完成活動的設定。

## 考量事項 {#considerations}

* [!DNL Target] 當前查找 [!UICONTROL 體驗片段] 每十分鐘匯入一次。 匯入的體驗片段應可在 [!DNL Target] 10分鐘內，但此時間範圍會日後縮短。
* 體驗片段會匯入至 [!DNL Target] 作為HTML或JSON選件。 體驗片段「主要」版本仍保留在 [!DNL AEM]. 您無法在 [!DNL Target].
* 您無法建立 [!UICONTROL 體驗片段] 使用 [!DNL Adobe I/O]. 建立 [!UICONTROL 體驗片段] 使用AEM，如上所述。
* 如果您更新AEM中的體驗片段，則體驗片段必須發佈並匯出至 [!DNL Target] aw [!DNL Target] 可使用最新變更。

## 移除ClientLib和無關HTML [!UICONTROL 體驗片段] 匯出至 [!UICONTROL 目標]

搭配使用體驗片段選件時 [!DNL Target] 在AEM傳送的頁面上，目標頁面已包含所有必要的用戶端程式庫。 另請注意，選件中也不需要無關的HTML元素。

有時整個HTML頁面會包住體驗片段並造成問題。 確認體驗片段是一小段HTML，而非包含HTML、HEAD、BODY等的完整HTML頁面。

如需詳細資訊，請參閱下列部落格文章： [AEM 6.5:從 [!UICONTROL 體驗片段] 匯出至Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## 訓練影片：使用AEM [!UICONTROL 體驗片段] with [!DNL Adobe Target]

以下影片會示範如何設定和使用 [!UICONTROL 體驗片段]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>此 [!DNL AEM] 4:54處討論的deeplink功能已移除。

如需詳細資訊，請參閱 [使用 [!UICONTROL 體驗片段] 搭配Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) 在 *AEM Sites影片和Tutorials* 頁面。
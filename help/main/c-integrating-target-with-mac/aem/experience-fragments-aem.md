---
keywords: 體驗；JSON；AEM；Adobe Experience Manager；匯出至 Adobe Target；體驗片段；片段；XF
description: 瞭解如何在 [!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments]活動中使用 [!DNL Adobe Target] 。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Experience Fragments]？
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: b29614680b27c9c33f11eed85d8ab4feebc28b0d
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 26%

---

# AEM [!UICONTROL Experience Fragments]

在[!UICONTROL Experience Fragments]個活動中使用[!DNL Adobe Experience Manager] (AEM)中建立的[!DNL Target] (XF)來協助最佳化和個人化。

## 考量事項

當您在[!UICONTROL Experience Fragments]中使用AEM [!DNL Target]時，請考慮下列事項：

* 您需為 [!DNL Adobe Experience Manager] (AEM) 客戶才能使用此功能。如需詳細資訊，請參閱下方的[要求](#section_AE6F0971E1574B3AA324003599B96E5A)。
* [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]可用於下列活動型別：

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]不適用於下列活動型別：

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* 您可以使用[!UICONTROL Experience Fragments]視覺化體驗撰寫器[!DNL Target] (VEC)和[表單式體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)，在[個活動中使用](/help/main/c-experiences/form-experience-composer.md)。

若要進一步瞭解AEM [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]，請參閱[AEM [!UICONTROL Experience Fragments]和內容片段總覽](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 要求 {#requirements}

您必須在[!UICONTROL Experience Fragments]內布建[!DNL Target]功能。 此外，您必須使用 [!DNL AEM] as a Cloud Service 或 [!DNL AEM] 6.4 (或更新版本)。您的客戶代表可協助確認您是否符合使用此功能的要求。

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帳戶

[!DNL Adobe Experience Manager] 6.3 和 6.4 的生命週期已結束，不再受支援 (購買了延長支援的客戶除外)。

請和 [Adobe Target 客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)聯絡，以啟用整合並取得驗證的詳細資訊。

## 在[!UICONTROL Experience Fragments]中建立和設定[!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

若要在[!DNL AEM]中使用[!UICONTROL Experience Fragments] [!DNL Target]，您必須執行下列步驟：

### 步驟 1：將 [!DNL AEM] 和 [!DNL Target] 整合

如需詳細資訊，請參閱：

* **AEM as a Cloud Service**： [在](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank}Adobe Target as a Cloud Service *指南中與Experience Manager*&#x200B;整合。
* **Adobe Developer**： [使用](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html){target=_blank}管理使用手冊&#x200B;*檔案中的Adobe I/0*&#x200B;與Adobe Target整合。
* **[!DNL AEM]6.5**： [在](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=zh-Hant){target=_blank}Adobe Analytics 6.5 *檔案中選擇使用Adobe Experience Manager和Adobe Target*。
* **[!DNL AEM]6.4**： [在](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank}Adobe Analytics 6.4 *檔案中選擇使用Adobe Experience Manager和Adobe Target*。

### 步驟 2：建立體驗片段

已在[!UICONTROL Experience Fragments]中建立[!DNL AEM]。 如需詳細資訊，請參閱：

* **AEM as a Cloud Service**： [[!UICONTROL Experience Fragments]Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=zh-Hant){target=_blank}指南中的&#x200B;**。
* **[!DNL AEM]Adobe Experience Manager 6.5**&#x200B;檔案中的[[!UICONTROL Experience Fragments] 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=zh-Hant){target=_blank}： **。
* **[!DNL AEM]Adobe Experience Manager 6.4**&#x200B;檔案中的[[!UICONTROL Experience Fragments] 6.4](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=zh-Hant){target=_blank}： **。

### 步驟3：設定[!DNL AEM]以與[!UICONTROL Experience Fragment]共用[!DNL Target]

1. 從[!DNL AEM]中，選取所需的[!UICONTROL Experience Fragment]或其收納資料夾，然後按一下&#x200B;**[!UICONTROL Properties]**。
2. 按一下&#x200B;**[!UICONTROL Cloud Services]**&#x200B;標籤，然後從&#x200B;**[!UICONTROL Cloud Service Configuration]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Adobe Target]**。

   上一步假設您的組織中有人已建立 [!DNL Adobe Target] 設定。

3. 按一下 **[!UICONTROL Save & Close]**。

### 步驟4：發佈[!UICONTROL Experience Fragment]並將其匯出至[!DNL Target]

依據您的 [!DNL AEM] 版本的不同，請參閱以下連結以取得逐步說明：

* **AEM as a Cloud Service**： [在[!UICONTROL Experience Fragments]Adobe Target as a Cloud Service](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank}指南中，將&#x200B;*匯出至Experience Manager*。
* **[!DNL AEM]6.5**： [在](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=zh-Hant){target=_blank}Adobe Experience Manager 6.5 *檔案中，將體驗片段匯出至Target*。
* **[!DNL AEM]6.4**： [在](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank}Adobe Experience Manager 6.4 *檔案中，將體驗片段匯出至Target*。

## 在[!UICONTROL Experience Fragments]個活動中使用[!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行先前的工作之後，[!UICONTROL Experience Fragment]會顯示在[!UICONTROL Offers]的[!DNL Target]頁面上。

[!DNL Target]目前每十分鐘會尋找要匯入的[!UICONTROL Experience Fragments]。 匯入的[!UICONTROL Experience Fragment]應該會在10分鐘內於[!DNL Target]內提供，但此時間範圍應會縮短。

[!UICONTROL Experience Fragment]已作為HTML或JSON選件匯入至[!DNL Target]。 [!UICONTROL Experience Fragment]「主要」版本仍保留在[!DNL AEM]中。 您無法在[!UICONTROL Experience Fragment]中編輯[!DNL Target]。

您可以依[!UICONTROL HTML XFs]和[!UICONTROL JSON XFs]篩選和搜尋，以協助您區分匯出至[!UICONTROL Experience Fragment]的[!DNL Target]型別。

![依據體驗片段類型進行篩選：Target UI 中的 HTML 或 JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以暫留在清單中的[!UICONTROL Experience Fragment]上，然後按一下[!UICONTROL View]圖示![資訊圖示](/help/main/assets/icons/InfoOutline.svg)以檢視有關[!UICONTROL Experience Fragment]的其他資訊，包括其[!UICONTROL Name]、[!UICONTROL Type]、[!UICONTROL Offer ID]、[!UICONTROL Offer path]和上次修改資訊。 按一下[!UICONTROL [!UICONTROL View Full Details]]以檢視參照此優惠方案的活動。

![體驗片段資訊快顯視窗](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

您可以使用[!UICONTROL Experience Fragments]視覺化體驗撰寫器[!DNL Target] (VEC)和[表單式體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)，在[個活動中使用](/help/main/c-experiences/form-experience-composer.md)。

>[!TIP]
>
>使用包含[!UICONTROL Experience Fragments]的人工智慧、機器學習與建議：
>
>* 若要充分利用 [!DNL Target] AI 和 ML 功能，您可以在建立活動時選取[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自動個人化](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
>
>* [!UICONTROL Experience Fragments]活動中不支援[!DNL Recommendations]。 不過，若要使用[!UICONTROL Experience Fragments]作為建議，您可以建立[!UICONTROL A/B Test]活動（包括[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]）或[!UICONTROL Experience Targeting] (XT)活動，以及[包含建議作為選件](/help/main/c-recommendations/recommendations-as-an-offer.md)。

**若要使用VEC使用[!UICONTROL Experience Fragments]：**

1. 在[!DNL Target]中，在[視覺化體驗撰寫器](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中建立或編輯體驗時，按一下頁面上您要插入[!DNL AEM]內容的位置，然後按一下「**[!UICONTROL Replace Content]**」>「**[!UICONTROL Experience Fragment]**」以顯示[!UICONTROL Experience Fragment]對話方塊。

   [!UICONTROL Experience Fragment]對話方塊會顯示在[!DNL AEM]中建立的內容，這些內容現在可從[!DNL Target]中以原生方式使用。

   >[!NOTE]
   >
   >[!UICONTROL Replace Content]選項不適用於影像。 如果您想將此選項用於影像，請按一下包含所需影像的容器元素。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 選取所需的[!UICONTROL Experience Fragment]，然後按一下&#x200B;**[!UICONTROL Add]**。
1. 完成活動的設定。

   如需有關設定各種活動類型的詳細資訊，請參閱下列主題:

   * **A/B 測試:** [建立 A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動分配:** [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動鎖定目標：**[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):**[建立 Automated Personalization 活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **體驗鎖定目標 (XT):** [建立體驗鎖定目標活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **A/B 測試或 XT 活動中的建議：**[產品建議形式的建議](/help/main/c-recommendations/recommendations-as-an-offer.md)

   在[!UICONTROL Experience Fragments]中匯出為JSON的[!DNL Target]無法用於使用VEC建立的活動；在VEC型活動中僅支援HTML [!UICONTROL Experience Fragments]。 如果您想要使用JSON [!UICONTROL Experience Fragments]，請在使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)建立的活動中使用。

**使用[!UICONTROL Experience Fragments]使用[!UICONTROL Form-based Experience Composer]：**

1. 在[!DNL Target]中，在[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中建立或編輯體驗時，在頁面上選取您要插入[!DNL AEM]內容的位置，按一下&#x200B;**[!UICONTROL More Details]**&#x200B;圖示（![更多詳細資料圖示](/help/main/assets/icons/MoreSmall.svg) ），然後選取&#x200B;**[!UICONTROL Change Experience Fragment]**&#x200B;以顯示[!UICONTROL Change Experience Fragment]對話方塊。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   [!UICONTROL Experience Fragment]對話方塊會顯示在[!DNL AEM]中建立的內容，這些內容現在可從[!DNL Target]中以原生方式使用。

1. 選取所需的[!UICONTROL Experience Fragment]，然後按一下&#x200B;**[!UICONTROL Add]**。
1. 完成活動的設定。

## 其他資訊

* [!DNL Target]目前每十分鐘會尋找要匯入的[!UICONTROL Experience Fragments]。 匯入的[!UICONTROL Experience Fragment]應該會在10分鐘內於[!DNL Target]內提供，但此時間範圍應會縮短。
* [!UICONTROL Experience Fragment]已作為HTML或JSON選件匯入至[!DNL Target]。 [!UICONTROL Experience Fragment]「主要」版本仍保留在[!DNL AEM]中。 您無法在[!UICONTROL Experience Fragment]中編輯[!DNL Target]。
* 您無法使用[!UICONTROL Experience Fragments]建立[!DNL Adobe Developer]。 使用AEM建立[!UICONTROL Experience Fragments]，如上所述。
* 如果您在AEM中更新[!UICONTROL Experience Fragment]，則必須發佈[!UICONTROL Experience Fragment]並再次匯出至[!DNL Target]，以便[!DNL Target]可以使用最新變更。

## 正在移除clientlibs和從匯出至[!UICONTROL Experience Fragments]的[!UICONTROL Target]中多餘的HTML

在AEM傳送的頁面上使用[!UICONTROL Experience Fragment]選件搭配[!DNL Target]時，目標頁面已包含必要的使用者端資料庫。 另請注意，產品建議中無關的 HTML 元素也不是必要的。

有時整個HTML頁面都會包裝[!UICONTROL Experience Fragment]並導致問題。 請確定[!UICONTROL Experience Fragment]是一小段HTML，而不是包含HTML、HEAD、BODY等的完整HTML頁面。

如需詳細資訊，請參閱下列部落格： [AEM 6.5：移除[!UICONTROL Experience Fragments]匯出至Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}的clientlibs。

## 訓練影片：將AEM [!UICONTROL Experience Fragments]與[!DNL Adobe Target]搭配使用

下列影片說明如何設定和使用[!UICONTROL Experience Fragments]：

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>已移除在4[!DNL AEM]討論的:54深層連結功能。

如需詳細資訊，請參閱[AEM Sites影片和教學課程[!UICONTROL Experience Fragments]頁面上的](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html)搭配Adobe Target *使用*。

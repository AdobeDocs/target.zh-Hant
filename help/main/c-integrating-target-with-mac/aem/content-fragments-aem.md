---
keywords: 體驗;JSON;AEM;Adobe Experience Manager;匯出至 Adobe Target;內容片段;片段;CF;cf;無頭;個人化;實驗
description: 瞭解如何在 [!DNL Adobe Target] 活動中使用 [!DNL Adobe Experience Manager] [!UICONTROL Content Fragments]。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Content Fragments]？
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: b29614680b27c9c33f11eed85d8ab4feebc28b0d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 15%

---

# AEM [!UICONTROL Content Fragments]

在[!DNL Target]活動中，使用在[!DNL Adobe Experience Manager] (AEM)中建立的[!UICONTROL Content Fragments] (CF)來協助Headless個人化和實驗。

## 考量事項

當您在[!DNL Target]中使用AEM [!UICONTROL Content Fragments]時，請考慮下列事項：

* 您需為 [!DNL Adobe Experience Manager as a Cloud Service] 客戶才能使用此功能。如需詳細資訊，請參閱下方的[要求](#section_AE6F0971E1574B3AA324003599B96E5A)。
* [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]可用於下列活動型別：

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]不適用於下列活動型別：

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* 您只能使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，在[!DNL Target]個活動中使用[!UICONTROL Content Fragments]。 您&#x200B;*無法*&#x200B;在使用[!UICONTROL Visual Experience Composer] (VEC)的[!DNL Target]個活動中使用[!UICONTROL Content Fragments]。

若要進一步瞭解AEM [!UICONTROL Content Fragments]和[!UICONTROL Experience Fragments]，請參閱[AEM [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]總覽](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 要求 {#requirements}

您必須使用[[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html){target=_blank}。 您的客戶代表可協助確認您是否符合使用此功能的要求：

請和 [Adobe Target 客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)聯絡，以啟用整合並取得驗證的詳細資訊。

## 設定和使用[!DNL AEM]中的[!UICONTROL Content Fragments] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

若要匯出[!UICONTROL Content Fragments]以用於[!DNL Target]活動，您必須在AEM中執行一些初步步驟。 如需詳細資訊，請參閱&#x200B;*Adobe Target as a Cloud Service檔案*&#x200B;中的[將內容片段匯出至Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank}。

如需有關設計、建立、組織和發佈[!UICONTROL Content Fragments]的資訊，請參閱[Experience Manager as a Cloud Service檔案](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}中的[[!UICONTROL Content Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=zh-Hant){target=_blank}和[使用內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank}。

## 在[!DNL Target]個活動中使用[!UICONTROL Content Fragments] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行先前的工作之後，[!UICONTROL Content Fragment]會顯示在[!DNL Target]的[!UICONTROL Offers]頁面上。

[!DNL Target]目前每十分鐘會尋找要匯入的[!UICONTROL Content Fragments]。 匯入的[!UICONTROL Content Fragment]應該會在10分鐘內於[!DNL Target]內提供，但此時間範圍應會縮短。

[!UICONTROL Content Fragment]已匯入至[!DNL Target]做為JSON選件。 [!UICONTROL Content Fragment]「主要」版本仍保留在[!DNL AEM]中。 您無法在[!DNL Target]中編輯[!UICONTROL Content Fragment]。

您可以依[!UICONTROL HTML XFs]、[!UICONTROL JSON XFs]和[!UICONTROL Content Fragments]篩選和搜尋，以協助您區分匯出至[!DNL Target]的不同優惠方案型別。

![依據內容片段類型進行篩選：Target UI 中的 HTML 或 JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以暫留在清單中的[!UICONTROL Experience Fragment]上，然後按一下[!UICONTROL View]圖示![資訊圖示](/help/main/assets/icons/InfoOutline.svg)以檢視有關[!UICONTROL Content Fragment]的其他資訊，包括其[!UICONTROL Name]、[!UICONTROL Type]、[!UICONTROL Offer ID]、[!UICONTROL Offer path]和上次修改資訊。 按一下[!UICONTROL [!UICONTROL View Full Details]]以檢視參照此優惠方案的活動。

您只能使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，在[!DNL Target]個活動中使用[!UICONTROL Content Fragments]。 您&#x200B;*無法*&#x200B;在使用[視覺化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)的[!DNL Target]活動中使用[!UICONTROL Content Fragments]。 [!UICONTROL Content Fragments]會匯出為[!DNL Target]中的JSON，且無法在使用VEC建立的活動中使用。

>[!TIP]
>
>使用包含[!UICONTROL Content Fragments]的人工智慧、機器學習與建議：
>
>* 若要充分利用[!DNL Target] AI和ML功能，您可以在建立[!UICONTROL A/B Test]活動時選取[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
>
>* [!DNL Recommendations]活動中不支援[!UICONTROL Content Fragments]。 不過，若要使用[!UICONTROL Content Fragments]作為建議，您可以建立[!UICONTROL A/B Test]活動（包括[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]）或[!UICONTROL Experience Targeting] (XT)活動，以及[包含建議作為選件](/help/main/c-recommendations/recommendations-as-an-offer.md)。

**使用[!UICONTROL Form-based Experience Composer]使用[!UICONTROL Content Fragments]：**

1. 在[!DNL Target]中，在[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中建立或編輯體驗時，請在頁面上選取您要插入[!DNL AEM]內容的位置，然後選取&#x200B;**[!UICONTROL Change Content Fragment]**&#x200B;以顯示[!UICONTROL Choose a Content Fragment]清單。

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   [!UICONTROL Content Fragment]清單顯示在[!DNL AEM]中建立的內容，現在可從[!DNL Target]中以原生方式使用。

1. 選取所需的[!UICONTROL Content Fragment]，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 完成活動的設定。

## 其他資訊

* [!DNL Target]目前每十分鐘會尋找要匯入的[!UICONTROL Content Fragments]。 匯入的[!UICONTROL Content Fragment]應該會在10分鐘內於[!DNL Target]內提供，但此時間範圍應會縮短。
* [!UICONTROL Content Fragment]已匯入至[!DNL Target]做為JSON選件。 [!UICONTROL Content Fragment]「主要」版本仍保留在[!DNL AEM]中。 您無法在[!DNL Target]中編輯[!UICONTROL Content Fragment]。
* 您無法使用[!DNL Adobe I/O]建立[!UICONTROL Content Fragments]。 使用AEM建立[!UICONTROL Content Fragments]，如上所述。
* 如果您在AEM中更新[!UICONTROL Content Fragment]，則必須發佈[!UICONTROL Content Fragment]並再次匯出至[!DNL Target]，以便[!DNL Target]可以使用最新變更。

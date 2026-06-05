---
keywords: 體驗;JSON;AEM;Adobe Experience Manager;匯出至 Adobe Target;內容片段;片段;CF;cf;無頭;個人化;實驗
description: 瞭解如何在 [!DNL Adobe Target] 活動中使用 [!DNL Adobe Experience Manager] [!UICONTROL 內容片段]。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 內容片段]？
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
TQID: https://experienceleague.adobe.com/tb500kFSZoR3czs10Gs3EIOWEX2ybnd7tSWwDmWSMWQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 775
ht-degree: 20%

---

# AEM [!UICONTROL 內容片段]

在[!DNL Target]活動中，使用在[!DNL Adobe Experience Manager] (AEM)中建立的[!UICONTROL 內容片段] (CF)，以協助Headless個人化和實驗。

## 考量事項

當您在[!DNL Target]中使用AEM [!UICONTROL 內容片段]時，請考量下列事項：

* 您需為 [!DNL Adobe Experience Manager as a Cloud Service] 客戶才能使用此功能。 如需詳細資訊，請參閱下方的[要求](#section_AE6F0971E1574B3AA324003599B96E5A)。
* [!UICONTROL 體驗片段]和[!UICONTROL 內容片段]可用於下列活動型別：

   * [[!UICONTROL A/B 測試]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL 自動分配]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL 自動鎖定目標]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL 體驗鎖定] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL 體驗片段]和[!UICONTROL 內容片段]不適用於下列活動型別：

   * [[!UICONTROL 多變數測試] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL 推薦]](/help/main/c-recommendations/recommendations.md)

* 您只能使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，在[!DNL Target]個活動中使用[!UICONTROL 內容片段]。 您&#x200B;*無法*&#x200B;在使用[!UICONTROL 視覺化體驗撰寫器] (VEC)的[!DNL Target]活動中使用[!UICONTROL 內容片段]。

若要進一步瞭解AEM [!UICONTROL 內容片段]和[!UICONTROL 體驗片段]，請參閱[AEM [!UICONTROL 體驗片段]和[!UICONTROL 內容片段]總覽](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 要求 {#requirements}

您必須使用[[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=zh-Hant){target=_blank}。 您的客戶代表可協助確認您是否符合使用此功能的要求：

請和 [Adobe Target 客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)聯絡，以啟用整合並取得驗證的詳細資訊。

## 設定和使用[!DNL AEM]中的[!UICONTROL 內容片段] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

若要匯出[!UICONTROL 內容片段]以用於[!DNL Target]活動，您必須在AEM中執行一些初步步驟。 如需詳細資訊，請參閱&#x200B;*Adobe Target as a Cloud Service檔案*&#x200B;中的[將內容片段匯出至Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=zh-Hant){target=_blank}。

如需有關設計、建立、組織和發佈[!UICONTROL 內容片段]的資訊，請參閱[Experience Manager as a Cloud Service檔案](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=zh-Hant){target=_blank}中的[[!UICONTROL 內容片段]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=zh-Hant){target=_blank}和[使用內容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=zh-Hant){target=_blank}。

## 在[!DNL Target]個活動中使用[!UICONTROL 內容片段] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行先前的工作後，[!UICONTROL 內容片段]會顯示在[!DNL Target]的[!UICONTROL 選件]頁面上。

[!DNL Target]目前每十分鐘會尋找要匯入的[!UICONTROL 內容片段]。 匯入的[!UICONTROL 內容片段]應該會在10分鐘內於[!DNL Target]內提供，但此時間範圍應會縮短。

[!UICONTROL 內容片段]已匯入至[!DNL Target]做為JSON選件。 [!UICONTROL 內容片段]「主要」版本仍保留在[!DNL AEM]中。 您無法在[!DNL Target]中編輯[!UICONTROL 內容片段]。

您可以依[!UICONTROL HTML XF]、[!UICONTROL JSON XF]和[!UICONTROL 內容片段]來篩選和搜尋，以協助您區分匯出至[!DNL Target]的不同選件型別。

![依據內容片段類型進行篩選：Target UI 中的 HTML 或 JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以將滑鼠停留在清單中的[!UICONTROL 體驗片段]上，然後按一下[!UICONTROL 檢視]圖示![資訊圖示](/help/main/assets/icons/InfoOutline.svg)，檢視有關[!UICONTROL 內容片段]的其他資訊，包括其[!UICONTROL 名稱]、[!UICONTROL 型別]、[!UICONTROL 選件ID]、[!UICONTROL 選件路徑]和上次修改資訊。 按一下[!UICONTROL [!UICONTROL 檢視完整詳細資料]]以檢視參考此優惠方案的活動。

您只能使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，在[!DNL Target]個活動中使用[!UICONTROL 內容片段]。 您&#x200B;*無法*&#x200B;在使用[視覺化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)的[!DNL Target]活動中使用[!UICONTROL 內容片段]。 [!UICONTROL 內容片段]會匯出為[!DNL Target]中的JSON，因此無法在使用VEC建立的活動中使用。

>[!TIP]
>
>使用包含[!UICONTROL 內容片段]的人工智慧、機器學習與建議：
>
>* 若要充分利用[!DNL Target] AI和ML功能，您可以在建立[!UICONTROL A/B測試]活動時選取[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
>
>* [!UICONTROL 在[!DNL Recommendations]活動中不支援內容片段]。 不過，若要使用[!UICONTROL 內容片段]提供建議，您可以建立[!UICONTROL A/B測試]活動（包括[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]）或[!UICONTROL 體驗鎖定目標] (XT)活動，以及[包含建議作為選件](/help/main/c-recommendations/recommendations-as-an-offer.md)。

**使用[!UICONTROL 表單式體驗撰寫器]使用[!UICONTROL 內容片段]：**

1. 在[!DNL Target]中，在[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中建立或編輯體驗時，請在頁面上選取您要插入[!DNL AEM]內容的位置，然後選取「**[!UICONTROL 變更內容片段]**」以顯示「[!UICONTROL 選擇內容片段]」清單。

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   [!UICONTROL 內容片段]清單顯示在[!DNL AEM]中建立的內容，現在可從[!DNL Target]中以原生方式使用。

1. 選取所需的[!UICONTROL 內容片段]，然後按一下&#x200B;**[!UICONTROL 儲存]**。
1. 完成活動的設定。

## 其他資訊

* [!DNL Target]目前每十分鐘會尋找要匯入的[!UICONTROL 內容片段]。 匯入的[!UICONTROL 內容片段]應該會在10分鐘內於[!DNL Target]內提供，但此時間範圍應會縮短。
* [!UICONTROL 內容片段]已匯入至[!DNL Target]做為JSON選件。 [!UICONTROL 內容片段]「主要」版本仍保留在[!DNL AEM]中。 您無法在[!DNL Target]中編輯[!UICONTROL 內容片段]。
* 您無法使用[!DNL Adobe I/O]建立[!UICONTROL 內容片段]。 使用AEM建立[!UICONTROL 內容片段]，如上所述。
* 如果您在AEM中更新[!UICONTROL 內容片段]，[!UICONTROL 內容片段]必須發佈並再次匯出到[!DNL Target]，以便[!DNL Target]可以使用最新的變更。

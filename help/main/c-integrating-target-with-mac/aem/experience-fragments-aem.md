---
keywords: 體驗；JSON；AEM；Adobe Experience Manager；匯出至 Adobe Target；體驗片段；片段；XF
description: 了解如何在  [!DNL Adobe Target]  活動中使用 [!DNL Adobe Experience Manager] [!UICONTROL 體驗片段]。
title: 我如何使用  [!DNL Adobe Experience Manager]  (AEM) [!UICONTROL 體驗片段]？
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: 7c81362a82ca6692bb8c183b8e8fc50c6329e2e8
workflow-type: ht
source-wordcount: '1352'
ht-degree: 100%

---

# AEM [!UICONTROL 體驗片段]

使用在 [!DNL Target] 活動的 [!DNL Adobe Experience Manager] (AEM) 中建立的[!UICONTROL 體驗片段] (XF)，以輔助最佳化和個人化。

## 考量事項

在 [!DNL Target] 中使用 AEM [!UICONTROL 體驗片段]時，請考慮以下事項：

* 您需為 [!DNL Adobe Experience Manager] (AEM) 客戶才能使用此功能。如需詳細資訊，請參閱下方的[要求](#section_AE6F0971E1574B3AA324003599B96E5A)。
* [!UICONTROL 體驗片段]和[!UICONTROL 內容片段]適用於以下活動類型：

   * [[!UICONTROL A/B 測試]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL 自動分配]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL 自動鎖定目標]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL 自動個人化](AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL 體驗鎖定] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL 體驗片段]和[!UICONTROL 內容片段]不適用於以下活動類型：

   * [[!UICONTROL 多變數測試] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* 您可以使用[可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 和[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，在 [!DNL Target] 活動中取用[!UICONTROL 體驗片段]。

若要了解有關 AEM [!UICONTROL 體驗片段]和內容片段的詳細資訊，請參閱 [AEM [!UICONTROL 體驗片段]和內容片段概觀](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 要求 {#requirements}

您必須在 [!DNL Target] 中佈建[!UICONTROL 體驗片段]功能。此外，您必須使用 [!DNL AEM] as a Cloud Service 或 [!DNL AEM] 6.4 (或更新版本)。您的客戶代表可協助確認您是否符合使用此功能的要求。

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帳戶

[!DNL Adobe Experience Manager] 6.3 和 6.4 的生命週期已結束，不再受支援 (購買了延長支援的客戶除外)。

請和 [Adobe Target 客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)聯絡，以啟用整合並取得驗證的詳細資訊。

## 在 [!DNL AEM] 中建立和設定[!UICONTROL 體驗片段]  {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

為了在 [!DNL Target] 中使用[!DNL AEM][!UICONTROL 體驗片段]，您必須執行下列步驟：

### 步驟 1：將 [!DNL AEM] 和 [!DNL Target] 整合

如需詳細資訊，請參閱：

* **AEM as a Cloud Service**：[在 *Experience Manager as a Cloud Service* 中和 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} 整合的指南。
* **Adobe I/O**：[使用 Adobe I/0 和 Adobe Target 整合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html){target=_blank} (參閱&#x200B;*管理使用手冊*&#x200B;文件)。
* **[!DNL AEM]6.5**：[選擇使用 Adobe Analytics 和 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=zh-Hant){target=_blank} (參閱 *Adobe Experience Manager 6.5* 文件)。
* **[!DNL AEM]6.4**：[選擇使用 Adobe Analytics 和 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank} (參閱 *Adobe Experience Manager 6.4* 文件)。

### 步驟 2：建立體驗片段

[!UICONTROL 體驗片段]是在 [!DNL AEM] 中建立的。如需詳細資訊，請參閱：

* **AEM as a Cloud Service**：[[!UICONTROL 體驗片段]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=zh-Hant){target=_blank} (參閱 *Experience Manager as a Cloud Service* 指南)。
* **[!DNL AEM]6.5**：[[!UICONTROL 體驗片段]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=zh-Hant){target=_blank} (參閱 *Adobe Experience Manager 6.5* 文件)。
* **[!DNL AEM]6.4**：[[!UICONTROL 體驗片段]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=zh-Hant){target=_blank} (參閱 *Adobe Experience Manager 6.4* 文件)。

### 步驟 3：設定 [!DNL AEM] 以和 [!DNL Target] 共用體驗片段

1. 從 [!DNL AEM] 內部選取所需的體驗片段或其收納檔案夾，然後按一下&#x200B;**[!UICONTROL 屬性]**。
2. 按一下&#x200B;**[!UICONTROL 雲端服務]**&#x200B;索引標籤，然後從&#x200B;**[!UICONTROL 雲端服務設定]**&#x200B;下拉式清單中，選取 **[!UICONTROL Adobe Target]**。

   上一步假設您的組織中有人已建立 [!DNL Adobe Target] 設定。

3. 按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

### 步驟 4：發佈[!UICONTROL 體驗片段]並將其匯出至 [!DNL Target]

依據您的 [!DNL AEM] 版本的不同，請參閱以下連結以取得逐步說明：

* **AEM as a Cloud Service**：[匯出[!UICONTROL 體驗片段]至 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=zh-Hant){target=_blank} (參閱 *Experience Manager as a Cloud Service* 指南)。
* **[!DNL AEM]6.5**：[匯出體驗片段至 Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=zh-Hant){target=_blank} (參閱 *Adobe Experience Manager 6.5* 文件)。
* **[!DNL AEM]6.4**：[匯出體驗片段至 Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank} (參閱 *Adobe Experience Manager 6.4* 文件)。

## 在 [!DNL Target] 活動中使用[!UICONTROL 體驗片段] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行先前的工作之後，[!UICONTROL 體驗片段]會顯示在 [!DNL Target] 的[!UICONTROL 「選件」]頁面中。

[!DNL Target] 目前每十分鐘會尋找要匯入的[!UICONTROL 體驗片段]。十分鐘內應該就能在 [!DNL Target] 中看到匯入的[!UICONTROL 體驗片段]，但日後所需時間應該會縮短。

[!UICONTROL 體驗片段]目前會以 HTML 或 JSON 選件的形式匯入 [!DNL Target]。該[!UICONTROL 體驗片段]的「主要」版本會留在 [!DNL AEM] 中。您無法在 [!DNL Target]中編輯[!UICONTROL 體驗片段]。

您可以依據 [!UICONTROL HTML XF] 和 [!UICONTROL JSON XF] 進行篩選和搜尋，以協助您區分匯出至 [!DNL Target] 的體驗片段類型。

![依據體驗片段類型進行篩選：Target UI 中的 HTML 或 JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以將游標停留在清單中的[!UICONTROL 體驗片段]上方，然後按一下[!UICONTROL 檢視]圖示![資訊圖示](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png)，即可查看有關[!UICONTROL 體驗片段]的其他資訊，包括其[!UICONTROL 名稱]、[!UICONTROL 類型]、[!UICONTROL 選件識別碼]、[!UICONTROL 選件路徑]和上次修改資訊。按一下[!UICONTROL 選件使用情況]索引標籤，以查看參照此選件的活動。

![體驗片段資訊快顯視窗](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

您可以使用[可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 和[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，在 [!DNL Target] 活動中取用[!UICONTROL 體驗片段]。


>[!TIP]
>
>使用人工智慧、機器學習和[!UICONTROL 體驗片段]的建議：
>
>* 若要充分利用 [!DNL Target] AI 和 ML 功能，您可以在建立活動時選取[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自動個人化](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
>
>* 在 [!DNL Recommendations] 活動中不支援[!UICONTROL 體驗片段]。但是，若要使用建議的[!UICONTROL 體驗片段]，您可建立 [!UICONTROL A/B 測試] (包括[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]) 或是[!UICONTROL 體驗鎖定目標] (XT) 活動並[包含選件形式的建議](/help/main/c-recommendations/recommendations-as-an-offer.md)。


**使用 VEC 來取用體驗片段：**

1. 在 [!DNL Target] 中，在[視覺化體驗撰寫器](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中建立或編輯體驗時，請按一下頁面上要插入 [!DNL AEM] 內容的位置，然後選取需要的選項以顯示[!UICONTROL 選擇體驗片段]清單。

   * [!UICONTROL 插入在前]
   * [!UICONTROL 插入在後]
   * [!UICONTROL 交換體驗片段]

   該[!UICONTROL 體驗片段]清單會顯示在 [!DNL AEM] 中建立的內容，現在已可從 [!DNL Target] 內取得原生清單。

   >[!NOTE]
   >
   >[!UICONTROL 「交換體驗片段」]選項不適用於影像。如果您想將此選項用於影像，請按一下包含所需影像的容器元素。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 選取需要的[!UICONTROL 體驗片段]，然後按一下&#x200B;**[!UICONTROL 完成]**。
1. 完成活動的設定。

   如需有關設定各種活動類型的詳細資訊，請參閱下列主題:

   * **A/B 測試:** [建立 A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動分配:** [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動鎖定目標：**[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalization (AP):**[建立 Automated Personalization 活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **體驗鎖定目標 (XT):** [建立體驗鎖定目標活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **A/B 測試或 XT 活動中的建議：**[選件形式的建議](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL 在 [!DNL Target] 中匯出為 JSON 的體驗片段]不能用於使用 VEC 建立的活動中；VEC 式活動僅支援 HTML [!UICONTROL 體驗片段]。如果您想使用 JSON [!UICONTROL 體驗片段]，請在使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)建立的活動中使用它們。

**[!UICONTROL 使用表單式體驗撰寫器來取用體驗片段]:**

1. 在 [!DNL Target] 中，在[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中建立或編輯體驗時，請選取頁面上要插入 [!DNL AEM] 內容的位置，然後選取&#x200B;**[!UICONTROL 變更體驗片段]**&#x200B;以顯示[!UICONTROL 選擇體驗片段]清單。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   該[!UICONTROL 體驗片段]清單會顯示在 [!DNL AEM] 中建立的內容，現在已可從 [!DNL Target] 內取得原生清單。

1. 選取需要的[!UICONTROL 體驗片段]，然後按一下&#x200B;**[!UICONTROL 儲存]**。
1. 完成活動的設定。

## 其他資訊

* [!DNL Target] 目前每十分鐘會尋找要匯入的[!UICONTROL 體驗片段]。十分鐘內應該就能在 [!DNL Target] 中看到匯入的[!UICONTROL 體驗片段]，但日後所需時間應該會縮短。
* [!UICONTROL 體驗片段]目前會以 HTML 或 JSON 選件的形式匯入 [!DNL Target]。該[!UICONTROL 體驗片段]的「主要」版本會留在 [!DNL AEM] 中。您無法在 [!DNL Target]中編輯[!UICONTROL 體驗片段]。
* 你無法使用 [!DNL Adobe I/O] 建立[!UICONTROL 體驗片段]。使用 AEM 建立[!UICONTROL 體驗片段]，如上所述。
* 如果您更新 AEM 中的[!UICONTROL 體驗片段]，必須再次將體驗片段發佈並匯出至 [!UICONTROL ，這樣 ] 才能使用最新的變更。[!DNL Target][!DNL Target]

## 從匯出至 [!UICONTROL Target] 的[!UICONTROL 體驗片段]中移除 ClientLib 和無關的 HTML

在 AEM 提供的頁面上使用包含 [!DNL Target] 的[!UICONTROL 體驗片段]選件時，目標頁面已包含所有必要的用戶端資料庫。另請注意，選件中無關的 HTML 元素也不是必要的。

有時，整個 HTML 頁面都會包覆[!UICONTROL 體驗片段]並導致問題。請確保[!UICONTROL 體驗片段]是一小段 HTML，而不是包含 HTML、HEAD、BODY 等的完整 HTML 頁面。

如需詳細資訊，請參閱以下部落格貼文：[AEM 6.5：從匯出至 Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank} 的[!UICONTROL 體驗片段]移除 ClientLibs。

## 訓練影片：將 AEM [!UICONTROL 體驗片段]用於 [!DNL Adobe Target] 

以下影片會向您展示如何設定和使用[!UICONTROL 體驗片段]：

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>已移除在 4:54 討論的 [!DNL AEM] 深度連結功能。

如需更多詳細資訊，請參閱[搭配使用[!UICONTROL 體驗片段]和 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) (見 *AEM Sites 影片和教學課程*&#x200B;頁面)。

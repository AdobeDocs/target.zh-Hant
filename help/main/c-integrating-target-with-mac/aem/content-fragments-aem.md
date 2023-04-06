---
keywords: 體驗;JSON;AEM;Adobe Experience Manager;匯出至 Adobe Target;內容片段;片段;CF;cf;headless;個人化;實驗
description: 了解如何在  [!DNL Adobe Target]  活動中使用 [!DNL Adobe Experience Manager] [!UICONTROL 內容片段]。
title: 我如何使用  [!DNL Adobe Experience Manager]  (AEM) [!UICONTROL 內容片段]？
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="What are Target Beta release features?"
feature: Integrations
source-git-commit: 01ade219f81bc1d43fd13321e8fc4f23b230856c
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 100%

---

# AEM [!UICONTROL 內容片段]

在 [!DNL Target] 活動中使用 [!DNL Adobe Experience Manager] (AEM) 中建立的[!UICONTROL 內容片段] (CF)，以協助 Headless 個人化和實驗。

用於 Headless 個人化和實驗的 AEM 內容片段

>[!NOTE]
>
>此功能的預定發行日期為 2023 年 4 月 6 日。

>[!NOTE]
>
>在 [!DNL Target] 中使用 AEM [!UICONTROL 內容片段]時，請考慮以下事項：
> 
>* 您需為 [!DNL Adobe Experience Manager] (AEM) 客戶才能使用此功能。如需詳細資訊，請參閱下方的[要求](#section_AE6F0971E1574B3AA324003599B96E5A)。
>
>* 此功能適用於以下活動類型：[!UICONTROL A/B 測試]、[!UICONTROL 自動分配]、[!UICONTROL 自動鎖定目標]、[!UICONTROL Automated Personalization] (AP) 和[!UICONTROL 體驗鎖定目標] (XT)。此功能無法在[!UICONTROL 多變數測試] (MVT) 和 [!UICONTROL Recommendations] 活動中使用。
>
>* 您只能在使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)的 [!DNL Target] 活動中取用[!UICONTROL 內容片段]。您無法使用[!UICONTROL 視覺化體驗撰寫器] (VEC) 來取用[!UICONTROL 內容片段]。


若要了解有關 AEM [!UICONTROL 內容片段]和[!UICONTROL 體驗片段]的詳細資訊，請參閱 [AEM[!UICONTROL 體驗片段]和[!UICONTROL 內容片段]概觀](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 要求 {#requirements}

您必須在 [!DNL Target] 中佈建[!UICONTROL 內容片段]功能。此外，您必須使用 [!DNL AEM] as a Cloud Service。您的客戶代表可協助確認您是否符合使用此功能的要求：

請和 [Adobe Target 客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)聯絡，以啟用整合並取得驗證的詳細資訊。

## 在 [!DNL AEM] 中設定並使用[!UICONTROL 內容片段] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

若要匯出[!UICONTROL 內容片段]以用於 [!DNL Target] 活動，您必須在 AEM 中執行一些預備步驟。如需詳細資訊，請參閱 *Experience Manager as a Cloud Service 文件*&#x200B;中的[匯出內容片段至 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank}。請注意，此連結在發行日 (2023 年 4 月 12 日) 即可供使用

如需有關設計、建立、策劃和發佈[!UICONTROL 內容片段]的資訊，請參閱[[!UICONTROL 內容片段]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=zh-Hant){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}。

## 在 [!DNL Target] 活動中使用 [!UICONTROL 內容片段]。 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行先前的工作之後，[!UICONTROL 內容片段]會顯示在 [!DNL Target] 中的[!UICONTROL 「選件」]頁面上。

[!DNL Target] 目前每十分鐘會尋找要匯入的[!UICONTROL 內容片段]。十分鐘內應該就能在 [!DNL Target] 中看到匯入的[!UICONTROL 內容片段]，但日後所需時間應該會縮短。

會將此[!UICONTROL 內容片段]匯入[!DNL Target]為 JSON 選件。該[!UICONTROL 內容片段]的「主要」版本會留在 [!DNL AEM] 中。您無法在 [!DNL Target] 中編輯[!UICONTROL 內容片段]。

您可以依據 [!UICONTROL HTML XF]、[!UICONTROL JSON XF] 和[!UICONTROL 內容片段]進行篩選和搜尋，以協助您區分匯出至 [!DNL Target] 的不同選件。

![依據內容片段類型進行篩選：Target UI 中的 HTML 或 JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以將游標停留在清單中的[!UICONTROL 內容片段]上方，然後按一下[!UICONTROL 檢視]圖示![資訊圖示](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png)，即可查看有關[!UICONTROL 內容片段]的其他資訊，包括其 [!UICONTROL AEM 路徑]和 [!UICONTROL AEM 深度連結]。按一下[!UICONTROL 選件使用情況]索引標籤，以查看參照此選件的活動。

![內容片段資訊快顯視窗](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

您只能在使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)的 [!DNL Target] 活動中取用[!UICONTROL 內容片段]。您&#x200B;*無法*&#x200B;使用[視覺化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 在 [!DNL Target] 活動中取用[!UICONTROL 內容片段]。[!UICONTROL 內容片段]會在 [!DNL Target] 中匯出為 JSON 並且不能用於使用 VEC 建立的活動中。

>[!TIP]
>
>使用人工智慧、機器學習和[!UICONTROL 內容片段]的建議：
>
>* 若要充分利用 [!DNL Target] AI 和 ML 功能，您可以在建立 A/B 測試時選取[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[「自動個人化](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
>
>* 在 [!DNL Recommendations] 活動中不支援[!UICONTROL 內容片段]。但是，若要使用建議的[!UICONTROL 內容片段]，您可建立 [!UICONTROL A/B 測試] (包括[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]) 或是[!UICONTROL 體驗鎖定目標] (XT) 活動並[包含選件形式的建議](/help/main/c-recommendations/recommendations-as-an-offer.md)。


**使用[!UICONTROL 表單式體驗撰寫器]來取用[!UICONTROL 內容片段]：**

1. 在 [!DNL Target] 中，在[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中建立或編輯體驗時，請選取頁面上要插入 [!DNL AEM] 內容的位置，然後選取&#x200B;**[!UICONTROL 變更內容片段]**&#x200B;以顯示[!UICONTROL 選擇內容片段]清單。

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   該[!UICONTROL 內容片段]清單會顯示在 [!DNL AEM] 中建立的內容，現在已可從 [!DNL Target] 內取得原生清單。

1. 請選取所需的內容片段，然後按一下&#x200B;**[!UICONTROL 儲存]**。
1. 完成活動的設定。

## 考量事項 {#considerations}

* [!DNL Target] 目前每十分鐘會尋找要匯入的[!UICONTROL 內容片段]。十分鐘內應該就能在 [!DNL Target] 中看到匯入的[!UICONTROL 內容片段]，但日後所需時間應該會縮短。
* 會將此[!UICONTROL 內容片段]匯入[!DNL Target]為 JSON 選件。此[!UICONTROL 內容片段]的「主要」版本會留在 [!DNL AEM] 中。您無法在 [!DNL Target] 中編輯[!UICONTROL 內容片段]。
* 你無法使用 [!DNL Adobe I/O] 建立[!UICONTROL 內容片段]。使用 AEM 建立[!UICONTROL 內容片段]，如上所述。
* 如果您更新 AEM 中的[!UICONTROL 內容片段]，必須再次將[!UICONTROL 內容片段]發佈並匯出至 [!DNL Target]，這樣 [!DNL Target] 才能使用最新的變更。
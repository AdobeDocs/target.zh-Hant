---
keywords: 體驗； JSON;AEM;Adobe Experience Manager；匯出至Adobe Target；內容片段；片段；CF;CF
description: 了解如何使用 [!DNL Adobe Experience Manager] [!UICONTROL 內容片段] in [!DNL Adobe Target] 活動。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 內容片段]?
feature: Integrations
source-git-commit: cdb0e3f3e1ebb2f9076d3994aed533bd7c296fad
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 2%

---

# AEM [!UICONTROL 內容片段]

使用 [!UICONTROL 內容片段] (CF)建立於 [!DNL Adobe Experience Manager] (AEM) [!DNL Target] 活動來協助最佳化或個人化。

>[!NOTE]
>
>使用AEM時，請考量下列事項 [!UICONTROL 內容片段] in [!DNL Target]:
> 
>* 此功能需要您 [!DNL Adobe Experience Manager] (AEM)客戶。 如需詳細資訊，請參閱 [需求](#section_AE6F0971E1574B3AA324003599B96E5A) 下方。
>
>* 此功能適用於下列活動類型： [!UICONTROL A/B測試], [!UICONTROL 自動分配], [!UICONTROL 自動鎖定目標], [!UICONTROL Automated Personalization] （美聯社）和 [!UICONTROL 體驗鎖定] (XT)。 此功能在 [!UICONTROL 多變數測試] (MVT)和 [!UICONTROL Recommendations] 活動。
>
>* 您可以 [!UICONTROL 內容片段] in [!DNL Target] 活動使用 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md) 只有。 您不能使用 [!UICONTROL 內容片段] 使用 [!UICONTROL 可視化體驗撰寫器] (VEC)。


深入了解AEM [!UICONTROL 內容片段] 和 [!UICONTROL 體驗片段]，請參閱 [AEM [!UICONTROL 體驗片段] 和 [!UICONTROL 內容片段] 概述](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## 要求 {#requirements}

您必須布建 [!UICONTROL 內容片段] 功能 [!DNL Target]. 此外，您必須使用 [!DNL AEM] as a Cloud Service。 您的客戶代表可協助確認您是否符合使用此功能的要求。

連絡人 [Adobe Target客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 啟用整合併提供驗證詳細資料。

## 配置和使用 [!UICONTROL 內容片段] in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

要導出 [!UICONTROL 內容片段] 用於 [!DNL Target] 活動，您必須在AEM中執行一些初步步驟。 如需詳細資訊，請參閱 [將內容片段匯出至Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}.

如需設計、建立、組織和發佈的相關資訊 [!UICONTROL 內容片段]，請參閱 [[!UICONTROL 內容片段]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=en){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}.

## 使用 [!UICONTROL 內容片段] in [!DNL Target] 活動 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

執行上述工作後， [!UICONTROL 內容片段] 顯示於 [!UICONTROL 選件] 頁面 [!DNL Target].

[!DNL Target] 當前查找 [!UICONTROL 內容片段] 每十分鐘匯入一次。 匯入的 [!UICONTROL 內容片段] 應可在 [!DNL Target] 10分鐘內，但此時間範圍會日後縮短。

此 [!UICONTROL 內容片段] 匯入 [!DNL Target] 作為JSON選件。 那個 [!UICONTROL 內容片段] 「主要」版本仍保留在 [!DNL AEM]. 您無法編輯 [!UICONTROL 內容片段] in [!DNL Target].

您可以依 [!UICONTROL HTMLXF], [!UICONTROL JSON XF]，和 [!UICONTROL 內容片段] 可協助您區分匯出至的不同選件類型 [!DNL Target].

![依內容片段類型篩選：HTML或JSON（在Target UI中）](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以暫留在 [!UICONTROL 內容片段] 在清單中，按一下 [!UICONTROL 檢視] 圖示 ![資訊圖示](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) 若要查看 [!UICONTROL 內容片段]，包括 [!UICONTROL AEM路徑] 和 [!UICONTROL AEM深層連結]. 按一下 [!UICONTROL 優惠方案使用量] 索引標籤來查看參考此選件的活動。

![內容片段資訊快顯視窗](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

您可以 [!UICONTROL 內容片段] in [!DNL Target] 活動使用 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md) 只有。 您 *不能* 消費 [!UICONTROL 內容片段] in [!DNL Target] 活動使用 [可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)。 [!UICONTROL 內容片段] 在中匯出為JSON [!DNL Target] 和無法用於使用VEC建立的活動。

>[!TIP]
>
>搭配使用人工智慧、機器學習和建議 [!UICONTROL 內容片段]:
>
>* 若要充分使用 [!DNL Target] AI和ML功能，您可以選取 [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) 或 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 建立A/B測試時。
>
>* [!UICONTROL 內容片段] 不支援 [!DNL Recommendations] 活動。 不過，若要使用 [!UICONTROL 內容片段] 您可以為建議建立 [!UICONTROL A/B測試] 活動(包括 [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標])或 [!UICONTROL 體驗鎖定] (XT)活動和 [將建議納入選件](/help/main/c-recommendations/recommendations-as-an-offer.md).


**要使用 [!UICONTROL 內容片段] 使用 [!UICONTROL 表單式體驗撰寫器]:**

1. 在 [!DNL Target]，在中建立或編輯體驗時 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)，請在頁面上選取您要插入的位置 [!DNL AEM] 內容，然後選取 **[!UICONTROL 變更內容片段]** 顯示 [!UICONTROL 選擇內容片段] 清單。

   ![content_fragment_list影像](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   此 [!UICONTROL 內容片段] 清單顯示中建立的內容 [!DNL AEM] 現在可從內取得原生功能 [!DNL Target].

1. 選取所需 [!UICONTROL 內容片段]，然後按一下 **[!UICONTROL 儲存]**.
1. 完成活動的設定。

## 考量事項 {#considerations}

* [!DNL Target] 當前查找 [!UICONTROL 內容片段] 每十分鐘匯入一次。 匯入的 [!UICONTROL 內容片段] 應可在 [!DNL Target] 10分鐘內，但此時間範圍會日後縮短。
* 此 [!UICONTROL 內容片段] 匯入 [!DNL Target] 作為JSON選件。 此 [!UICONTROL 內容片段] 「主要」版本仍保留在 [!DNL AEM]. 您無法編輯 [!UICONTROL 內容片段] in [!DNL Target].
* 您無法建立 [!UICONTROL 內容片段] 使用 [!DNL Adobe I/O]. 建立 [!UICONTROL 內容片段] 使用AEM，如上所述。
* 如果您更新 [!UICONTROL 內容片段] 在AEM中， [!UICONTROL 內容片段] 必須發佈並匯出至 [!DNL Target] aw [!DNL Target] 可使用最新變更。
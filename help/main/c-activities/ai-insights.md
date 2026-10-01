---
keywords: AI深入分析；Experimentation Accelerator；商機；活動概覽
description: 瞭解如何在Adobe Target活動概觀中使用AI產生的深入分析和來自Experimentation Accelerator的最佳化機會。
title: 活動概觀中的AI深入分析
feature: Activities
badge: label="Beta" type="Informative"
source-git-commit: 643b30757e9212388dcb6921580f86feb0704338
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 16%
---
# AI深入分析

>[!AVAILABILITY]
>
>AI深入分析功能目前是以Beta版的形式提供。
></br>
>**[!UICONTROL AI深入分析]**&#x200B;區段僅適用於具有&#x200B;**[!UICONTROL 手動]**&#x200B;流量分配的&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動。

您的&#x200B;**[!UICONTROL 活動概覽]**&#x200B;中的&#x200B;**[!UICONTROL AI深入分析]**&#x200B;功能表可讓您存取深入分析和最佳化機會。 使用此標籤來檢閱實驗學習、比較處理，並識別可能改善轉換率的變更。

## 設定AI見解和商機

>[!CONTEXTUALHELP]
>id="target_ai_insights_primary_metric"
>title="主要量度"
>abstract="主要量度會自動從報告設定中提取。 若要進行變更，請在「目標和設定」下方修改目標量度。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_hypothesis"
>title="假設"
>abstract="假設是您定義的陳述，用來說明實驗的預期結果。 包括說明要變更的內容及位置，然後指出您預期變更的量度以及變更方式。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_treatment_details"
>title="體驗詳細資料"
>abstract="體驗詳細資訊會顯示使用者符合體驗資格時體驗的外觀。 您可以為所有實驗檢閱這些影像。 有些實驗可能會要求您確認影像或在需要時進行取代。"

在存取AI產生的深入分析和機會之前，您必須先透過確認主要量度、假設和體驗熒幕擷取畫面來設定活動。

主要量度會自動從報表設定中提取，且取決於您設定目標與設定的方式。 您必須在AI見解面板中建立假設。 [了解更多](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)

1. 在[!DNL Adobe Target]中開啟您的活動。

1. 選取&#x200B;**[!UICONTROL AI深入分析]**&#x200B;功能表以開啟設定面板。

1. 按一下![](assets/do-not-localize/Smock_Edit_18_N.svg)為您的實驗建立假設。

   ![](assets/ai-insights-7.png)

1. 透過描述已進行的變更以及變更將如何影響主要量度來輸入您的假設。

   按一下&#x200B;**[!UICONTROL 「儲存」]**。

1. 在&#x200B;**[!UICONTROL 體驗詳細資料]**&#x200B;底下，按一下卡片以新增您體驗的熒幕擷圖。

   >[!NOTE]
   >有些影像可能已自動擷取。 若是如此，請按一下&#x200B;**[!UICONTROL 確認]**&#x200B;以確認熒幕擷圖。

   ![](assets/ai-insights-1.png)

1. 選取&#x200B;**[!UICONTROL 上傳影像]**&#x200B;以從您每個體驗的本機檔案上傳偏好的熒幕擷取畫面。

   ![](assets/ai-insights-2.png)

1. 複製預覽連結或直接開啟以預覽體驗。

1. 每個體驗取得熒幕擷圖後，請檢閱詳細資料，然後按一下&#x200B;**[!UICONTROL 確認]**&#x200B;以完成設定。

設定完成後，您的活動便可產生商機。 實驗具有足夠的資料進行統計驗證且必要的實驗詳細資訊獲得確認後，分析即可使用。

## 洞察

>[!CONTEXTUALHELP]
>id="target_ai_insights"
>title="洞察"
>abstract="實驗洞察是當實驗資料達到統計顯著性時，AI 所獲得的學習成果。"

實驗見解是衍生自此實驗的AI產生的學習。 當實驗達到統計顯著性並提供促使其成功的背景資訊後，這些見解就可供使用。 它們會醒目提示成功體驗中與控制不同的關鍵屬性，而且可能會影響結果。

1. 按一下卡片以存取&#x200B;**[!UICONTROL 深入分析]**&#x200B;功能表。

   ![](assets/ai-insights-3.png)

1. 瀏覽您的AI產生的深入分析，以檢閱實驗學習，並將成功體驗與控制體驗進行比較。

   ![](assets/ai-insights-4.png)

1. 在&#x200B;**[!UICONTROL 中，是什麼讓此體驗獲勝？]**，請檢閱說明此體驗優於控制的原因的詳細資料。

## 機會

>[!CONTEXTUALHELP]
>id="target_ai_insights_opportunities"
>title="機會"
>abstract="實驗機會是AI建議的體驗想法，根據在您的實驗熒幕擷取畫面和結果中找到AI的模式。"

**[!UICONTROL 機會]**&#x200B;面板會顯示AI產生的建議，這些建議旨在改善測試效能並符合更廣泛的業務目標和KPI。

1. 瀏覽建議的商機，並選取您要檢閱的商機。

   ![](assets/ai-insights-5.png)

1. 選取商機，以開啟「商機詳細資料」視窗，其中概述特定體驗或變數。 此檢視包括：

   * 用來產生商機的目前體驗影像。

   * AI產生的假設，可解釋建議體驗的預期結果以及它可能會改善效能的原因。

   * 如何在您的體驗中實作建議，以及衡量對所選量度之影響的指引。

   ![](assets/ai-insights-6.png)


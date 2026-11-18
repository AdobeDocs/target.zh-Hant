---
keywords: 重複資料刪除；允許重複專案；排除重複選件；自動個人化；不允許重複選件；排除；預設內容；
description: 管理[!UICONTROL Automated Personalization] (AP)活動中的排除專案。
title: 如何管理[!UICONTROL Automated Personalization]活動中的排除專案？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
TQID: 'https://experienceleague.adobe.com/ERpNwQPsIRBmU0vTZbGa-lYg30BYl-uJxA8UT0f6060'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 4%
---
# 管理排除項目 {#manage-exclusions}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中防止重複選件、排除特定體驗，以及排除預設內容。

>[!ENDSHADEBOX]

排除專案可控制&#x200B;**[!UICONTROL Automated Personalization]** (AP)活動提供哪些優惠方案及體驗。 它們可防止相同選件顯示兩次、移除無法搭配使用的選件組合，以及移除預設內容，讓活動提供更乾淨、更相關的體驗，且符合您的目標和對象。

## 允許或不允許重複選件 {#allow-duplicate-offers}

<a id="concept_4EF78013F80E48EFA024AE0274C9F037"></a>

在AP活動中的不同位置使用選件資料庫中的選件時，避免這些選件重複。

例如，活動可在具有12個選件的頁面上具有6個位置，因此相同選件可放置於多個位置。 不允許重複選件，以防止同一活動內的不同位置同時顯示相同選件。

1. 在[建立或編輯AP活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)時，請按一下&#x200B;**[!UICONTROL 設定]**&#x200B;圖示（![設定圖示](/help/main/assets/icons/Setting.svg)）。

1. 按一下&#x200B;**[!UICONTROL 允許重複選件]**，根據您的需求開啟或關閉此功能。

   ![設定圖示](../assets/exclusion-1.png)

## 排除特定體驗 {#exclude-experiences}

<a id="task_C17D36EF58AF4908B17A3D84CA6DE85A"></a>

排除特定體驗，以從AP活動中移除某些選件組合。 有些組合可能無法搭配使用，或者您可以限制測試的體驗數量，以降低活動的流量需求。

1. 在[建立或編輯AP活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)時，按一下&#x200B;**[!UICONTROL 管理內容]**&#x200B;圖示（![管理內容圖示](/help/main/assets/icons/Experience.svg)）。

   **[!UICONTROL 「體驗」]**&#x200B;清單顯示從所有內容和位置選項的排列中產生的每一個體驗。

1. 排除您不想測試的體驗。

   * 若要排除單一體驗，請按一下&#x200B;**[!UICONTROL 更多動作]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmall.svg) ），然後按一下&#x200B;**[!UICONTROL 排除]**。
   * 若要一次排除數個體驗，請選取每個體驗的核取方塊，然後按一下[排除]。**&#x200B;** 選取一或多個體驗時，會顯示&#x200B;**[!UICONTROL 排除]**&#x200B;圖示。

   ![分批排除體驗](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   體驗現已從活動中排除，其&#x200B;**[!UICONTROL 狀態]**&#x200B;顯示為&#x200B;**[!UICONTROL 已排除]**。

## 排除預設內容 {#exclude-default-content}

<a id="task_DCB4528989DF4C05A3A4729E5891D18F"></a>

當您不想讓預設內容成為AP活動的一部分時，請排除此預設內容，如此一來，位置就只會包含一個與預設內容不同的選件。 此方法也可讓您變更頁面其餘部分的外觀與操作方式，以符合您測試的優惠方案。 例如，若要比對選件的調色盤，您可以變更頁面的背景顏色，並排除預設的背景顏色。

1. 在[建立或編輯AP活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)時，請選取您要取代的內容，然後按一下&#x200B;**[!UICONTROL 變更文字/HTML]**、**[!UICONTROL 變更影像選件]**&#x200B;或&#x200B;**[!UICONTROL 變更背景顏色]**。 可用的選項會依內容型別而異。

   ![變更選項](../assets/exclusion-1.png)

1. 建立您的新內容。

1. 按一下&#x200B;**[!UICONTROL 更多動作]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/Setting.svg) ），然後按一下&#x200B;**排除預設選件/包含預設選件**&#x200B;切換以排除或包含預設選件。

   <!--
   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)
   -->

<!--
1. Click **[!UICONTROL Save]**.

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**To exclude default content using the [!UICONTROL Form-Based Experience Composer]:** 

1. While creating or editing an AP activity, click **[!UICONTROL Change Text/HTML]** or **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]**. 
1. In the dialog box, create your new content and uncheck **[!UICONTROL Include]** to the right of the default content (or uncheck the Default Image/Video in the [!UICONTROL Select Content] screen). 

   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   For Image/Video content: 

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. Click **[!UICONTROL Save]**. 

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)
-->

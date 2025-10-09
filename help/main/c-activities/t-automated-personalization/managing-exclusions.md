---
keywords: 重複資料刪除；允許重複專案；排除重複選件；自動個人化；不允許重複選件；排除；預設內容；
description: 管理[!UICONTROL Automated Personalization] (AP)活動中的排除專案。
title: 如何管理[!UICONTROL Automated Personalization]活動中的排除？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: 2715e803938ee552e2c6db438ed4dbece4b6220e
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 21%

---

# 管理排除項目

掌握排除專案，控制您的[!UICONTROL Automated Personalization] (AP)策略。 無論您是要防止重複選件、改良體驗組合，還是要移除預設內容，排除專案可讓您提供更乾淨、更相關的體驗，以符合您的目標和受眾期望。

## 允許或不允許重複選件 {#concept_4EF78013F80E48EFA024AE0274C9F037}

在AP活動中的不同位置使用選件資料庫中的選件時，避免這些選件重複。

例如，您可能在有 12 個產品建議的六個位置頁面上有一個活動。相同產品建議有可能放入活動中的一或多個位置。此功能可讓您防止重複選件同時顯示在相同活動內的不同位置。

1. 在[建立或編輯AP活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時，根據您的需求，按一下&#x200B;**[!UICONTROL Configure]**&#x200B;圖示（ ![設定圖示](/help/main/assets/icons/Setting.svg) ） >按一下&#x200B;**[!UICONTROL Allow Duplicate Offers]**&#x200B;以開啟或關閉此功能。

## 排除特定體驗 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

如果您想要從AP活動中排除某些選件組合，請排除特定體驗。

可能有某些組合無法搭配使用，或您可能正在限制測試的體驗數量，以降低活動的流量需求。

1. 在[建立或編輯AP活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時，按一下&#x200B;**管理內容**&#x200B;圖示（![管理內容圖示](/help/main/assets/icons/Experience.svg)）。

   [!UICONTROL Experiences]清單顯示從所有內容和位置選項的排列中產生的每一個體驗。

1. 視需要排除體驗。

   您可以按一下&#x200B;[!UICONTROL **更多動作**]&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmall.svg) ），然後按一下&#x200B;[!UICONTROL **排除**]，以排除特定體驗。

   或者，您可以選取相關體驗的核取方塊，然後按一下「**[!UICONTROL Exclude]**」，以分批排除體驗。 勾選一或多個體驗時，[!UICONTROL Exclude]圖示就會顯示。

   ![分批排除體驗](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   體驗現已從活動中排除，其[!UICONTROL Status]顯示為[!UICONTROL Excluded]。

## 排除預設內容 {#task_DCB4528989DF4C05A3A4729E5891D18F}

有時候，您可能不想將預設內容加入您的AP活動。 您可以使用此方法，讓某個位置在活動中只有一個選件（與您的預設內容不同）。

排除預設內容可有效地變更頁面其餘部分的外觀與操作方式，以適合您在 AP 活動中所測試的產品建議。例如，假設您想要符合所測試之產品建議的色板，則可以變更頁面的背景顏色，並排除預設背景顏色。

**若要使用[!UICONTROL Visual Experience Composer] (VEC)排除預設內容：**

1. 在[建立或編輯AP活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時，請選取您要取代的內容，然後按一下以存取&#x200B;**[!UICONTROL Change Text/HTML]**、**[!UICONTROL Change Image Offer]**&#x200B;或&#x200B;**[!UICONTROL Change Background Color]**。 可用的選項會因內容型別而異。

   ![變更選項](/help/main/c-activities/t-automated-personalization/assets/options.png)
1. 建立您的新內容。

1. 按一下&#x200B;**[!UICONTROL More Actions]** （![更多動作圖示](/help/main/assets/icons/Setting.svg) ）圖示，然後按一下&#x200B;**排除預設選件/包含預設選件**/切換以排除或包含預設選件。

   <!-- Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)-->

<!-- 1. Click **[!UICONTROL Save]**.

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

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)-->

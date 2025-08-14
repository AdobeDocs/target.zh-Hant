---
keywords: 重複資料刪除；允許重複專案；排除重複選件；自動個人化；不允許重複選件；排除；預設內容；
description: 管理[!UICONTROL Automated Personalization] (AP)活動中的排除專案。
title: 如何管理[!UICONTROL Automated Personalization]活動中的排除？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: c5016d212edafa908b8755044e73d28167e20e8a
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 37%

---

# 管理排除項目

在[!UICONTROL Automated Personalization]的[!DNL Adobe Target] (AP)活動中排除重複選件、排除特定體驗，以及排除預設內容，藉此管理排除專案。

## 排除重複選件 {#concept_4EF78013F80E48EFA024AE0274C9F037}

在[!UICONTROL Automated Personalization]活動中的不同位置使用選件資料庫中的選件時，防止重複這些選件。

例如，您可能在有 12 個產品建議的六個位置頁面上有一個活動。相同產品建議有可能放入活動中的一或多個位置。此功能可防止重複產品建議同時顯示在相同活動內的不同位置。

按一下&#x200B;**[!UICONTROL Configure]**&#x200B;圖示> **[!UICONTROL Duplicate Offers]**，然後按一下&#x200B;**[!UICONTROL Allow Duplicates]**&#x200B;或&#x200B;**[!UICONTROL Disallow Duplicates]**。

![重複產品建議選項](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## 排除特定體驗 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

如果您想要從[!UICONTROL Automated Personalization]活動中排除某些選件組合，請排除特定體驗。

可能有某些組合無法搭配使用，或您可能正在限制測試的體驗數量，以降低活動的流量需求。

1. 在[建立或編輯 AP 活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時，按一下標頭列中的&#x200B;**管理內容**。

   ![管理內容連結](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   [!UICONTROL Experiences]清單顯示從所有內容和位置選項的排列中產生的每一個體驗。

1. 視需要排除體驗。

   您可以暫留在所需的體驗上，然後按一下排除圖示，以排除特定的體驗。

   ![透過暫留排除體驗](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   或者，您可以選取相關體驗的核取方塊，然後按一下對話方塊右上角的&#x200B;**[!UICONTROL Exclude]**&#x200B;圖示，以分批排除體驗。 勾選一或多個體驗時，[!UICONTROL Exclude]圖示就會顯示。

   ![分批排除體驗](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   您可以按一下[!UICONTROL Status]下拉式清單，以篩選此清單檢視，而只看到已排除或已包含的活動。

   體驗現已從活動中排除，其[!UICONTROL Status]顯示為[!UICONTROL Excluded]。

   ![排除的體驗](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## 排除預設內容 {#task_DCB4528989DF4C05A3A4729E5891D18F}

有時候，您可能不想將預設內容加入您的[!UICONTROL Automated Personalization]活動。 您存取此設定的方式與建立排除群組不同。您可以使用此方法以在一個位置中只有一個產品建議 (與您的預設內容不同) 作為 AP 活動的一部分。

排除預設內容可有效地變更頁面其餘部分的外觀與操作方式，以適合您在 AP 活動中所測試的產品建議。例如，假設您想要符合所測試之產品建議的色板，則可以變更頁面的背景顏色，並排除預設背景顏色。

**若要使用[!UICONTROL Visual Experience Composer] (VEC)排除預設內容：**

1. 在[建立或編輯AP活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時，請選取您要取代的內容，然後按一下以存取&#x200B;**[!UICONTROL Change Text/HTML]**、**[!UICONTROL Change Image]**&#x200B;或&#x200B;**[!UICONTROL Change Background Color]**。
1. 在對話方塊中，建立新內容，並取消勾選預設內容右邊的&#x200B;**包含** （或在[!UICONTROL Select Content]畫面中取消勾選「預設影像/影片」）。

   根據內容或選件型別，[!UICONTROL Include]核取方塊的位置稍有不同。

   針對文字/HTML 內容:

   ![在編輯文字/HTML 對話方塊中包含核取方塊](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   針對影像/影片內容:

   ![在選取內容對話方塊中包含核取方塊](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   背景顏彩:

   ![在編輯背景顏色對話方塊中包含核取方塊](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. 按一下 **[!UICONTROL Save]**。

   您可以看到使用您在[!UICONTROL Manage Content]下指定的選件所建立的體驗。 您注意到在[!UICONTROL Manage Content]中不會使用您排除的預設選件建立任何體驗。

   ![exclude_content_vec_4圖片](assets/exclude_content_vec_4.png)

**若要使用[!UICONTROL Form-Based Experience Composer]排除預設內容：**

1. 在建立或編輯AP活動時，按一下&#x200B;**[!UICONTROL Change Text/HTML]**&#x200B;下的&#x200B;**[!UICONTROL Change Image Offer]**&#x200B;或&#x200B;**[!UICONTROL Content]**。
1. 在對話方塊中，建立新內容，並取消勾選預設內容右邊的&#x200B;**[!UICONTROL Include]** （或在[!UICONTROL Select Content]畫面中取消勾選「預設影像/影片」）。

   根據內容或選件型別，[!UICONTROL Include]核取方塊的位置稍有不同。

   針對文字/HTML 內容:

   ![exclude_content_form_1圖片](assets/exclude_content_form_1.png)

   針對影像/影片內容:

   ![exclude_content_form_2圖片](assets/exclude_content_form_2.png)

1. 按一下 **[!UICONTROL Save]**。

   您可以看到使用您在[!UICONTROL Manage Content]下指定的選件所建立的體驗。 您注意到在[!UICONTROL Manage Content]中不會使用您排除的預設選件建立任何體驗。

   ![exclude_content_form_3圖片](assets/exclude_content_form_3.png)

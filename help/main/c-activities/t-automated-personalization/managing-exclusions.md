---
keywords: 刪除重複項目；允許重複項目；排除重複選件；自動個人化；不允許重複選件；排除；預設內容；排除群組
description: 管理Adobe中的排除 [!DNL Target] Automated Personalization(AP)活動。 建立排除群組並排除重複選件、特定體驗和預設內容。
title: 如何管理Automated Personalization活動中的排除項目？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 88%

---

# 管理排除項目

管理排除的方法包括建立排除群組、排除重複選件、排除特定體驗，以及排除 [!UICONTROL Automated Personalization] (AP) [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)活動。

## 建立排除群組 {#task_AAAA6C7239A84F7696C8492F04B575A2}

在 Automated Personalization (AP) 活動中建立排除群組，以確保會自動排除具有指定選件的體驗。

排除群組有效地確保不相容的選件不會出現在相同體驗的不同位置中。例如，假設您有兩個選件: 一個是全部商品 20% 折扣，另一個是 15% 折扣。您絕不希望這兩個選件都讓相同體驗中的訪客看到。如果將這兩個選件新增至排除群組，就可以確保永遠不會發生這種情形。

您也可以限制哪些受眾能夠看見 AP 活動中特定選件。如需詳細資訊，請參閱[Target Automated Personalization 選件](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)。

**若要建立排除群組:**

1. 在[建立或編輯 AP 活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時，按一下標頭列中的&#x200B;**[!UICONTROL 管理內容]**。

   ![管理內容連結](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

1. 在[!UICONTROL 「管理內容」]對話方塊中，按一下&#x200B;**[!UICONTROL 「排除群組」]**。

   ![管理內容 > 排除群組對話方塊](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   如果您先前已建立排除群組，則會出現在清單中。如果您尚未建立排除群組，則會提示您建立。

1. 按一下&#x200B;**[!UICONTROL 「建立排除群組」]**。

   ![建立排除群組對話方塊](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. (必要) 指定排除群組的描述性名稱。

   描述性名稱可協助您或其他人快速找到並瞭解群組的用途。

1. 尋找並選取您想要新增至排除群組的選件。

   您可以從排除群組的相同位置中選取多個選件。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

排除群組中的選件將來會自動從相同的體驗中排除。

## 排除重複選件 {#concept_4EF78013F80E48EFA024AE0274C9F037}

防止來自選件資料庫的選件在[!UICONTROL 自動個人化]活動中的不同位置重複使用。

例如，您可能在有 12 個選件的六個位置頁面上有一個活動。相同選件有可能放入活動中的一或多個位置。此功能可防止重複選件同時顯示在相同活動內的不同位置。

按一下「**[!UICONTROL 設定]** > **[!UICONTROL 重複選件]**」，然後按一下&#x200B;**[!UICONTROL 「允許重複項目」]**&#x200B;或&#x200B;**[!UICONTROL 「不允許重複項目」]**。

![重複選件選項](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## 排除特定體驗 {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

如果您要從您的自動個人化活動中排除某些選件組合，請排除特定體驗。

特定的組合可能無法一起運作，或您可能限制測量的體驗數目，以降低活動的流量需求。

1. 在[建立或編輯 AP 活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)時，按一下標頭列中的&#x200B;**管理內容**。

   ![管理內容連結](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   [!UICONTROL 「體驗」]清單顯示從所有內容和位置選項的排列中產生的每一個體驗。

1. 視需要排除體驗。

   您可以暫留在所需的體驗上，然後按一下排除圖示，以排除特定的體驗。

   ![透過暫留排除體驗](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   或者，您可以選取相關體驗的核取方塊，然後按一下對話方塊右上角的 **[!UICONTROL 排除]**&#x200B;圖示，以分批排除/包含體驗。勾選一或多個體驗時，[!UICONTROL 排除]圖示就會出現。

   ![分批排除體驗](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   您可以按一下[!UICONTROL 「狀態」]下拉式清單，以篩選此清單檢視，而只看到已排除或已包含的活動。

   體驗現在會從活動中排除，而其[!UICONTROL 「狀態」]會顯示為[!UICONTROL 「已排除」]。

   ![排除的體驗](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## 排除預設內容 {#task_DCB4528989DF4C05A3A4729E5891D18F}

在某些情況下，您可能不想要隨著自動個人化活動納入您的預設內容。您存取此設定的方式與建立排除群組不同。您可以使用此方法以在一個位置中只有一個選件 (與您的預設內容不同) 作為 AP 活動的一部分。

排除預設內容可有效地變更頁面其餘部分的外觀與操作方式，以適合您在 AP 活動中所測試的選件。例如，假設您想要符合所測試之選件的色板，則可以變更頁面的背景顏色，並排除預設背景顏色。

**若要使用可視化體驗撰寫器 (VEC) 來排除預設內容:**

1. 同時 [建立或編輯AP活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)，選取您要取代的內容，然後按一下以存取 **[!UICONTROL 變更文字/HTML]**, **[!UICONTROL 變更影像]**，或 **[!UICONTROL 更改背景顏色]**.
1. 在對話方塊中，建立新內容，並取消勾選預設內容右邊 **「包含」** (或在「選取內容」畫面中取消勾選「預設影像/影片」)。

   視內容/選件類型而定，[!UICONTROL 「包含」]核取方塊的位置會稍微不同。

   針對文字/HTML 內容:

   ![在編輯文字/HTML 對話方塊中包含核取方塊](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   針對影像/影片內容:

   ![在選取內容對話方塊中包含核取方塊](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   背景顏彩:

   ![在編輯背景顏色對話方塊中包含核取方塊](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

   您可以在[!UICONTROL 「管理內容」]下看到透過您指定的選件建立的體驗。您將注意到，使用您排除的預設選件時不會在[!UICONTROL 管理內容]中建立任何體驗。

   ![exclude_content_vec_4影像](assets/exclude_content_vec_4.png)

**若要使用表單式體驗撰寫器來排除預設內容:**

1. 在建立或編輯 AP 活動時，按一下&#x200B;**[!UICONTROL 「內容」]**&#x200B;下的&#x200B;**[!UICONTROL 「變更文字/HTML」]**&#x200B;或&#x200B;**[!UICONTROL 「變更影像選件」]**。
1. 在對話方塊中，建立新內容，並取消勾選預設內容右邊 **[!UICONTROL 「包含」]** (或在「選取內容」畫面中取消勾選「預設影像/影片」)。

   視內容/選件類型而定，「包含」核取方塊的位置會稍微不同。

   針對文字/HTML 內容:

   ![exclude_content_form_1影像](assets/exclude_content_form_1.png)

   針對影像/影片內容:

   ![exclude_content_form_2影像](assets/exclude_content_form_2.png)

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

   您可以在[!UICONTROL 「管理內容」]下看到透過您指定的選件建立的體驗。您將注意到，使用您排除的預設選件時不會在[!UICONTROL 管理內容]中建立任何體驗。

   ![exclude_content_form_3影像](assets/exclude_content_form_3.png)

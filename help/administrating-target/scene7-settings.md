---
keywords: scene7;dynamic media classic;digital asset management;assets;dam;content library;swap image
description: Adobe Target可與Adobe Dynamic Media Classic整合，以在內容庫中提供數位資產管理(DAM)。
title: Dynamic Media Classic整合組態整合
feature: administration general
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 23%

---


# Scene7組態{#scene-settings}

[!DNL Target] 可與整合， [!DNL Adobe Dynamic Media Classic] 以在內容庫中提供數位資 [!UICONTROL 產管理]。

>[!NOTE]
>
>將[!DNL Target]與[!DNL Dynamic Media Classic]整合後，可傳送上傳至[!DNL Adobe Experience Cloud]資產資料夾的資產（作為活動的一部分）。 此整合無法存取[!DNL Dynamic Media Classic]中上傳的所有資產，以便在[!DNL Target]活動中傳送。

如果您已擁有[!DNL Dynamic Media]帳戶，則可以提供您現有的憑證。 如果您沒有帳戶，則可以向您的[!DNL Adobe]代表索取受限制用途的[!DNL Dynamic Media Classic]帳戶，無需額外付費。 此帳戶僅能用於限制用於[!DNL Target]的用途。 此服務已提供給工作流程需要影像交換功能的客戶。

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

如果未配置此設定，則活動建立工作流中的[!UICONTROL 交換影像選件]選項不可用。 在設定此設定後，在[視覺體驗撰寫器(VEC)和表單式體驗撰寫器(Form-Based Experience Composer)](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中都可使用交換／變更影像選件的選項。 然後，您就可以利用影像選件與從[!DNL Adobe Experience Cloud]上傳的影像，以用於[!DNL Target]活動。

如果您想要直接在選件中或在活動建立期間的自訂代碼中參考公用影像 URL，應該將影像部署至您自己的 Web 伺服器，並在代碼中使用您自己的 URL。無法取得上傳至[!DNL Experience Cloud]之影像的已發佈URL，以直接使用或在使用[!DNL Target]的定位工作流程外使用。 根據合約，此功能是不被允許的。

請注意，來自[!DNL Dynamic Media]影像的儲存URL和最終發佈URL不同，而且必須&#x200B;*NOT*&#x200B;使用影像的儲存連結來建立選件，因為傳送在這類情況下無法運作。 您必須使用影像選件功能，如我們的說明檔案所述。

若要與[!DNL Dynamic Media Classic]([!DNL Scene7])整合，您必須指定下列資訊。

1. 按一下「**[!UICONTROL 管理]** > **[!UICONTROL Scene7組態]**」。

   ![Scene7頁面](/help/administrating-target/assets/scene7.png)

1. 指定以下[!DNL Dynamic Media Classic]帳戶資訊：

   **地區:**[!DNL Dynamic Media] 您的 帳戶的地區: 北美、歐洲或亞洲。

   **隨選資料夾:** 用於 Target 資料夾外部內容的位置，並且會手動上傳至 [!DNL Dynamic Media].

   **電子郵件地址：** 用於登入( [!DNL Dynamic Media Classic] [!DNL Scene7])的電子郵件地址。

   **密碼：** 用於登入()的 [!DNL Dynamic Media Classic] 密碼[!DNL Scene7]。

1. 按一下&#x200B;**[!UICONTROL 「提交」]**。

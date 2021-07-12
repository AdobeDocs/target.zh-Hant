---
keywords: scene7;dynamic media classic；數位資產管理；資產；dam；內容庫；交換影像
description: 了解如何將Adobe [!DNL Target] 與AdobeDynamic Media Classic(前身為Scene7)整合，以在內容庫中提供數位資產管理(DAM)。
title: 如何設定Dynamic Media Classic(Scene7)整合？
feature: 管理與設定
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 21%

---

# Dynamic Media Classic(前身為Scene7)設定

[!DNL Adobe Target] 可與(舊 [!DNL Adobe Dynamic Media Classic] 稱)整 [!DNL Scene7]合，以在內容庫中提供數位資產 [!UICONTROL 管理(DAM)]。

>[!NOTE]
>
>將[!DNL Target]與[!DNL Dynamic Media Classic]整合可啟用上傳至[!DNL Adobe Experience Cloud]資產資料夾的資產（作為活動的一部分）傳送。 此整合不會啟用對[!DNL Dynamic Media Classic]中上傳以在[!DNL Target]活動中傳送的所有資產的存取。

如果您已有[!DNL Dynamic Media]帳戶，則可以提供現有憑證。 如果您沒有帳戶，則可以向您的[!DNL Adobe]代表免費申請一個限制使用的[!DNL Dynamic Media Classic]帳戶。 此帳戶只能用於限制在[!DNL Target]中使用的用途。 此服務已提供給工作流程需要影像交換功能的客戶。

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

如果未配置此設定，則活動建立工作流程中的[!UICONTROL 交換影像選件]選項不可用。 設定此設定後，可交換/變更影像選件的選項可在[可視化體驗撰寫器(VEC)和表單式體驗撰寫器](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中使用。 然後，您就可以將影像選件與已從[!DNL Adobe Experience Cloud]上傳以用於[!DNL Target]活動的影像搭配使用。

如果您想要直接在選件中或在活動建立期間的自訂代碼中參考公用影像 URL，應該將影像部署至您自己的 Web 伺服器，並在代碼中使用您自己的 URL。無法取得上傳至[!DNL Experience Cloud]之影像的已發佈URL，以使用[!DNL Target]直接或在目標工作流程之外使用。 根據合約，此功能是不被允許的。

請注意，來自[!DNL Dynamic Media]之影像的儲存URL和最終發佈URL不同，且必須&#x200B;*NOT*&#x200B;使用影像的儲存連結建立選件，因為傳送在此情況下將無法運作。 您必須使用影像選件功能，如說明檔案中所述。

若要與[!DNL Dynamic Media Classic]([!DNL Scene7])整合，需指定下列資訊。

1. 按一下「**[!UICONTROL 管理]** > **[!UICONTROL Scene7設定]**」。

   ![Scene7頁面](/help/administrating-target/assets/scene7.png)

1. 指定以下[!DNL Dynamic Media Classic]帳戶資訊：

   **地區:**[!DNL Dynamic Media] 您的 帳戶的地區: 北美、歐洲或亞洲。

   **隨選資料夾:** 用於 Target 資料夾外部內容的位置，並且會手動上傳至 [!DNL Dynamic Media].

   **電子郵件地址：** 用來登入( [!DNL Dynamic Media Classic] [!DNL Scene7])的電子郵件地址。

   **密碼：** 用來登入( [!DNL Dynamic Media Classic] [!DNL Scene7])的密碼。

1. 按一下&#x200B;**[!UICONTROL 「提交」]**。

---
description: Target Standard 可以與 Adobe Dynamic Media Classic (先前的 Scene7) 整合以在內容庫中提供數位資產管理 (DAM)。
title: Dynamic Media Classic 整合 配置整合
feature: administration general
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 29%

---


# Scene7設定 {#scene-settings}

Target can be integrated with [!DNL Adobe Dynamic Media Classic] (formerly [!DNL Scene7]) to provide Digital Asset Management (DAM) in the Content Library.

>[!NOTE]
>
>Integrating [!DNL Target] with [!DNL Dynamic Media Classic] enables delivery of assets (as part of activities) uploaded to the [!DNL Adobe Experience Cloud] assets folder. This integration does not enable access to all assets uploaded in [!DNL Dynamic Media Classic] for delivery in [!DNL Target] activities.

If you already have a [!DNL Dynamic Media] account, you can supply your existing credentials. If you do not have an account, you can request a restricted-use [!DNL Dynamic Media Classic] account at no additional charge from your [!DNL Adobe] representative. This account can be used for purposes restricted for use in [!DNL Target] only. 此服務已提供給工作流程需要影像交換功能的客戶。

If this setting is not configured, the [!UICONTROL Swap Image offer] option within the activity creation workflow is not available. 設定完此設定後，可在 [Visual Experience Composer(VEC)和表單型體驗撰寫器中，使用交換／變更影像選件的選項](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)。 You can then leverage image offers with images that have been uploaded from the [!DNL Adobe Experience Cloud] for use in [!DNL Target] activities.

如果您想要直接在選件中或在活動建立期間的自訂代碼中參考公用影像 URL，應該將影像部署至您自己的 Web 伺服器，並在代碼中使用您自己的 URL。There is no way to obtain the published URL of an image uploaded into the [!DNL Experience Cloud] to consume directly or outside of targeting workflows using [!DNL Target]. 根據合約，此功能是不被允許的。

Note that the storage URL and the final publish URLs of images from [!DNL Dynamic Media] are different and one must *NOT* create offers using the storage link of images as delivery will not work in such cases. 您必須使用影像選件功能，如我們的說明檔案所述。

To integrate with [!DNL Dynamic Media Classic] ([!DNL Scene7]), you need to specify the following information.

1. 按一 **[!UICONTROL 下「管理]** > **[!UICONTROL Scene7設定」]**。

   ![Scene7頁面](/help/administrating-target/assets/scene7.png)

1. Specify the following [!DNL Dynamic Media Classic] account information:

   **地區:**[!DNL Dynamic Media] 您的 帳戶的地區: 北美、歐洲或亞洲。

   **隨選資料夾:** 用於 Target 資料夾外部內容的位置，並且會手動上傳至 [!DNL Dynamic Media].

   **電子郵件地址：** 用於登入( [!DNL Dynamic Media Classic][!DNL Scene7])的電子郵件地址。

   **密碼：** 用於登入()的 [!DNL Dynamic Media Classic] 密碼[!DNL Scene7]。

1. 按一下&#x200B;**[!UICONTROL 「提交」]**。

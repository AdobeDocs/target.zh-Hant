---
keywords: implementation;api;profile;profile api settings;authentication token
description: 啟用或停用透過 API 批次更新的驗證，並產生設定檔驗證 Token。
title: 設定檔 API 設定
feature: api
subtopic: Getting Started
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 64%

---


# 設定檔 API 設定{#profile-api-settings}

啟用或停用透過 API 批次更新的驗證，並產生設定檔驗證 Token。

[!DNL Adobe Target] 會為每一個使用者建立和維護一個設定檔: This profile is stored on the [!DNL Target] edge cluster and is updated in real time after every visit, however, you can update a profile individually or in bulk via API.

為了提高安全性，您可以要求「大量更新 API」呼叫必須在要求的標頭中傳送有效的存取 Token。Users with [!UICONTROL Approver] permissions can generate and enable profile API authentication tokens.

**若要使用 Target UI 來要求驗證和產生存取 Token:**

1. 按一 **[!UICONTROL 下「管理]** >實 **[!UICONTROL 施」]**。
1. 在「描 **[!UICONTROL 述檔API]** 」投影片 **[!UICONTROL 下，「需要驗證]** 」切換至啟用或停用的位置。

   ![](assets/profile_api_settings.png)

1. (Conditional) If you enabled authentication requirements, click **[!UICONTROL Generate New Pfofile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   Token 會根據[!UICONTROL 「到期時間」]方塊中列出的時間而到期。

   >[!NOTE]
   >
   >您也可以透過 API 來產生設定檔驗證 Token。如需詳細資訊，請參閱 [Adobe Target Developers 網站](https://developers.adobetarget.com/)上的[設定檔](https://developers.adobetarget.com/api/#profiles)。

1. 複製 Token 並加入要求的標頭中，格式為: &quot;Authorization&quot; : &quot;Bearer &quot;

Click [!UICONTROL Generate New Profile Authentication Token] to regenerate the token as needed.

>[!IMPORTANT]
>
>重設此 Token 會造成使用目前 Token 的 API 呼叫失敗。這需要更新任何使用此 Token 的指令碼或應用程式。

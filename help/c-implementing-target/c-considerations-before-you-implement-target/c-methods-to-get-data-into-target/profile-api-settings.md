---
keywords: implementation;api;profile;profile api settings;authentication token
description: 透過Adobe Target API啟用或停用批次更新的驗證，並產生描述檔驗證Token。
title: Adobe Target中的設定檔API設定
feature: api
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 40%

---


# 設定檔 API 設定

透過Adobe Target API啟用或停用批次更新的驗證，並產生描述檔驗證Token。

[!DNL Adobe Target] 會為每一個使用者建立和維護一個設定檔: This profile is stored on the [!DNL Target] edge cluster and is updated in real time after every visit; however, you can update a profile individually or in bulk via API.

為了提高安全性，您可以要求「大量更新 API」呼叫必須在要求的標頭中傳送有效的存取 Token。

**若要使用 Target UI 來要求驗證和產生存取 Token:**

1. 按一 **[!UICONTROL 下「管理]** >實 **[!UICONTROL 施」]**。
1. 在「描 **[!UICONTROL 述檔API]** 」投影片 **[!UICONTROL 下，「需要驗證]** 」切換至啟用或停用的位置。

   ![](assets/profile_api_settings.png)

1. (Conditional) If you enabled authentication requirements, click **[!UICONTROL Generate New Profile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   Token 會根據[!UICONTROL 「到期時間」]方塊中列出的時間而到期。

   您必須具備下列其中一個使用者權限才能產生驗證Token:

   * 至少 [!UICONTROL 是Editor] (或 [!UICONTROL Approver])權限

      如需客戶的詳細資 [!DNL Target Standard] 訊，請參 [閱「指定使用者中的角色和](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) 權限」 **。 如需客戶的詳細資 [!DNL Target Premium] 訊，請參 [閱設定企業權限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)。

   * 工作區／產品設定檔層級上的管理員角色

      工作區僅供客 [!DNL Target Premium] 戶使用。 For more information, see [Configure enterprise permissions](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

   * 產品層級的管理權限(Sysadmin權 [!DNL Adobe Target] 限)
   >[!NOTE]
   >
   >您也可以透過 API 來產生設定檔驗證 Token。如需詳細資訊，請參閱 [Adobe Target Developers 網站](https://developers.adobetarget.com/)上的[設定檔](https://developers.adobetarget.com/api/#profiles)。

1. 複製 Token 並加入要求的標頭中，格式為: &quot;Authorization&quot; : &quot;Bearer &quot;

Click [!UICONTROL Generate New Profile Authentication Token] to regenerate the token as needed.

>[!IMPORTANT]
>
>重設此 Token 會造成使用目前 Token 的 API 呼叫失敗。這需要更新任何使用此 Token 的指令碼或應用程式。

---
keywords: 實現；api;profile;profile api設定；authentication token
description: 瞭解如何通過Adobe配置批更新的身份驗證 [!DNL Target] API和生成配置檔案驗證令牌。
title: 如何使用配置檔案API設定啟用或禁用批更新？
feature: APIs/SDKs
role: Developer
exl-id: 6346e11b-0853-47f1-9706-69e8635a6f25
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 61%

---

# 設定檔 API 設定

通過啟用或禁用批更新的身份驗證 [!DNL Adobe Target] API和生成配置檔案驗證令牌。

[!DNL Adobe Target] 會為每一個使用者建立和維護一個設定檔: 此配置檔案儲存在 [!DNL Target] 邊緣簇，每次訪問後即時更新；但是，您可以通過API單獨或批量更新配置檔案。

為了提高安全性，您可以要求「大量更新 API」呼叫必須在要求的標頭中傳送有效的存取 Token。

**若要使用 Target UI 來要求驗證和產生存取 Token:**

1. 按一下「**[!UICONTROL 管理]** > 「**[!UICONTROL 實施]**」。
1. 下 **[!UICONTROL 配置檔案API]** 滑動 **[!UICONTROL 需要身份驗證]** 切換到啟用或禁用位置。

   ![](assets/profile_api_settings.png)

1. （條件）如果啟用了身份驗證要求，請按一下 **[!UICONTROL 生成新的配置檔案身份驗證令牌]**。

   ![](assets/profile_api_settings_2.png)

   Token 會根據[!UICONTROL 「到期時間」]方塊中列出的時間而到期。

   您必須具備下列其中一個使用者權限才能產生驗證權杖：

   * 至少有 [!UICONTROL 編輯者]權限 (或[!UICONTROL 核准者]權限)

      如需有關 [!DNL Target Standard] 客戶的詳細資訊，請參閱&#x200B;*使用者*&#x200B;中的[指定角色與權限](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。如需有關 [!DNL Target Premium] 客戶的詳細資訊，請參閱[設定企業權限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)。

   * 工作區/產品設定檔層級的管理員角色

      工作區僅適用於 [!DNL Target Premium] 客戶。如需詳細資訊，請參閱[企業使用者權限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)。

   * [!DNL Adobe Target] 產品層級的管理員權限 (Sysadmin 權限)
   >[!NOTE]
   >
   >您也可以透過 API 來產生設定檔驗證 Token。如需詳細資訊，請參閱 [Adobe Target Developers 網站](https://developers.adobetarget.com/)上的[設定檔](https://developers.adobetarget.com/api/#profiles)。

1. 複製 Token 並加入要求的標頭中，格式為: &quot;Authorization&quot; : &quot;Bearer &quot;

按一下 [!UICONTROL 生成新的配置檔案身份驗證令牌] 以根據需要重新生成令牌。

>[!IMPORTANT]
>
>重設此 Token 會造成使用目前 Token 的 API 呼叫失敗。這需要更新任何使用此 Token 的指令碼或應用程式。

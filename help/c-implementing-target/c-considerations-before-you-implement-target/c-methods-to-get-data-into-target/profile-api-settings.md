---
description: 啟用或停用透過 API 批次更新的驗證，並產生設定檔驗證 Token。
keywords: 實作; API; 設定檔; 設定檔 API 設定
seo-description: 啟用或停用透過 API 批次更新的驗證，並產生設定檔驗證 Token。
seo-title: 設定檔 API 設定
solution: Target
subtopic: 快速入門
title: 設定檔 API 設定
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 設定檔 API 設定{#profile-api-settings}

啟用或停用透過 API 批次更新的驗證，並產生設定檔驗證 Token。

Adobe Target 會為每一個使用者建立和維護一個設定檔: 此設定檔儲存在 Target 邊緣叢集，並於每一次造訪之後即時更新，不過，您可以個別地或透過 API 大量地更新設定檔。

為了提高安全性，您可以要求「大量更新 API」呼叫必須在要求的標頭中傳送有效的存取 Token。具備「核准者」權限的使用者可以產生和啟用設定檔 API 驗證 Token。

**若要使用 Target UI 來要求驗證和產生存取 Token:**

1. 按一下 **[!UICONTROL 「設定]** &gt; **[!UICONTROL 實作」]**。
1. 在 **[!UICONTROL 「設定檔 API 設定」]** 下，使用 **「需要驗證」]下拉式清單來啟用或停用驗證需求。[!UICONTROL **

   ![](assets/profile_api_settings.png)

1. (依條件) 如果您已啟用驗證需求，請按一下 **[!UICONTROL 「產生設定檔驗證 Token」]**。

   ![](assets/profile_api_settings_2.png)

   Token 會根據[!UICONTROL 「到期時間」]方塊中列出的時間而到期。

   >[!NOTE]
   >
   >您也可以透過 API 來產生設定檔驗證 Token。如需詳細資訊，請參閱 [Adobe Target Developers 網站](https://developers.adobetarget.com/)上的[設定檔](https://developers.adobetarget.com/api/#profiles)。

1. 複製 Token 並加入要求的標頭中，格式為: &quot;Authorization&quot; : &quot;Bearer &quot;

視需要按一下[!UICONTROL 「重新產生設定檔驗證 Token」]，以重新產生 Token。

>[!IMPORTANT]
>
>重設此 Token 會造成使用目前 Token 的 API 呼叫失敗。這需要更新任何使用此 Token 的指令碼或應用程式。


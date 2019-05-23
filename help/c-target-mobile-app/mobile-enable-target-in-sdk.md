---
description: 將 Adobe Mobile Services SDK 新增至您的應用程式。
keywords: 行動應用程式;行動應用程式 sdk;target 行動應用程式;行動 target sdk;行動應用程式 sdk;在 sdk 中啟用 target
seo-description: 將 Adobe Mobile Services SDK 新增至您的應用程式。
seo-title: 啟用 SDK 中的 Target
title: 啟用 SDK 中的 Target
topic: Target
uuid: 673dd5c7-9c09-4a6e-bc41-c6ad27cf269c
translation-type: tm+mt
source-git-commit: 3ed060bf19f06b2f217bd68532884af8d30cc367

---


# 啟用 SDK 中的 Target{#enable-target-in-the-sdk}

將 Adobe Mobile Services SDK 新增至您的應用程式。

1. 如果您尚未在您的應用程式中安裝 Adobe Mobile Services SDK，請使用您的 Analytics 或 Experience Cloud 憑證，並從 [Adobe Mobile Services](https://mobilemarketing.adobe.com) 網站下載 SDK。

1. 將 Adobe Mobile Services SDK 新增至您的應用程式。

   您可以在[「核心實施和生命週期」](https://marketing.adobe.com/resources/help/en_US/mobile/ios/dev_qs.html)下找到說明。
1. 新增用戶端代碼、逾時和啟用 SSL。

   在 Experience Cloud 中，開啟 Mobile Services，然後前往**[!UICONTROL 「管理應用程式設定]** &gt; **[!UICONTROL SDK Target 選項」]**。

   新增您的 Target 用戶端代碼和逾時。clientcode 是您的帳戶或公司所特有。逾時為 Target 在顯示預設內容之前將等候回應的時間 (秒)。確定已在 Adobe Mobile Services 的「管理應用程式設定」頁面中勾選**[!UICONTROL 「使用 HTTPS」]選項。**如果未啟用 HTTPS，除非您將 Target 伺服器加入白名單，否則 iOS9+ 中的所有呼叫將被封鎖。

   ![](assets/mobile-clientcode.png)

1. 建立/找到應用程式之後，請尋找應用程式設定並下載所需的 SDK。

   ![](assets/download-sdk.png)

>[!IMPORTANT]
>
> 如果您無法存取行動行銷介面，可以直接在您的應用程式代碼的配置檔案中進行變更; 不過，它不會與使用者介面中的設定頁面同步。


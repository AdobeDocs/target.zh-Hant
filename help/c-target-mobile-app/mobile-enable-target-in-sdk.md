---
keywords: 行動應用程式;行動應用程式 sdk;target 行動應用程式;行動 target sdk;行動應用程式 sdk;在 sdk 中啟用 target
description: 將 Adobe Mobile Services SDK 新增至您的應用程式。
title: 啟用 SDK 中的 Target
feature: Implement Mobile
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 90%

---


# 啟用 SDK 中的 Target{#enable-target-in-the-sdk}

將 Adobe Mobile Services SDK 新增至您的應用程式。

1. 如果您尚未在您的應用程式中安裝 Adobe Mobile Services SDK，請使用您的 Analytics 或 Experience Cloud 憑證，並從 [Adobe Mobile Services](https://mobilemarketing.adobe.com) 網站下載 SDK。

1. 將 Adobe Mobile Services SDK 新增至您的應用程式。

   您可以在[「核心實施和生命週期」](https://experienceleague.adobe.com/docs/mobile-services/ios/getting-started-ios/dev-qs.html)下找到說明。

1. 新增用戶端代碼、逾時和啟用 SSL。

   在 Experience Cloud 中，開啟 Mobile Services，然後前往&#x200B;**[!UICONTROL 「管理應用程式設定」]**>**[!UICONTROL 「SDK Target 選項」]**。

   新增您的 Target 用戶端代碼和逾時。clientcode 是您的帳戶或公司所特有。逾時為 Target 在顯示預設內容之前將等候回應的時間 (秒)。確定已在 Adobe Mobile Services 的「管理應用程式設定」頁面中勾選&#x200B;**[!UICONTROL 「使用 HTTPS」]**&#x200B;選項。如果未啟用HTTPS，除非您允許列出Target伺服器，否則iOS9+中的所有呼叫都將遭到封鎖。

   ![](assets/mobile-clientcode.png)

1. 建立/找到應用程式之後，請尋找應用程式設定並下載所需的 SDK。

   ![](assets/download-sdk.png)

>[!IMPORTANT]
>
> 如果您無法存取行動行銷介面，可以直接在您的應用程式代碼的配置檔案中進行變更; 不過，它不會與使用者介面中的設定頁面同步。


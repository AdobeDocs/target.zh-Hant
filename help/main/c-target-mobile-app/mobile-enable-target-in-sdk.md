---
keywords: 行動應用程式;行動應用程式 sdk;target 行動應用程式;行動 target sdk;行動應用程式 sdk;在 sdk 中啟用 target
description: 瞭解如何將Adobe移動服務SDK添加到移動應用。
title: 如何啟用 [!DNL Target] 在Adobe移動SDK中？
feature: Implement Mobile
role: Developer
exl-id: c34bd50c-e17f-4dfb-8470-8f4c8639ee9f
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 80%

---

# 啟用 [!DNL Target] 在SDK中

將 Adobe Mobile Services SDK 新增至您的應用程式。

1. 如果您尚未在您的應用程式中安裝 Adobe Mobile Services SDK，請使用您的 Analytics 或 Experience Cloud 憑證，並從 [Adobe Mobile Services](https://mobilemarketing.adobe.com/) 網站下載 SDK。

1. 將 Adobe Mobile Services SDK 新增至您的應用程式。

   您可以在[「核心實施和生命週期」](https://experienceleague.adobe.com/docs/mobile-services/ios/getting-started-ios/dev-qs.html)下找到說明。

1. 新增用戶端代碼、逾時和啟用 SSL。

   在 Experience Cloud 中，開啟 Mobile Services，然後前往&#x200B;**[!UICONTROL 「管理應用程式設定」]**>**[!UICONTROL 「SDK Target 選項」]**。

   新增您的 Target 用戶端代碼和逾時。clientcode 是您的帳戶或公司所特有。逾時為 Target 在顯示預設內容之前將等候回應的時間 (秒)。確定已在 Adobe Mobile Services 的「管理應用程式設定」頁面中勾選&#x200B;**[!UICONTROL 「使用 HTTPS」]**&#x200B;選項。如果未啟用HTTPS，則除非您允許列出目標伺服器，否則iOS9+中的所有調用都將被阻止。

   ![](assets/mobile-clientcode.png)

1. 建立/找到應用程式之後，請尋找應用程式設定並下載所需的 SDK。

   ![](assets/download-sdk.png)

>[!IMPORTANT]
>
> 如果您無法存取行動行銷介面，可以直接在您的應用程式代碼的配置檔案中進行變更; 不過，它不會與使用者介面中的設定頁面同步。

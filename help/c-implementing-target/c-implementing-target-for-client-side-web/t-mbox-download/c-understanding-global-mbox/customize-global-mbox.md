---
keywords: global mbox;customize global mbox;edit at.js;at.js;implement at.js
description: 協助您自訂at.js之全域mbox的資訊。
title: 自訂全域 mbox
feature: null
subtopic: Getting Started
topic: Standard
uuid: 0f784d6e-8f36-4c26-adbf-0d56b7d6d390
translation-type: tm+mt
source-git-commit: 8bf89f30fec597b983067ec4604dba09a9ec2832
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 59%

---


# 自訂全域 mbox{#customize-a-global-mbox}

協助您自訂at.js之全域mbox的資訊。

1. 按一 **[!UICONTROL 下「管理]** >實 **[!UICONTROL 施」]**。

1. Disable **[!UICONTROL Page load enabled (Auto create global mbox)]**, then add the name of the custom global mbox that you would like to use to deliver activities from [!DNL Target].

   此自訂全域 mbox 也用於點擊追蹤。

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. 完成後按一下&#x200B;**[!UICONTROL 「儲存」]**。

1. Implement the [!DNL at.js] library on your site.

   如需 [詳細資訊，請參閱如何部署at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) 。

1. 計算您的發行轉變所需的時間。

   在您準備好使用 [!DNL Target] 時，若要開始對未來的所有活動使用您的全域 mbox，您可以繼續進行此步驟。

   更新自訂全域 mbox 的名稱以符合以上的步驟 2 中使用的名稱。

   >[!IMPORTANT]
   >
   >儲存時，您帳戶中的所有活動都會與此 mbox 同步。如果此 mbox 不在您的網站上，則所有活動將停止運作。


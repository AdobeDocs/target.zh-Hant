---
keywords: Overview and Reference
description: 使用 Target 搭配 Adobe Campaign 來最佳化電子郵件內容。
title: 將 Target 與 Adobe Campaign 整合
feature: campaign
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 51%

---


# 將 Target 與 Adobe Campaign 整合{#integrate-target-with-adobe-campaign}

Use [!DNL Target] with [!DNL Adobe Campaign] to optimize email content.

To optimize your email content--for example, to display different offers for male and female recipients--you can create a redirect offer in [!DNL Target], then use [!DNL Adobe Campaign] to manage the email offers.

開啟電子郵件時即會進行整合。When the customer opens the email, a call is made to [!DNL Target] and a dynamic version of the content appears. 內容包含所有瀏覽器皆支援的靜態影像。[!DNL Target] 會在對象或工作階段等級上追蹤對選件的反應，且這項資料會出現在 報表中。[!DNL Target]

Target 可以追蹤下列資料:

* 使用者代理
* IP 位址
* 地理位置
* 與 Target 中的訪客 ID 相關聯的區段 (遵守法律許可)
* Data from [!DNL Campaign] Datamart

具有幾項限制:

* 因為僅能使用影像，內容無法個人化。
* Tracking is not consolidated in [!DNL Adobe Campaign].
* 沒有統一的使用者體驗。

   You must use both [!DNL Target] and [!DNL Campaign] to set up different parts of the integration:

   *  中的 rawbox 和體驗[!DNL Target]
   >[!NOTE]
   >
   >使用rawbox和時，請參 [!DNL Target]閱「建立允許清單」下的重要安全性聲明，此清單指定已授權將mbox呼叫傳送至Target的主機 [](/help/administrating-target/hosts.md#allowlist)。

   * The delivery in [!DNL Campaign]



## 開始之前 {#section_FF19BF1BCA064260930BF6C141313B0E}

Before you use [!DNL Adobe Campaign] to set up your targeted email offers, set up the following in [!DNL Target]:

* Two or more [!DNL Target] redirect offers

   See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md).
* 具有每個選件的體驗以及所需[成功量度](/help/c-activities/r-success-metrics/success-metrics.md)的 Target 活動。

   請參閱[重新導向至 URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md)。

Start the activity in [!DNL Target] before setting up the [!DNL Campaign] portion of the integration.

## 在 Adobe Campaign 電子郵件中包含 Target 選件 {#section_B201BBE27A704E18AF0D553F35695837}

1. Create an email in [!DNL Adobe Campaign].
1. 在電子郵件屬性中，按一下&#x200B;**[!UICONTROL 「包含」]** > **[!UICONTROL 「Adobe Target 提供的動態影像」]**。
1. 從共用資產中選取預設影像。
1. 指定位置 (rawbox)。
1. 新增任何其他決策參數，例如收件者的性別。
1. 預覽電子郵件，並為每個選件至少選取一位收件者 (在此範例中是一男一女)。
1. In [!DNL Campaign], define the [!DNL Target] Edge server you are using to control the activity and the name of the tenant.
1. Specify the external account used for the [!DNL Adobe Experience Cloud] so you can access the resources in the [!DNL Experience Cloud].

For more information, refer to the [!DNL Adobe Campaign] documentation.

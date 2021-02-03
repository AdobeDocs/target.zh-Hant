---
keywords: 概覽和參考
description: 使用 Target 搭配 Adobe Campaign 來最佳化電子郵件內容。
title: 將 與 Adobe Campaign 整合
feature: Integrations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 51%

---


# 將 Target 與 Adobe Campaign 整合{#integrate-target-with-adobe-campaign}

使用[!DNL Target]搭配[!DNL Adobe Campaign]來最佳化電子郵件內容。

若要最佳化您的電子郵件內容——例如，為男性和女性收件者顯示不同的選件——您可以在[!DNL Target]中建立重新導向選件，然後使用[!DNL Adobe Campaign]來管理電子郵件選件。

開啟電子郵件時即會進行整合。當客戶開啟電子郵件時，會呼叫[!DNL Target]並顯示動態版本的內容。 內容包含所有瀏覽器皆支援的靜態影像。[!DNL Target] 會在對象或工作階段等級上追蹤對選件的反應，且這項資料會出現在 報表中。[!DNL Target]

Target 可以追蹤下列資料:

* 使用者代理
* IP 位址
* 地理位置
* 與 Target 中的訪客 ID 相關聯的區段 (遵守法律許可)
* 來自[!DNL Campaign] Datamart的資料

具有幾項限制:

* 因為僅能使用影像，內容無法個人化。
* 追蹤未整合在[!DNL Adobe Campaign]中。
* 沒有統一的使用者體驗。

   您必須同時使用[!DNL Target]和[!DNL Campaign]來設定整合的不同部分：

   *  中的 rawbox 和體驗[!DNL Target]
   >[!NOTE]
   >
   >使用rawbox和[!DNL Target]時，請參閱[建立允許清單下的重要安全性注意事項，此清單指定授權將mbox呼叫傳送至Target](/help/administrating-target/hosts.md#allowlist)的主機。

   * [!DNL Campaign]中的傳送



## 開始之前 {#section_FF19BF1BCA064260930BF6C141313B0E}

在使用[!DNL Adobe Campaign]設定目標電子郵件選件之前，請在[!DNL Target]中設定下列項目：

* 兩個或多個[!DNL Target]重新導向選件

   請參閱[建立重新導向選件](/help/c-experiences/c-manage-content/offer-redirect.md)。
* 具有每個選件的體驗以及所需[成功量度](/help/c-activities/r-success-metrics/success-metrics.md)的 Target 活動。

   請參閱[重新導向至 URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md)。

在設定整合的[!DNL Campaign]部分之前，先啟動[!DNL Target]中的活動。

## 在 Adobe Campaign 電子郵件中包含 Target 選件 {#section_B201BBE27A704E18AF0D553F35695837}

1. 在[!DNL Adobe Campaign]中建立電子郵件。
1. 在電子郵件屬性中，按一下&#x200B;**[!UICONTROL 「包含」]** > **[!UICONTROL 「Adobe Target 提供的動態影像」]**。
1. 從共用資產中選取預設影像。
1. 指定位置 (rawbox)。
1. 新增任何其他決策參數，例如收件者的性別。
1. 預覽電子郵件，並為每個選件至少選取一位收件者 (在此範例中是一男一女)。
1. 在[!DNL Campaign]中，定義您用來控制租用戶活動和名稱的[!DNL Target] Edge伺服器。
1. 指定[!DNL Adobe Experience Cloud]使用的外部帳戶，以便訪問[!DNL Experience Cloud]中的資源。

有關詳細資訊，請參閱[!DNL Adobe Campaign]文檔。

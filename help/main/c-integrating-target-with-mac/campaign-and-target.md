---
keywords: 概覽和參考
description: 瞭解如何搭配Adobe Campaign使用Adobe [!DNL Target] 來最佳化電子郵件內容。
title: 如何將 [!DNL Target] 與Adobe Campaign整合？
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 32%

---

# 將[!DNL Target]與Adobe Campaign整合

使用[!DNL Target]搭配[!DNL Adobe Campaign]以最佳化電子郵件內容。

若要最佳化您的電子郵件內容，您可以在[!DNL Target]中建立重新導向選件，然後使用[!DNL Adobe Campaign]來管理電子郵件選件。 例如，您可以為男性收件者和女性收件者顯示不同的優惠方案。

開啟電子郵件時即會進行整合。當客戶開啟電子郵件時，會致電[!DNL Target]，並顯示內容的動態版本。 內容包含所有瀏覽器皆支援的靜態影像。[!DNL Target]會追蹤對象或工作階段層級對優惠方案的反應，且可在[!DNL Target]個報表中找到該資料。

[!DNL Target]可以追蹤下列資料：

* 使用者代理
* IP 位址
* 地理位置
* 在[!DNL Target]中與訪客ID相關聯的區段（須受法律核准）
* 來自[!DNL Campaign]資料市場的資料

具有幾項限制:

* 因為僅能使用影像，內容無法個人化。
* 追蹤未在[!DNL Adobe Campaign]中合併。
* 沒有統一的使用者體驗。

同時使用[!DNL Target]和[!DNL Campaign]來設定整合的不同部分：

* [!DNL Target]中的原始方塊和體驗

>[!NOTE]
>
>使用 rawbox 和 [!DNL Target] 時，請參閱[建立允許清單下的重要安全性注意事項，此清單指定授權傳送 mbox 呼叫至 Target 的主機](/help/main/administrating-target/hosts.md#allowlist)。

* [!DNL Campaign]中的傳遞

## 開始之前 {#section_FF19BF1BCA064260930BF6C141313B0E}

使用[!DNL Adobe Campaign]設定目標電子郵件優惠方案之前，請先在[!DNL Target]中設定下列專案：

* 兩個或更多[!DNL Target]重新導向選件

  請參閱[建立重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md)。

* 具有每個選件的體驗以及所需[!DNL Target]成功量度[的](/help/main/c-activities/r-success-metrics/success-metrics.md)活動。

  請參閱[重新導向至 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)。

設定整合的[!DNL Target]部分之前，請先在[!DNL Campaign]中啟動活動。

## 在[!DNL Target]電子郵件中包含[!DNL Adobe Campaign]選件 {#section_B201BBE27A704E18AF0D553F35695837}

1. 在[!DNL Adobe Campaign]中建立電子郵件。
1. 在電子郵件內容中，按一下&#x200B;**[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target]**。
1. 從共用資產中選取預設影像。
1. 指定位置 (rawbox)。
1. 新增任何其他決策參數，例如收件者的性別。
1. 預覽電子郵件，並為每個產品建議至少選取一位收件者 (在此範例中是一男一女)。
1. 在[!DNL Campaign]中，定義您用來控制租使用者活動與名稱的[!DNL Target] Edge伺服器。
1. 指定用於[!DNL Adobe Experience Cloud]的外部帳戶，以便您可以存取[!DNL Experience Cloud]中的資源。

如需詳細資訊，請參閱[!DNL Adobe Campaign]檔案。

## 影片：將[!DNL Target]與[!DNL Campaign]整合

>[!VIDEO](https://video.tv.adobe.com/v/35149)

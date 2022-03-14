---
keywords: 概覽和參考
description: 瞭解如何使用Adobe [!DNL Target] 以優化電子郵件內容。
title: 如何整合 [!DNL Target] 和Adobe Campaign?
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 41%

---

# 整合 [!DNL Target] 與Adobe Campaign

使用 [!DNL Target] 與 [!DNL Adobe Campaign] 優化電子郵件內容。

要優化您的電子郵件內容，您可以在 [!DNL Target]，則使用 [!DNL Adobe Campaign] 來管理電子郵件服務。 例如，您可以顯示男性和女性收件人的不同優惠。

開啟電子郵件時即會進行整合。當客戶開啟電子郵件時，將撥打 [!DNL Target] 並顯示內容的動態版本。 內容包含所有瀏覽器皆支援的靜態影像。[!DNL Target] 會在對象或工作階段等級上追蹤對選件的反應，且這項資料會出現在 報表中。[!DNL Target]

[!DNL Target] 可以追蹤下列資料:

* 使用者代理
* IP 位址
* 地理位置
* 與中的訪問者ID關聯的段 [!DNL Target] （須經法律批准）
* 資料來源 [!DNL Campaign] 達塔馬爾

具有幾項限制:

* 因為僅能使用影像，內容無法個人化。
* 跟蹤未合併到 [!DNL Adobe Campaign]。
* 沒有統一的使用者體驗。

同時使用 [!DNL Target] 和 [!DNL Campaign] 設定整合的不同部分：

* 原始盒子和 [!DNL Target]

>[!NOTE]
>
>使用 rawbox 和 [!DNL Target] 時，請參閱[建立允許清單下的重要安全性注意事項，此清單指定授權傳送 mbox 呼叫至 Target 的主機](/help/main/administrating-target/hosts.md#allowlist)。

* 在 [!DNL Campaign]

## 開始之前 {#section_FF19BF1BCA064260930BF6C141313B0E}

使用前 [!DNL Adobe Campaign] 要設定目標電子郵件服務，請在中設定以下 [!DNL Target]:

* 兩個或多個 [!DNL Target] 重定向服務

   請參閱 [建立重定向服務](/help/main/c-experiences/c-manage-content/offer-redirect.md)。

* A [!DNL Target] 每項服務和所需體驗的活動 [成功度量](/help/main/c-activities/r-success-metrics/success-metrics.md)。

   請參閱[重新導向至 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)。

在中啟動活動 [!DNL Target] 設定前 [!DNL Campaign] 部分整合。

## 包括 [!DNL Target] 提議 [!DNL Adobe Campaign] 電子郵件 {#section_B201BBE27A704E18AF0D553F35695837}

1. 在中建立電子郵件 [!DNL Adobe Campaign]。
1. 在電子郵件屬性中，按一下&#x200B;**[!UICONTROL 「包含」]** > **[!UICONTROL 「Adobe Target 提供的動態影像」]**。
1. 從共用資產中選取預設影像。
1. 指定位置 (rawbox)。
1. 新增任何其他決策參數，例如收件者的性別。
1. 預覽電子郵件，並為每個選件至少選取一位收件者 (在此範例中是一男一女)。
1. 在 [!DNL Campaign]，定義 [!DNL Target] 您正在使用的邊緣伺服器控制活動和租戶名稱。
1. 指定用於 [!DNL Adobe Experience Cloud] 這樣您就可以訪問 [!DNL Experience Cloud]。

有關詳細資訊，請參閱 [!DNL Adobe Campaign] 文檔。

## 視頻：整合 [!DNL Target] 與 [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)

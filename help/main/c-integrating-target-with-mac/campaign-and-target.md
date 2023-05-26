---
keywords: 概覽和參考
description: 瞭解如何使用Adobe [!DNL Target] 使用Adobe Campaign最佳化電子郵件內容。
title: 如何整合 [!DNL Target] 與Adobe Campaign？
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 41%

---

# 整合 [!DNL Target] 使用Adobe Campaign

使用 [!DNL Target] 替換為 [!DNL Adobe Campaign] 以最佳化電子郵件內容。

若要最佳化您的電子郵件內容，您可以在中建立重新導向選件 [!DNL Target]，然後使用 [!DNL Adobe Campaign] 以管理電子郵件優惠方案。 例如，您可以為男性收件者和女性收件者顯示不同的優惠方案。

開啟電子郵件時即會進行整合。客戶開啟電子郵件時，會致電給 [!DNL Target] 且會出現動態版本的內容。 內容包含所有瀏覽器皆支援的靜態影像。[!DNL Target] 會在對象或工作階段等級上追蹤對選件的反應，且這項資料會出現在 報表中。[!DNL Target]

[!DNL Target] 可以追蹤下列資料:

* 使用者代理
* IP 位址
* 地理位置
* 與中的訪客ID相關聯的區段 [!DNL Target] （須經法律核准）
* 資料來源 [!DNL Campaign] 資料市場

具有幾項限制:

* 因為僅能使用影像，內容無法個人化。
* 追蹤未在中合併 [!DNL Adobe Campaign].
* 沒有統一的使用者體驗。

使用兩者 [!DNL Target] 和 [!DNL Campaign] 若要設定整合的不同部分：

* 原始方塊和中的體驗 [!DNL Target]

>[!NOTE]
>
>使用 rawbox 和 [!DNL Target] 時，請參閱[建立允許清單下的重要安全性注意事項，此清單指定授權傳送 mbox 呼叫至 Target 的主機](/help/main/administrating-target/hosts.md#allowlist)。

* 中的傳遞 [!DNL Campaign]

## 開始之前 {#section_FF19BF1BCA064260930BF6C141313B0E}

使用前 [!DNL Adobe Campaign] 若要設定目標電子郵件優惠方案，請在以下位置設定下列專案： [!DNL Target]：

* 兩個或更多 [!DNL Target] 重新導向選件

   另請參閱 [建立重新導向選件](/help/main/c-experiences/c-manage-content/offer-redirect.md).

* A [!DNL Target] 具有每個選件的體驗且符合所需體驗的活動 [成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md).

   請參閱[重新導向至 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)。

在中開始活動 [!DNL Target] 在設定之前 [!DNL Campaign] 整合的部分。

## 包含 [!DNL Target] 中的優惠方案 [!DNL Adobe Campaign] 電子郵件 {#section_B201BBE27A704E18AF0D553F35695837}

1. 在中建立電子郵件 [!DNL Adobe Campaign].
1. 在電子郵件屬性中，按一下&#x200B;**[!UICONTROL 「包含」]** > **[!UICONTROL 「Adobe Target 提供的動態影像」]**。
1. 從共用資產中選取預設影像。
1. 指定位置 (rawbox)。
1. 新增任何其他決策參數，例如收件者的性別。
1. 預覽電子郵件，並為每個選件至少選取一位收件者 (在此範例中是一男一女)。
1. 在 [!DNL Campaign]，定義 [!DNL Target] 您用來控制活動和租使用者名稱稱的Edge伺服器。
1. 指定用於的外部帳戶 [!DNL Adobe Experience Cloud] 以便您能存取 [!DNL Experience Cloud].

如需詳細資訊，請參閱 [!DNL Adobe Campaign] 說明檔案。

## 影片：整合 [!DNL Target] 替換為 [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)

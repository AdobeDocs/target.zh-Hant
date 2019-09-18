---
description: 使用 Target 搭配 Adobe Campaign 來最佳化電子郵件內容。
keywords: 概覽和參考
seo-description: 使用 Target 搭配 Adobe Campaign 來最佳化電子郵件內容。
seo-title: 將 Target 與 Adobe Campaign 整合
solution: Target
title: 將 Target 與 Adobe Campaign 整合
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2e419d331
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# 將 Target 與 Adobe Campaign 整合{#integrate-target-with-adobe-campaign}

使用 Target 搭配 Adobe Campaign 來最佳化電子郵件內容。

若要將電子郵件內容最佳化 (例如，針對男性和女性收件者，分別顯示不同選件)，您可以在 Target 中建立重新導向選件，然後利用 Adobe Campaign 來管理電子郵件選件。

開啟電子郵件時即會進行整合。當客戶開啟電子郵件時，即會呼叫 Target 並顯示動態版的內容。內容包含所有瀏覽器皆支援的靜態影像。Target 會在對象或工作階段等級上追蹤對選件的反應，且這項資料會出現在 Target 報表中。

Target 可以追蹤下列資料:

* 使用者代理
* IP 位址
* 地理位置
* 與 Target 中的訪客 ID 相關聯的區段 (遵守法律許可)
* 來自 Campaign Datamart 的資料

具有幾項限制:

* 因為僅能使用影像，內容無法個人化。
* Adobe Campaign 中不會將追蹤合併。
* 沒有統一的使用者體驗。

   您必須使用 Target 和 Campaign 來設定整合的不同部分:

   * Target 中的 rawbox 和體驗
   * Campaign 中的傳送

## 開始之前 {#section_FF19BF1BCA064260930BF6C141313B0E}

使用 Adobe Campaign 來設定鎖定目標的電子郵件選件之前，請在 Target 中設定下列各項:

* 兩個或更多個 Target 重新導向選件

   See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md).
* 具有每個選件的體驗以及所需[成功量度](/help/c-activities/r-success-metrics/success-metrics.md)的 Target 活動。

   請參閱[重新導向至 URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md)。

在設定整合的 Campaign 部分之前，請先在 Target 中啟動活動。

## 在 Adobe Campaign 電子郵件中包含 Target 選件 {#section_B201BBE27A704E18AF0D553F35695837}

1. 在 Adobe Campaign 中建立電子郵件。
1. 在電子郵件屬性中，按一下&#x200B;**[!UICONTROL 「包含]** &gt; **[!UICONTROL Adobe Target 提供的動態影像」]**。
1. 從共用資產中選取預設影像。
1. 指定位置 (rawbox)。
1. 新增任何其他決策參數，例如收件者的性別。
1. 預覽電子郵件，並為每個選件至少選取一位收件者 (在此範例中是一男一女)。
1. 在 Campaign 中，定義您用來控制活動的 Target Edge 伺服器，以及租用戶的名稱。
1. 指定用於 Experience Cloud 的外部帳戶，讓您可存取 Experience Cloud 中的資源。

如需詳細資訊，請參閱 Adobe Campaign 說明文件。

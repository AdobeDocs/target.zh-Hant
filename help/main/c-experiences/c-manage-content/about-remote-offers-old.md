---
keywords: 遠端選件；遠端選件選取矩陣；快取內容；動態內容；url型別
description: 瞭解如何使用Adobe [!DNL Target] 中的遠端選件來主控外部內容(CMS或其他系統中的內容)。 探索您為何要使用遠端選件。
title: 如何建立遠端選件？
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 29%

---

# 建立遠端選件

使用遠端選件來主控 所參考且位於 [!DNL Adobe Target][!DNL Target] 外部的內容，並傳遞至使用者的網站。基於方便使用或安全性理由，此內容可能位於內容管理(CMS)或其他系統中。

>[!NOTE]
>
>您可以在[!UICONTROL Offers] > [!UICONTROL Code Offers]頁面或[Forms體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)中建立遠端選件。 您無法在視覺化體驗撰寫器(VEC)中建立或套用遠端選件。 內容將會插入[!DNL Target]要求位置，因此這些可能不適合全域[!DNL Target]要求。
>
>[!DNL Target Classic]包含類似的功能： [!UICONTROL Offer on Your Site]和[!UICONTROL Offer Outside Test&Target]。

遠端選件的一些範例包括:

* 版本各異的交互銷售
* 動態購物車訊息
* 表單
* 計算器
* 利率更新
* 電子郵件
* 資訊站
* 語音助理

## 使用遠端選件的最佳作法 {#section_7718512D08E14121B6F6B8C38134F4BC}

在活動中使用遠端選件的最佳作法:

* 如果您的選件與[!DNL Target]要求位於相同的網域中，使用[!UICONTROL Cached]選項可讓您使用相對URL來說明您的選件位置。

  這表示當您將行銷活動從測試伺服器移至生產環境時，不需要手動變更 URL 即可自動存取內容。

* 如果您的測試涉及伺服器動態產生的資料，則[!UICONTROL Dynamic]選項可能是正確的選擇。
* 如果您只打算測試現有遠端選件內容的外觀，請使用[!UICONTROL Visual Experience Composer]來變更從內容管理系統傳回的內容外觀。
* 使用[遠端選件選擇矩陣](#reference_B23BEDD29DDD47709A7651AFD27E776B) （如下）協助您選擇最適合您特定案例的選件。 若您有任何疑問，請洽詢您的帳戶代表。

## 從「代碼選件」頁面建立遠端選件

1. 按一下「**[!UICONTROL Offers]**」，然後選取「**[!UICONTROL Code Offers]**」標籤。

   ![選件>代碼選件](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 按一下&#x200B;**[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**。

   ![建立遠端選件對話方塊](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人快速在[!UICONTROL Assets]資料庫中找到選件。

1. 指定重新導向URL型別。

   如需詳細資訊，請參閱下方的[重新導向URL型別：快取或動態](#url-type)。

1. 指定遠端選件的遠端URL。

1. 按一下 **[!UICONTROL Save]**。

## 使用表單式體驗撰寫器建立遠端選件

1. 使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)建立活動時，請選取位置以顯示&#x200B;**[!UICONTROL Content]**&#x200B;區段。

   表單式體驗撰寫器中的![內容區段](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 按一下&#x200B;**[!UICONTROL Default Content]**&#x200B;下拉式清單，然後按一下&#x200B;**[!UICONTROL Change Remote Offer]**。

   ![變更遠端選件選項](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 按一下&#x200B;**[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**。

   ![建立遠端選件對話方塊](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人快速在[!UICONTROL Assets]資料庫中找到選件。

1. 指定重新導向URL型別。

   如需詳細資訊，請參閱下方的[重新導向URL型別：快取或動態](#url-type)。

1. 指定遠端選件的遠端URL。

1. 按一下 **[!UICONTROL Save]**。

## 重新導向URL型別：快取或動態 {#url-type}

下列資訊可協助您瞭解這兩個選項之間的差異：

### 快取的URL

快取遠端選件的內容是從[!DNL Target]提供。

每兩小時，[!DNL Target]會從遠端URL擷取內容，然後將內容儲存在[!DNL Target]內。 當訪客載入的網站具有包含遠端選件的體驗時，[!DNL Target]會傳遞選件。

快取遠端選件提供增強的安全性，因為登入[!DNL Target]的人員無法變更內容。 若要變更內容，此人需要登入內容管理或其他系統，然後在那裡變更內容。

您可以為快取遠端選件指定絕對或相對 URL。

### 動態URL

動態遠端選件是由內容管理或其他系統提供，而非由[!DNL Target]提供。

當訪客載入的網站有一項體驗包含遠端選件時，您可能不想讓[!DNL Target]定期快取內容再傳送。 反之，您會想要呼叫裝載內容的系統，可能傳入特定資訊，使得傳回的選件可針對每位使用者動態（或不同）。 例如，如果使用者為了信用卡而登入的網站有一項體驗包含動作遠端選件，您可以將參數傳入 URL 中，以取得使用者的帳戶資訊。然後，網站會提供使用者特有的資訊，例如帳戶餘額。

您可以按一下&#x200B;**[!UICONTROL Add Parameter]**&#x200B;新增一或多個[!DNL Target]要求或要求引數。

## 在活動中使用遠端選件

您必須使用[!UICONTROL Form-Based Experience Composer]套用遠端選件。 您目前無法使用VEC套用遠端選件。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer]是非視覺化體驗和選件建立介面，適合在視覺化體驗撰寫器無法使用或不實用的情況下，用於建立可供[!UICONTROL A/B Tests]、[!UICONTROL Experience Targeting] (XT)、[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Recommendations]活動使用的體驗。 例如，您可能會使用[!UICONTROL Form-Based Experience Composer]來建立使用遠端選件的體驗。

1. 在[!UICONTROL Form-Based Experience Composer]中建立或編輯活動。

   如需詳細逐步指示，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

1. 指定所需位置，並視需要新增任何對象細分。

1. 按一下&#x200B;**[!UICONTROL Content]**&#x200B;區段中的下拉式清單，然後按一下&#x200B;**[!UICONTROL Change Remote Offer]**。

   ![變更遠端選件選項](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 從[!UICONTROL Select Remote Offer]對話方塊中選取所需的遠端選件，然後按一下&#x200B;**[!UICONTROL Done]**。

1. 完成活動的設定。

## 動態遠端選件如何運作 {#concept_CC2A969420B34364A9FA78C1CE251818}

動態遠端選件會使用動態頁面技術，將數值傳遞給選件。

轉譯頁面之後，即會排除選件。不可見的iframe會收集資料、從框架複製資料，並在頁面上插入，以載入您傳遞的值。

![remote_offer_howitworks_2圖片](assets/remote_offer_howitworks_2.jpeg)

## 遠端選件選擇矩陣 {#reference_B23BEDD29DDD47709A7651AFD27E776B}

遠端選件選擇矩陣可協助您決定要選擇的遠端選件型別： [!UICONTROL Cached]或[!UICONTROL Dynamic]。

| 功能 | 已快取 | 動態 |
|--- |--- |--- |
| 每次訪客請求時更新 | 無 | 是 |
| 內容更新 | 每 2 個小時快取 | 每次要求時立即更新 |
| 載入時間 | 更快 | 較慢，因為處理請求 |
| 可在頁面上看到 JavaScript | 是 | 否，但可以透過 URL 傳遞 |
| 選件可以包含 JavaScript | 是 | 是 |
| 選件 URL | 絕對或相對 | 相對 |
| 請求的電腦 | Adobe 伺服器 | 訪客的電腦，具有訪客的 Cookie |

## 訓練影片：表單式撰寫器![教學課程徽章](/help/main/assets/tutorial.png)

此影片提供表單式撰寫器的示範，您可用來建立遠端選件。

* 使用表單式體驗撰寫器建立活動
* 瞭解使用表單式體驗撰寫器與可視化體驗撰寫器的時機
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)

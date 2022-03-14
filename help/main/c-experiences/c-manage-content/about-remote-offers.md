---
keywords: 遠程提供；遠程提供選擇矩陣；快取內容；動態內容；url類型
description: 瞭解如何在Adobe中使用遠程產品 [!DNL Target] 承載外部內容（CMS或其他系統中的內容）。 瞭解您可能希望使用遠程產品的原因。
title: 如何建立遠程優惠？
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 49%

---

# 建立遠端選件

使用遠端選件來主控 所參考且位於 [!DNL Adobe Target][!DNL Target] 外部的內容，並傳遞至使用者的網站。此內容可能位於內容管理(CMS)或其他系統中，原因可能是易用性或安全性。

>[!NOTE]
>
>可在 [!UICONTROL 優惠] > [!UICONTROL 代碼優惠] 或 [Forms經驗作曲家](/help/main/c-experiences/form-experience-composer.md)。 無法在Visual Experience Composer(VEC)中建立或應用遠程優惠。 將在 [!DNL Target] 請求位置，因此這些位置很可能不適合於全球 [!DNL Target] 請求。
>
>[!DNL Target Classic] 包含類似的功能: [!UICONTROL 您網站上的選件]和 [!UICONTROL Test&amp;Target 外部的選件]。

遠端選件的一些範例包括:

* 版本各異的交互銷售
* 動態購物車訊息
* 表單
* 計算器
* 利率更新
* 電子郵件
* 亭
* 語音助理

## 使用遠程產品的最佳做法 {#section_7718512D08E14121B6F6B8C38134F4BC}

在活動中使用遠端選件的最佳作法:

* 如果您的服務位於與 [!DNL Target] 請求，使用 [!UICONTROL 快取] 選項，您可以使用相對URL來描述您的服務位置。

   這表示當您將行銷活動從測試伺服器移至生產環境時，不需要手動變更 URL 即可自動存取內容。

* 如果測試包含伺服器動態產生的資料，[!UICONTROL 「動態」]選項可能才是正確的選擇。
* 如果您只打算測試現有遠端選件內容的外觀，請使用[!UICONTROL 可視化體驗撰寫器]，以變更內容管理系統所傳回的內容的外觀和風格。
* 使用 [遠程服務選擇清單](#reference_B23BEDD29DDD47709A7651AFD27E776B) （下）幫助您選擇最適合您特定案例的服務。 若您有任何疑問，請洽詢您的帳戶代表。

## 從「代碼優惠」頁建立遠程優惠

1. 按一下&#x200B;**[!UICONTROL 「選件」]**，然後選取&#x200B;**[!UICONTROL 「代碼選件」]**&#x200B;索引標籤。

   ![優惠>代碼優惠](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]** > **[!UICONTROL 「遠端選件」]**。

   ![「建立遠程服務」對話框](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在[!UICONTROL 資產]資料庫中快速尋找選件。

1. 指定重定向URL類型。

   請參閱 [重定向URL類型：快取或動態](#url-type) 下面的。

1. 指定遠端選件的遠端 URL.

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 使用基於表單的經驗編寫器建立遠程服務

1. 使用建立活動時 [基於表單的體驗作曲家](/help/main/c-experiences/form-experience-composer.md)，選擇顯示 **[!UICONTROL 內容]** 的子菜單。

   ![基於表單的體驗作曲家中的內容部分](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 按一下 **[!UICONTROL 預設內容]** 下拉清單，然後按一下 **[!UICONTROL 更改遠程服務]**。

   ![更改遠程選項](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]** > **[!UICONTROL 「遠端選件」]**。

   ![「建立遠程服務」對話框](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在[!UICONTROL 資產]資料庫中快速尋找選件。

1. 指定重定向URL類型。

   請參閱 [重定向URL類型：快取或動態](#url-type) 下面的。

1. 指定遠端選件的遠端 URL.

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 重定向URL類型：快取或動態 {#url-type}

以下資訊有助於您瞭解兩個選項之間的差異：

### 快取的URL

快取遠端選件的內容由 [!DNL Target] 提供。

[!DNL Target] 每兩小時會從遠端 URL 擷取內容，然後將內容儲存在 [!DNL Target] 內。當訪客載入的網站有一個體驗包含遠端選件時，[!DNL Target] 會傳送此選件。

快取的遠程服務提供了增強的安全性，因為有人登錄到 [!DNL Target] 無法更改內容。 若要變更內容，此人需要登入內容管理或其他系統，然後在那裡變更內容。

您可以為快取遠端選件指定絕對或相對 URL。

### 動態URL

動態遠端選件由內容管理或其他系統提供，而非由 [!DNL Target] 提供。

每當訪客載入的網站有一項體驗包含遠端選件時，您可能不想讓 [!DNL Target] 定期快取內容再傳送。相反，您希望調用承載內容的系統，可能會傳遞特定資訊，以便返回的服務對於每個用戶都是動態的（或不同的）。 例如，如果使用者為了信用卡而登入的網站有一項體驗包含動作遠端選件，您可以將參數傳入 URL 中，以取得使用者的帳戶資訊。然後，網站會提供使用者特有的資訊，例如帳戶餘額。

您可以按一下 **[!UICONTROL 添加參數]** 添加一個或多個 [!DNL Target] 請求或請求參數。

## 在活動中使用遠程服務

您必須使用 [!UICONTROL 基於表單的體驗作曲家]。 當前無法使用VEC應用遠程優惠。

的 [!DNL Adobe Target] [!UICONTROL 基於表單的體驗作曲家] 是一種非視覺體驗，提供建立介面，在建立體驗時非常有用，可在 [!UICONTROL A/BTest]。 [!UICONTROL 體驗目標] (XT), [!UICONTROL Automated Personalization] （美聯社） [!UICONTROL Recommendations] 當視覺體驗作曲家不可用或無法使用時進行活動。 例如，您可以使用 [!UICONTROL 基於表單的體驗作曲家] 建立使用遠程產品的體驗。

1. 建立或編輯 [!UICONTROL 基於表單的體驗作曲家]。

   請參閱 [基於表單的體驗作曲家](/help/main/c-experiences/form-experience-composer.md) 詳細的逐步說明。

1. 指定所需位置並根據需要添加任何訪問群體細化。

1. 按一下 **[!UICONTROL 內容]** ，然後按一下 **[!UICONTROL 更改遠程服務]**。

   ![更改遠程選項](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 從 [!UICONTROL 選擇遠程優惠] 對話框，然後按一下 **[!UICONTROL 完成]**。

1. 完成活動的設定。

## 動態遠程如何提供工作 {#concept_CC2A969420B34364A9FA78C1CE251818}

動態遠端選件會使用動態頁面技術，將數值傳遞給選件。

轉譯頁面之後，即會排除選件。一個不可見的iframe會收集資料，將其複製出框架，然後插入頁面，載入傳遞的值。

![](assets/remote_offer_howitworks_2.jpeg)

## 遠程服務選擇清單 {#reference_B23BEDD29DDD47709A7651AFD27E776B}

遠端選件選取矩陣可協助您決定要選擇的遠端選件類型:[!UICONTROL 已快取]或[!UICONTROL 動態]。

| 功能 | 已快取 | 動態 |
|--- |--- |--- |
| 每次訪客請求時更新 | 無 | 是 |
| 內容更新 | 每 2 個小時快取 | 每次要求時立即更新 |
| 載入時間 | 更快 | 較慢，因為處理請求 |
| 可在頁面上看到 JavaScript | 是 | 否，但可以透過 URL 傳遞 |
| 選件可以包含 JavaScript | 是 | 是 |
| 選件 URL | 絕對或相對 | 相對 |
| 請求的電腦 | Adobe 伺服器 | 訪客的電腦，具有訪客的 Cookie |

## 培訓視頻：基於表單的作曲家 ![教程徽章](/help/main/assets/tutorial.png)

此視頻提供了基於表單的作曲家的演示，您可以使用它建立遠程產品。

* 使用表單式體驗撰寫器建立活動
* 瞭解使用表單式體驗撰寫器與可視化體驗撰寫器的時機
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)

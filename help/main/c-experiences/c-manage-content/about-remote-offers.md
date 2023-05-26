---
keywords: 遠端選件；遠端選件選擇矩陣；快取內容；動態內容；url型別
description: 瞭解如何在Adobe中使用遠端選件 [!DNL Target] 託管外部內容（CMS或其他系統中的內容）。 探索您為何要使用遠端選件。
title: 如何建立遠端選件？
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 49%

---

# 建立遠端選件

使用遠端選件來主控 所參考且位於 [!DNL Adobe Target][!DNL Target] 外部的內容，並傳遞至使用者的網站。基於易於使用或安全性理由，此內容可能位於內容管理(CMS)或其他系統中。

>[!NOTE]
>
>遠端選件可建立於 [!UICONTROL 選件] > [!UICONTROL 代碼選件] 頁面或中的 [Forms體驗撰寫器](/help/main/c-experiences/form-experience-composer.md). 您無法在視覺化體驗撰寫器(VEC)中建立或套用遠端選件。 內容將插入至 [!DNL Target] 要求位置，因此這些可能不適合全域 [!DNL Target] 要求。
>
>[!DNL Target Classic] 包含類似的功能: [!UICONTROL 您網站上的選件]和 [!UICONTROL Test&amp;Target 外部的選件]。

遠端選件的一些範例包括:

* 版本各異的交互銷售
* 動態購物車訊息
* 表單
* 計算器
* 利率更新
* 電子郵件
* 資訊站
* 語音助理

## 使用遠端選件的最佳實務 {#section_7718512D08E14121B6F6B8C38134F4BC}

在活動中使用遠端選件的最佳作法:

* 如果您的選件與 [!DNL Target] 請求，使用 [!UICONTROL 已快取] 選項可讓您在描述選件位置時使用相對URL。

   這表示當您將行銷活動從測試伺服器移至生產環境時，不需要手動變更 URL 即可自動存取內容。

* 如果測試包含伺服器動態產生的資料，[!UICONTROL 「動態」]選項可能才是正確的選擇。
* 如果您只打算測試現有遠端選件內容的外觀，請使用[!UICONTROL 可視化體驗撰寫器]，以變更內容管理系統所傳回的內容的外觀和風格。
* 使用 [遠端選件選擇矩陣](#reference_B23BEDD29DDD47709A7651AFD27E776B) （下文）可協助您選擇最適合您特定案例的優惠方案。 若您有任何疑問，請洽詢您的帳戶代表。

## 從代碼選件頁面建立遠端選件

1. 按一下&#x200B;**[!UICONTROL 「選件」]**，然後選取&#x200B;**[!UICONTROL 「代碼選件」]**&#x200B;索引標籤。

   ![選件>代碼選件](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]** > **[!UICONTROL 「遠端選件」]**。

   ![建立遠端選件對話方塊](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在[!UICONTROL 資產]資料庫中快速尋找選件。

1. 指定重新導向URL型別。

   另請參閱 [重新導向URL型別：快取或動態](#url-type) 詳細資訊，請參閱下文。

1. 指定遠端選件的遠端 URL.

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 使用表單式體驗撰寫器建立遠端選件

1. 使用建立活動時 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，選取要顯示的位置 **[!UICONTROL 內容]** 區段。

   ![表單式體驗撰寫器中的內容區段](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 按一下 **[!UICONTROL 預設內容]** 下拉式清單，然後按一下 **[!UICONTROL 變更遠端選件]**.

   ![變更遠端選件選項](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]** > **[!UICONTROL 「遠端選件」]**。

   ![建立遠端選件對話方塊](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在[!UICONTROL 資產]資料庫中快速尋找選件。

1. 指定重新導向URL型別。

   另請參閱 [重新導向URL型別：快取或動態](#url-type) 詳細資訊，請參閱下文。

1. 指定遠端選件的遠端 URL.

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 重新導向URL型別：快取或動態 {#url-type}

以下資訊可協助您瞭解這兩個選項之間的差異：

### 快取URL

快取遠端選件的內容由 [!DNL Target] 提供。

[!DNL Target] 每兩小時會從遠端 URL 擷取內容，然後將內容儲存在 [!DNL Target] 內。當訪客載入的網站有一個體驗包含遠端選件時，[!DNL Target] 會傳送此選件。

快取的遠端選件提供增強的安全性，因為有人登入 [!DNL Target] 無法變更內容。 若要變更內容，此人需要登入內容管理或其他系統，然後在那裡變更內容。

您可以為快取遠端選件指定絕對或相對 URL。

### 動態URL

動態遠端選件由內容管理或其他系統提供，而非由 [!DNL Target] 提供。

每當訪客載入的網站有一項體驗包含遠端選件時，您可能不想讓 [!DNL Target] 定期快取內容再傳送。而是要呼叫裝載內容的系統，可能傳入特定資訊，以便每個使用者傳回的選件可以是動態的（或不同的）。 例如，如果使用者為了信用卡而登入的網站有一項體驗包含動作遠端選件，您可以將參數傳入 URL 中，以取得使用者的帳戶資訊。然後，網站會提供使用者特有的資訊，例如帳戶餘額。

您可以按一下 **[!UICONTROL 新增引數]** 以新增一或多個 [!DNL Target] 要求或要求引數。

## 在活動中使用遠端選件

您必須使用套用遠端選件 [!UICONTROL 表單式體驗撰寫器]. 您目前無法使用VEC套用遠端選件。

此 [!DNL Adobe Target] [!UICONTROL 表單式體驗撰寫器] 是非視覺體驗和選件建立介面，對於建立在中使用的體驗很有幫助。 [!UICONTROL A/B測試]， [!UICONTROL 體驗鎖定] (XT)， [!UICONTROL Automated Personalization] (AP)，和 [!UICONTROL Recommendations] 視覺化體驗撰寫器無法使用或不實用的活動。 例如，您可以使用 [!UICONTROL 表單式體驗撰寫器] 以建立使用遠端選件的體驗。

1. 在中建立或編輯活動 [!UICONTROL 表單式體驗撰寫器].

   另請參閱 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md) 以取得詳細的逐步指示。

1. 指定所需位置，並視需要新增任何對象細分。

1. 按一下 **[!UICONTROL 內容]** 區段，然後按一下 **[!UICONTROL 變更遠端選件]**.

   ![變更遠端選件選項](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 從中選擇所需的遠端選件 [!UICONTROL 選取遠端選件] 對話方塊，然後按一下 **[!UICONTROL 完成]**.

1. 完成活動的設定。

## 動態遠端選件的運作方式 {#concept_CC2A969420B34364A9FA78C1CE251818}

動態遠端選件會使用動態頁面技術，將數值傳遞給選件。

轉譯頁面之後，即會排除選件。不可見的iframe會收集資料、從框架複製資料，然後插入頁面上，載入您傳遞的值。

![remote_offer_howitworks_2圖片](assets/remote_offer_howitworks_2.jpeg)

## 遠端選件選擇矩陣 {#reference_B23BEDD29DDD47709A7651AFD27E776B}

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

## 訓練影片：表單式撰寫器 ![教學課程徽章](/help/main/assets/tutorial.png)

此影片提供表單式撰寫器的示範，您可用來建立遠端選件。

* 使用表單式體驗撰寫器建立活動
* 瞭解使用表單式體驗撰寫器與可視化體驗撰寫器的時機
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)

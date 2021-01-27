---
keywords: remote offer;remote offer selection matrix;cached content;dynamic content;url type
description: 我可以使用遠端選件來代管外部內容嗎？
title: 建立遠端選件
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 4109b0580ddb2809d29e75d0e5ec7ed4b5b126cf
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 54%

---


# 建立遠端選件

使用遠端選件來主控 所參考且位於 [!DNL Adobe Target][!DNL Target] 外部的內容，並傳遞至使用者的網站。此內容可能位於內容管理(CMS)或其他系統中，以方便使用或出於安全原因。

>[!NOTE]
>
>您可在[!UICONTROL 選件] > [!UICONTROL 代碼選件]頁面或[表單型體驗撰寫器](/help/c-experiences/form-experience-composer.md)中建立遠端選件。 您無法在Visual Experience Composer(VEC)中建立或套用遠端選件。 內容會插入至[!DNL Target]請求位置，因此這些位置很可能不適用於全域[!DNL Target]請求。
>
>[!DNL Target Classic] 包含類似的功能: [!UICONTROL 您網站上的選件]和 [!UICONTROL Test&amp;Target 外部的選件]。

遠端選件的一些範例包括:

* 版本各異的交互銷售
* 動態購物車訊息
* 表單
* 計算器
* 利率更新

## 從「代碼選件」頁面建立遠端選件

1. 按一下&#x200B;**[!UICONTROL 「選件」]**，然後選取&#x200B;**[!UICONTROL 「代碼選件」]**&#x200B;索引標籤。

   ![選件>程式碼選件](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]** > **[!UICONTROL 「遠端選件」]**。

   ![「建立遠程選件」對話框](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在[!UICONTROL 資產]資料庫中快速尋找選件。

1. 指定「重新導向URL」類型。

   請參閱[重新導向URL類型：如需詳細資訊，請在下方快取或Dynamic](#url-type)。

1. 指定遠端選件的遠端 URL.

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 使用表單型體驗撰寫器建立遠端選件

1. 使用[表單型體驗撰寫器](/help/c-experiences/form-experience-composer.md)建立活動時，選取要顯示&#x200B;**[!UICONTROL 內容]**&#x200B;區段的位置。

   ![表單型體驗撰寫器中的內容區段](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. 按一下「預設內容」下拉式清單，然後按一下「變更遠端選件」。********

   ![變更遠端選件選項](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 按一下&#x200B;**[!UICONTROL 「建立」]** > **[!UICONTROL 「遠端選件」]**。

   ![「建立遠程選件」對話框](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在[!UICONTROL 資產]資料庫中快速尋找選件。

1. 指定「重新導向URL」類型。

   請參閱[重新導向URL類型：如需詳細資訊，請在下方快取或Dynamic](#url-type)。

1. 指定遠端選件的遠端 URL.

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 重新導向URL類型：快取或動態{#url-type}

以下資訊可協助您瞭解兩個選項之間的差異：

### 快取的URL

快取遠端選件的內容由 [!DNL Target] 提供。

[!DNL Target] 每兩小時會從遠端 URL 擷取內容，然後將內容儲存在 [!DNL Target] 內。當訪客載入的網站有一個體驗包含遠端選件時，[!DNL Target] 會傳送此選件。

快取的遠端選件提供增強的安全性，因為登入[!DNL Target]的訪客無法變更內容。 若要變更內容，此人需要登入內容管理或其他系統，然後在那裡變更內容。

您可以為快取遠端選件指定絕對或相對 URL。

### 動態URL

動態遠端選件由內容管理或其他系統提供，而非由 [!DNL Target] 提供。

每當訪客載入的網站有一項體驗包含遠端選件時，您可能不想讓 [!DNL Target] 定期快取內容再傳送。您會改為呼叫代管內容的系統，可能會傳入特定資訊，讓傳回的選件對每個使用者都是動態（或不同）的。 例如，如果使用者為了信用卡而登入的網站有一項體驗包含動作遠端選件，您可以將參數傳入 URL 中，以取得使用者的帳戶資訊。然後，網站會提供使用者特有的資訊，例如帳戶餘額。

您可以按一下「新增參數」，新增一或多個「[!DNL Target]請求」或請求參數。****

## 在活動中使用遠端選件

您必須使用[!UICONTROL 表單型體驗撰寫器]套用遠端選件。 您目前無法使用VEC套用遠端選件。

1. 在[!UICONTROL 表單型體驗撰寫器]中建立或編輯活動。

   如需詳細的逐步指示，請參閱[表單式體驗撰寫器](/help/c-experiences/form-experience-composer.md)。

1. 指定所需位置，並視需要新增任何受眾調整。

1. 按一下&#x200B;**[!UICONTROL Content]**&#x200B;區段中的下拉式清單，然後按一下&#x200B;**[!UICONTROL 變更遠端選件]**。

   ![變更遠端選件選項](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 從[!UICONTROL 選擇遠端選件]對話方塊中選擇所要的遠端選件，然後按一下&#x200B;**[!UICONTROL 完成]**。

1. 完成活動的設定。

## 使用遠端選件的最佳範例{#section_7718512D08E14121B6F6B8C38134F4BC}

在活動中使用遠端選件的最佳作法:

* 如果您的選件與[!DNL Target]請求位於相同的網域中，則使用[!UICONTROL  Cached]選項可讓您使用相對URL來描述選件位置。

   這表示當您將行銷活動從測試伺服器移至生產環境時，不需要手動變更 URL 即可自動存取內容。

* 如果測試包含伺服器動態產生的資料，[!UICONTROL 「動態」]選項可能才是正確的選擇。
* 如果您只打算測試現有遠端選件內容的外觀，請使用[!UICONTROL 可視化體驗撰寫器]，以變更內容管理系統所傳回的內容的外觀和風格。
* 使用遠端選件選擇量表（下）協助您選擇最適合您特定案例的選件。 若您有任何疑問，請洽詢您的帳戶代表。

## 動態遠端選件如何運作{#concept_CC2A969420B34364A9FA78C1CE251818}

動態遠端選件會使用動態頁面技術，將數值傳遞給選件。

轉譯頁面之後，即會排除選件。不可見的iframe會收集資料，將其複製出影格，並插入頁面，載入您傳遞的值。

![](assets/remote_offer_howitworks_2.jpeg)

## 遠程選件選擇矩陣{#reference_B23BEDD29DDD47709A7651AFD27E776B}

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
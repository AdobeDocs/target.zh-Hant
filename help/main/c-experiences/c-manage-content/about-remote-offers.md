---
keywords: 遠端選件；快取內容；動態內容；url型別
description: 瞭解如何利用 [!DNL Target] 中的遠端選件來主控來自CMS或其他系統的外部內容。
title: 如何建立遠端選件？
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
TQID: https://experienceleague.adobe.com/maKcis5ROOKMcc3-axxGv1qJIQzC6o-Qc-Cjl8clQ1I
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1145
ht-degree: 24%

---

# 建立遠端產品建議

使用遠端選件在[!DNL Adobe Target]外部託管內容，允許[!DNL Target]參照此內容並將其傳遞給使用者網站。 基於方便使用或安全理由，此內容可以位於內容管理系統(CMS)或其他系統中。

您可以在[!UICONTROL 選件] > [!UICONTROL 代碼選件]頁面或[Forms體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)中建立遠端選件。 您無法在[!UICONTROL 視覺化體驗撰寫器] (VEC)中建立或套用遠端選件。 內容會插入[!DNL Target]要求位置，因此這些位置可能不適合全域[!DNL Target]要求。

遠端產品建議的一些範例包括:

* 版本各異的交互銷售
* 動態購物車訊息
* 表單
* 計算器
* 利率更新
* 電子郵件
* 資訊站
* 語音助理

## 使用遠端選件的最佳作法 {#section_7718512D08E14121B6F6B8C38134F4BC}

在活動中使用遠端產品建議的最佳作法:

* 支援遠端選件，位置如下：

   * A/B活動
   * 體驗鎖定目標 (XT) 活動
   * 表單式工作流程

* 不支援遠端選件：

   * [進階功能](/help/main/c-intro/intro.md#premium) (Automated Personalization (AP)、自動鎖定目標和Recommendations)
   * Multivariate Testing (MVT)，因為依賴VEC而不支援遠端選件。

* 如果您的選件與[!DNL Target]要求位於相同的網域中，使用[!UICONTROL Cached]選項可讓您使用相對URL來說明您的選件位置。

  這表示當您將活動從中繼伺服器移至生產環境時，無需手動變更URL即可自動存取內容。

* 如果測試包含伺服器動態產生的資料，[!UICONTROL 「動態」]選項可能才是正確的選擇。
* 如果您只打算測試現有遠端選件內容的外觀，請使用[!UICONTROL 可視化體驗撰寫器]，以變更內容管理系統所傳回的內容的外觀和風格。
* 使用[遠端選件選擇矩陣](#reference_B23BEDD29DDD47709A7651AFD27E776B) （如下）協助您選擇最適合您特定案例的選件。 若您有任何疑問，請洽詢您的帳戶代表。

## 從[!UICONTROL 代碼選件]頁面建立遠端選件

1. 按一下&#x200B;**[!UICONTROL 「選件」]**，然後選取&#x200B;**[!UICONTROL 「代碼選件」]**&#x200B;索引標籤。

1. 按一下&#x200B;**[!UICONTROL 建立選件]** > **[!UICONTROL 遠端選件]**。

1. 在[!UICONTROL 建立遠端選件]對話方塊中，提供選件的描述性名稱。

   描述性名稱可協助您和其他人在[!UICONTROL 選件]資料庫中快速找到選件。

1. （視條件而定）如果您有[Target Premium帳戶](/help/main/c-intro/intro.md#premium)，請選取所需的[工作區](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC)。

1. 指定重新導向URL型別。

   如需詳細資訊，請參閱下列[重新導向URL型別： [!UICONTROL 站上快取]或[!UICONTROL 站上動態]](#url-type)。

1. 指定遠端選件的絕對遠端URL。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

## 使用[!UICONTROL 表單式體驗撰寫器]建立遠端選件

1. 使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)建立活動時，請選取位置以顯示&#x200B;**[!UICONTROL 內容]**&#x200B;區段。
1. 按一下&#x200B;**[!UICONTROL 內容]**&#x200B;下拉式清單，按一下&#x200B;**[!UICONTROL 清單]**&#x200B;圖示（![清單](/help/main/assets/icons/MoreSmallList.svg)），然後按一下&#x200B;**[!UICONTROL 變更遠端選件]**。

1. 按一下&#x200B;**[!UICONTROL 建立選件]** > **[!UICONTROL 遠端選件]**。

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在[!UICONTROL 資產]資料庫中快速尋找選件。

1. （視條件而定）如果您有[Target Premium帳戶](/help/main/c-intro/intro.md#premium)，請選取所需的[工作區](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC)。

1. 指定重新導向URL型別。

   如需詳細資訊，請參閱下列[重新導向URL型別： [!UICONTROL 站上快取]或[!UICONTROL 站上動態]](#url-type)。

1. 指定遠端選件的遠端URL。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

## 重新導向URL型別： [!UICONTROL 現場快取]或[!UICONTROL 現場動態] {#url-type}

下列資訊可協助您瞭解這兩個選項之間的差異：

### [!UICONTROL 站上快取] URL

快取遠端選件的內容是從[!DNL Target]提供。

每兩小時，[!DNL Target]會從遠端URL擷取內容，然後將內容儲存在[!DNL Target]內。 當訪客載入的網站具有包含遠端選件的體驗時，[!DNL Target]會提供選件。

快取遠端選件提供增強的安全性，因為登入[!DNL Target]的人員無法變更內容。 若要變更內容，使用者必須登入內容管理或其他系統，然後在那裡變更內容。

您可以為快取遠端產品建議指定絕對或相對 URL。

### [!UICONTROL 站上動態] URL

動態遠端選件是由內容管理或其他系統提供，而非由[!DNL Target]提供。

當訪客載入的網站有一項體驗包含遠端選件時，您可能不想讓[!DNL Target]定期快取內容再傳送。 反之，您會想要呼叫裝載內容的系統，可能傳入特定資訊，使得傳回的選件可針對每位使用者動態（或不同）。 例如，如果使用者為了信用卡而登入的網站有一項體驗包含動作遠端產品建議，您可以將參數傳入 URL 中，以取得使用者的帳戶資訊。 然後，網站會提供使用者特有的資訊，例如帳戶餘額。

您可以按一下&#x200B;**[!UICONTROL 新增引數]**&#x200B;以新增一或多個[!DNL Target]要求或要求引數。

## 在活動中使用遠端選件

使用[!UICONTROL 表單式體驗撰寫器]套用遠端選件。 您目前無法使用[!UICONTROL 視覺化體驗撰寫器] (VEC)套用遠端選件。

[!DNL Adobe Target] [!UICONTROL 表單式體驗撰寫器]是一種非視覺化體驗和選件建立介面，適合在[!UICONTROL 視覺化體驗撰寫器]無法使用或不實用的情況下，用於建立可供[!UICONTROL A/B測試]、[!UICONTROL 體驗鎖定目標] (XT)、[!UICONTROL Automated Personalization] (AP)及[!UICONTROL Recommendations]活動使用的體驗。 例如，您可以使用[!UICONTROL 表單式體驗撰寫器]，建立使用遠端選件的體驗。

1. 在[!UICONTROL 表單式體驗撰寫器]中建立或編輯活動。

   如需詳細逐步指示，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

1. 指定所需位置，並視需要新增任何對象細分。

1. 按一下&#x200B;**[!UICONTROL 內容]**&#x200B;下拉式清單，按一下&#x200B;**[!UICONTROL 清單]**&#x200B;圖示（![清單](/help/main/assets/icons/MoreSmallList.svg)），然後按一下&#x200B;**[!UICONTROL 變更遠端選件]**。

1. 從[!UICONTROL 變更遠端選件]對話方塊中選取所需的遠端選件，然後按一下&#x200B;**[!UICONTROL 建立選件]** > **[!UICONTROL 遠端選件]**。

1. 完成活動的設定。

## 動態遠端選件如何運作 {#concept_CC2A969420B34364A9FA78C1CE251818}

動態遠端產品建議會使用動態頁面技術，將數值傳遞給產品建議。

轉譯頁面之後，即會排除產品建議。 不可見的iFrame會收集資料、從框架複製資料，然後插入頁面上，載入您傳遞的值。

![remote_offer_howitworks_2圖片](assets/remote_offer_howitworks_2.jpeg)

1. 訪客的瀏覽器會向您的伺服器要求頁面。

2. 瀏覽器轉譯頁面，包括mbox。

3. `mboxCreate`呼叫包含轉譯動態內容所需的引數。

4. [!DNL Target]傳回包含動態內容位置及其引數的URL。 在mbox區域中設定iFrame。

5. 瀏覽器會要求URL並在頁面中呈現。

## 遠端選件選擇矩陣 {#reference_B23BEDD29DDD47709A7651AFD27E776B}

遠端選件選擇矩陣可協助您決定要選擇哪種型別的遠端選件： [!UICONTROL 現場快取]或[!UICONTROL 現場動態]。

| 功能 | 站上快取 | 站上動態 |
|--- |--- |--- |
| 每次訪客請求時更新 | 無 | 是 |
| 內容更新 | 每兩小時快取一次 | 每次要求時立即更新 |
| 載入時間 | 更快 | 較慢，因為處理請求 |
| 可在頁面上看到 JavaScript | 是 | 否，但可以透過 URL 傳遞 |
| 產品建議可以包含 JavaScript | 是 | 是 |
| 產品建議 URL | 絕對或相對 | 相對 |
| 請求的電腦 | Adobe 伺服器 | 訪客的電腦，具有訪客的 Cookie |

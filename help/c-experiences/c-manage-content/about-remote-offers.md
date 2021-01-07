---
keywords: remote offer;remote offer selection matrix;cached content;dynamic content
description: 使用遠端選件，將Target參考的Adobe Target以外的內容裝載在網站上，並傳遞給使用者的網站。 此內容可能在內容管理或其他系統中，可能是基於易於使用或安全性理由。
title: 建立遠端選件
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 89%

---


# 建立遠端選件

使用遠端選件來主控 所參考且位於 [!DNL Adobe Target]Target 外部的內容，並傳遞至使用者的網站。此內容可能在內容管理或其他系統中，可能是基於易於使用或安全性理由。

>[!NOTE]
>
>遠端選件僅能在表單式撰寫器中建立。內容會插入至[!DNL Target]請求位置，因此這些位置很可能不適用於全域[!DNL Target]請求。
>
>[!DNL Target Classic] 包含類似的功能: [!UICONTROL 您網站上的選件]和 [!UICONTROL Test&amp;Target 外部的選件]。

遠端選件的一些範例包括:

* 版本各異的交互銷售
* 動態購物車訊息
* 表單
* 計算器
* 利率更新

**建立遠端選件:**

1. 按一下&#x200B;**[!UICONTROL 「選件」]**，然後選取&#x200B;**[!UICONTROL 「代碼選件」]**&#x200B;索引標籤。
1. 按一下&#x200B;**[!UICONTROL 「建立」]** > **[!UICONTROL 「遠端選件」]**。

   ![](assets/remote_offer_ui.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人在[!UICONTROL 資產]資料庫中快速尋找選件。

1. 指定遠端選件的遠端 URL:

   | 選項 | 說明 |
   |--- |--- |
   | 已快取 | 快取遠端選件的內容由 Target 提供。<br>[!DNL Target] 每兩小時會從遠端 URL 擷取內容，然後將內容儲存在 Target 內。當訪客載入的網站有一個體驗包含遠端選件時，Target 會傳送此選件。<br>因為登入 Target 的人無法變更內容，讓快取遠端選件得以提供增強的安全性。若要變更內容，此人需要登入內容管理或其他系統，然後在那裡變更內容。<br>您可以為快取遠端選件指定絕對或相對 URL。 |
   | 動態 | 動態遠端選件由內容管理或其他系統提供，而非由 Target 提供。<br>每當訪客載入的網站有一項體驗包含遠端選件時，您可能不想讓 Target 定期快取內容再傳送。相反地，您想要呼叫裝載內容的系統，可能傳入特定的資訊，使得傳回的選件隨著每個使用者而動態變化或不同。<br>例如，如果使用者為了信用卡而登入的網站有一項體驗包含動作遠端選件，您可以將參數傳入 URL 中，以取得使用者的帳戶資訊。然後，網站會提供使用者特有的資訊，例如帳戶餘額。<br>按一 [!UICONTROL 下「新] 增參數」以新增一或多 [!DNL Target] 個請求或請求參數。 |

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 使用遠端選件的最佳作法 {#section_7718512D08E14121B6F6B8C38134F4BC}

在活動中使用遠端選件的最佳作法:

* 如果您的選件與[!DNL Target]請求位於相同的網域中，則使用[!UICONTROL  Cached]選項可讓您使用相對URL來描述選件位置。

   這表示當您將行銷活動從測試伺服器移至生產環境時，不需要手動變更 URL 即可自動存取內容。

* 如果測試包含伺服器動態產生的資料，[!UICONTROL 「動態」]選項可能才是正確的選擇。
* 如果您只打算測試現有遠端選件內容的外觀，請使用[!UICONTROL 可視化體驗撰寫器]，以變更內容管理系統所傳回的內容的外觀和風格。
* 請使用「遠端選件選擇矩陣」，以協助您選擇最適合您的特定個案的選件。若您有任何疑問，請洽詢您的帳戶代表。

## 動態遠端選件如何運作 {#concept_CC2A969420B34364A9FA78C1CE251818}

動態遠端選件會使用動態頁面技術，將數值傳遞給選件。

轉譯頁面之後，即會排除選件。隱藏的 iframe 會收集資料、從框架複製資料並插入至網頁，和載入已傳遞的數值。

![](assets/remote_offer_howitworks_2.jpeg)

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
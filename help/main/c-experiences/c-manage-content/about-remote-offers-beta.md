---
keywords: 遠端選件；快取內容；動態內容；url型別
description: 瞭解如何在中使用遠端選件 [!DNL Target] 託管外部內容（CMS或其他系統中的內容）。
title: 如何建立遠端選件？
feature: Experiences and Offers
badgeBeta: label="Beta 版" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 有哪些 Beta 版功能。"
hide: true
hidefromtoc: true
source-git-commit: bd7e6cc206f0d38ee6672c37d836e40b8831da1c
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 21%

---

# 建立遠端選件

使用遠端選件來主控 所參考且位於 [!DNL Adobe Target][!DNL Target] 外部的內容，並傳遞至使用者的網站。此內容可能在內容管理(CMS)或其他系統中，可能是基於易於使用或安全性理由。

>[!NOTE]
>
>本文包含更新的 [!DNL Target] 目前是Beta版計劃一部分的使用者介面。 此 [!DNL Adobe Target] 團隊通常會為特定客戶啟用新功能，以進行測試和提供回饋。 在測試期間完成後，這些功能將在未來為所有客戶啟用 [!DNL Target Standard/Premium] 發行版本和發行說明中宣佈。

遠端選件可建立於 [!UICONTROL Offers] > [!UICONTROL Code Offers] 頁面或中的 [Forms體驗撰寫器](/help/main/c-experiences/form-experience-composer.md). 您無法在中建立或套用遠端選件 [!UICONTROL Visual Experience Composer] (VEC)。 內容會插入至 [!DNL Target] 要求位置，因此這些位置可能不適合全域 [!DNL Target] 要求。

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

* 如果您的選件與位於相同的網域 [!DNL Target] 請求，使用 [!UICONTROL Cached] 選項可讓您在描述選件位置時使用相對URL。

  這表示當您將活動從中繼伺服器移至生產環境時，無需手動變更URL即可自動存取內容。

* 如果您的測試涉及伺服器動態產生的資料，則 [!UICONTROL Dynamic] 選項可能是正確的選擇。
* 如果您只打算測試現有遠端選件內容的外觀，請使用 [!UICONTROL Visual Experience Composer] 變更從內容管理系統傳回之內容的外觀與風格。
* 使用 [遠端選件選擇矩陣](#reference_B23BEDD29DDD47709A7651AFD27E776B) （下文）協助您選擇最適合您特定案例的優惠方案。 若您有任何疑問，請洽詢您的帳戶代表。

## 從建立遠端選件 [!UICONTROL Code Offers] 頁面

1. 按一下 **[!UICONTROL Offers]**，然後選取 **[!UICONTROL Code Offers]** 標籤。

   ![選件>代碼選件](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. 按一下 **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

   ![建立遠端選件對話方塊](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui_new.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人快速在中找到選件 [!UICONTROL Assets] 資料庫。

1. （視條件而定）如果您擁有 [Target Premium帳戶](/help/main/c-intro/intro.md#premium)，選取所需的 [工作區](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. 指定重新導向URL型別。

   另請參閱 [重新導向URL型別：快取或動態](#url-type) 詳細資訊，請參閱下文。

1. 指定遠端選件的絕對遠端URL。

1. 按一下 **[!UICONTROL Create]**。

## 使用建立遠端選件 [!UICONTROL Form-Based Experience Composer]

1. 使用建立活動時 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)，選取要顯示的位置 **[!UICONTROL Content]** 區段。

   ![表單式體驗撰寫器中的內容區段](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 按一下 **[!UICONTROL Default Content]** 下拉式清單，然後按一下 **[!UICONTROL Change Remote Offer]**.

   ![變更遠端選件選項](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 按一下 **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![建立遠端選件對話方塊](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 為選件提供描述性名稱。

   描述性名稱可協助您和其他人快速在中找到選件 [!UICONTROL Assets] 資料庫。

1. 指定重新導向URL型別。

   另請參閱 [重新導向URL型別：快取或動態](#url-type) 詳細資訊，請參閱下文。

1. 指定遠端選件的遠端URL。

1. 按一下 **[!UICONTROL Save]**。

## 重新導向URL型別：快取或動態 {#url-type}

下列資訊可協助您瞭解這兩個選項之間的差異：

### 快取的URL

快取遠端選件的內容提供自 [!DNL Target].

每兩小時， [!DNL Target] 在遠端URL擷取內容，然後將內容儲存在內部 [!DNL Target]. 當訪客載入的網站有一項體驗包含遠端選件時， [!DNL Target] 提供選件。

快取遠端選件提供增強的安全性，因為有人員登入 [!DNL Target] 無法變更內容。 若要變更內容，某人需要記錄（或其他系統），並在那裡變更內容。

您可以為快取遠端選件指定絕對或相對 URL。

### 動態URL

動態遠端選件由內容管理或其他系統提供，而非由提供 [!DNL Target].

您可能不希望內容定期快取，然後由傳送 [!DNL Target] 每當訪客載入的網站有一項體驗包含遠端選件時。 反之，您會想要呼叫裝載內容的系統，可能傳入特定資訊，使得傳回的選件可針對每位使用者動態（或不同）。 例如，如果使用者為了信用卡而登入的網站有一項體驗包含動作遠端選件，您可以將參數傳入 URL 中，以取得使用者的帳戶資訊。然後，網站會提供使用者特有的資訊，例如帳戶餘額。

您可以按一下 **[!UICONTROL Add Parameter]** 以新增一或多個 [!DNL Target] 要求或要求引數。

## 在活動中使用遠端選件

您必須使用套用遠端選件 [!UICONTROL Form-Based Experience Composer]. 您目前無法使用套用遠端選件 [!UICONTROL Visual Experience Composer] (VEC)。

此 [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] 是非視覺化體驗和選件建立介面，對於建立在中使用的體驗非常有用。 [!UICONTROL A/B Tests]， [!UICONTROL Experience Targeting] (XT)， [!UICONTROL Automated Personalization] (AP)，以及 [!UICONTROL Recommendations] 活動當 [!UICONTROL Visual Experience Composer] 無法使用或不實用。 例如，您可以使用 [!UICONTROL Form-Based Experience Composer] 以建立使用遠端選件的體驗。

1. 在中建立或編輯活動 [!UICONTROL Form-Based Experience Composer].

   另請參閱 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md) 以取得詳細的逐步指示。

1. 指定所需位置，並視需要新增任何對象細分。

1. 按一下 **[!UICONTROL Content]** 區段，然後按一下 **[!UICONTROL Change Remote Offer]**.

   ![變更遠端選件選項](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 從中選擇所需的遠端選件 [!UICONTROL Select Remote Offer] 對話方塊，然後按一下 **[!UICONTROL Done]**.

1. 完成活動的設定。

## 動態遠端選件如何運作 {#concept_CC2A969420B34364A9FA78C1CE251818}

動態遠端選件會使用動態頁面技術，將數值傳遞給選件。

轉譯頁面之後，即會排除選件。不可見的iFrame會收集資料、從框架複製資料，然後插入頁面上，載入您傳遞的值。

![remote_offer_howitworks_2圖片](assets/remote_offer_howitworks_2.jpeg)

1. 訪客的瀏覽器會向您的伺服器要求頁面。

2. 瀏覽器轉譯頁面，包括mbox。

3. `mboxCreate` 呼叫包含轉譯動態內容所需的引數。

4. [!DNL Target] 傳回包含動態內容位置及其引數的URL。 在mbox區域中設定iFrame。

5. 瀏覽器在頁面中要求URL並轉譯。

## 遠端選件選擇矩陣 {#reference_B23BEDD29DDD47709A7651AFD27E776B}

遠端選件選擇矩陣可協助您決定要選擇的遠端選件型別： [!UICONTROL Cached] 或 [!UICONTROL Dynamic].

| 功能 | 已快取 | 動態 |
|--- |--- |--- |
| 每次訪客請求時更新 | 無 | 是 |
| 內容更新 | 每兩小時快取一次 | 每次要求時立即更新 |
| 載入時間 | 更快 | 較慢，因為處理請求 |
| 可在頁面上看到 JavaScript | 是 | 否，但可以透過 URL 傳遞 |
| 選件可以包含 JavaScript | 是 | 是 |
| 選件 URL | 絕對或相對 | 相對 |
| 請求的電腦 | Adobe 伺服器 | 訪客的電腦，具有訪客的 Cookie |

## 訓練影片：表單式撰寫器 ![教學課程徽章](/help/main/assets/tutorial.png)

本影片提供 [!UICONTROL Form-Based Experience Composer]，可用來建立遠端選件。

* 使用建立活動 [!UICONTROL Form-Based Experience Composer]
* 瞭解何時使用 [!UICONTROL Form-Based Experience Composer] 與 [!UICONTROL Visual Experience Composer]
* 使用細分來鎖定位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)
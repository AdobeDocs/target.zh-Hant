---
keywords: 相關性;類別相關性
description: 瞭解中的類別相關性 [!DNL Adobe Target] 會自動擷取使用者造訪的類別，然後計算使用者與此類別的相關性，以便進行定位和細分。
title: 類別相關性是什麼？
feature: Audiences
exl-id: 9478a7fb-e4b5-46d9-be73-b72cb99c3e5e
source-git-commit: 80481a149d436f13bd510c4c4287d447799afbb4
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 66%

---

# 類別親和性

中的類別相關性功能 [!DNL Adobe Target] 自動擷取使用者在您網站上瀏覽的類別，然後計算每個類別的使用者相關性，以便進行定位和細分。 類別相關性有助於確保將內容定位到最有可能對該資訊採取行動的訪客。

## 將類別相關性資訊傳入 [!DNL Target] {#section_B0C8E46EEBAC4549AD90352A47787D04}

每當有使用者造訪您的網站時，這位訪客專屬的設定檔參數即會記錄在 [!DNL Target] 資料庫中。此資料會與使用者的 Cookie 緊密結合。一個有用的引數是 `user.categoryId`，指派mbox引數至產品頁面。 當訪客繼續瀏覽或返回另一個工作階段時，就可以記錄特定使用者檢視的產品類別。您也可以將類別資訊作為 Mbox 參數 `user.categoryId` 傳遞至任何 Mbox 中 (包括巢狀 Mbox) 來進行記錄，如同 URL 參數 `user.categoryId`，或傳遞至具有全域 Mbox 的 頁面參數中。[!DNL Target]請洽詢您的客戶代表以取得更多詳細資訊。

使用逗號分隔類別，以在多個類別中包含某個項目。例如:

* `user.categoryId=clothing,shoes,nike,running,nike clothing,nike shoes,nike running shoes`

根據頻率和最近一次訪客查看您的產品類別，記錄類別相似性 (如果有)。類別相關性可用來鎖定活動的目標族群。

您可在描述檔指令碼中使用 `user.categoryAffinities[]`，傳回訪客已填入的相似性陣列。如需詳細資訊，請參閱 [設定檔屬性中物件與方法下的user.categoryAffinities](/help/main/c-target/c-visitor-profile/profile-parameters.md#objects).

>[!IMPORTANT]
>
>此 `user.categoryId` 用於類別相關性演演算法的屬性與 `entity.categoryId` 屬性用於 [!DNL Adobe Target Recommendations]&#39;產品和內容建議。 需要 `user.categoryId`，才能追蹤使用者最喜愛的類別。需要 `entity.categoryId`，才能讓建議以目前頁面或目前項目的類別為依據。將兩個值傳遞至 [!DNL Target] 如果要同時使用這兩項功能。

## 類別相關性的商業案例 {#section_D6FF913E88E6486B8FBCE117CA8B253B}

訪客在某個工作階段中的活動（例如他們最常檢視的類別），可用於在後續的造訪中鎖定目標。 訪客在工作階段期間檢視的每個類別頁面皆會擷取下來，還會根據新近和頻率模型來計算其「最喜愛的」類別。然後，每當訪客返回首頁時，主圖影像區域可鎖定目標來顯示該使用者最喜愛類別的相關內容。

## 使用類別相似性的範例 {#section_A4AC0CA550924CB4875F4F4047554C18}

假設您在線上銷售樂器，並想將貝斯吉他的促銷定位在曾經表達過對吉他有興趣的訪客。您現在可以使用類別相似性來建立選件，並將此選件僅顯示給具有此類別相似性的訪客。

## 類別相關性演算法 {#section_8B86C7FF50294208866ABF16F07D5EB9}

類別相關性演算法的運作方式如下:

* 第一個類別檢視獲得10點
* 在第一次點選後每個類別各點五分
* 每點擊一個新類別，系統會從先前點擊過的所有類別中扣除 1 點
* 如果已點選（已檢視）類別，則再次點選該類別時，所有其他類別不會減去1
* 如果點擊第六個新類別，前五個類別中得分最低的類別會排除在計算之外
* 作業結束時，所有值除以 2

>[!NOTE]
>
>在單一mbox呼叫中傳遞數個類別時，中類別的順序 `categoryAffinities` 無法保證。 系統會先記錄任意類別，並計分10分。

### 範例: 類別相關性演算法

例如，在工作階段中檢視 `mens-clothing` 類別，然後 `accessories`，然後 `jewelry`，然後再次檢視 `accessories` 會產生下列相關性:

* `accessories`: 9 (+5 – 1 + 5)

* `mens-clothing`: 8 (+10 – 1 – 1)

* `jewelry`: 5 (+5)

工作階段結束且使用者稍後回到網站時，分數已減半:

* `accessories`: 4.5 (9/2)

* `mens-clothing`: 4 (8/2)

* `jewelry`: 2.5 (5/2)

假設使用者接著依序檢視 `jewelry`、`accessories`、`beauty`、`shoes` 和 `womens-clothing`:

* `accessories`: 6.5 (4.5 + 5 – 1 – 1 - 1)

* `womens-clothing`: 5 (+5)

* `jewelry`: 4.5 (2.5 + 5 – 1 – 1 - 1)

* `shoes`: 4 (+5 – 1)

* `beauty`: 3 (+5 – 1 - 1)

* 在最後點按 `womens-clothing` 後，會捨棄得分最低的類別 `mens-clothing`，其分數為 1 (4 – 1 – 1 - 1)

工作階段結束且使用者稍後回到網站時，分數已減半:

* `accessories`: 3.3 (6.5/2)

* `womens-clothing`: 2.5 (5/2)

* `jewelry`: 2.3 (4.5/2)

* `shoes`: 2 (4/2)

* `beauty`: 1.5 (3/2)

## 使用類別相關性來鎖定目標 {#concept_5750C9E6C97A40F8B062A5C16F2B5FFC}

以下小節包含的資訊可協助您使用類別相關性對象，在活動中鎖定目標。

### 建立對象來使用類別相關性 {#section_A27C600BBA664FE7A74F8FE076B78F40}

1. 從 **[!UICONTROL 受眾]** 清單，按一下 **[!UICONTROL 建立對象]**.

   或

   若要複製現有對象，請在「對象」清單中將游標移至所需對象上方，然後按一下「複製」圖示。然後您可以編輯對象以建立類似的對象。

1. 輸入描述性的對象名稱。
1. 按一下「**[!UICONTROL + 新增規則]** > **[!UICONTROL 訪客設定檔]**」。
1. 從&#x200B;**[!UICONTROL 「訪客設定檔」]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 「類別相關性」]**。

   ![訪客設定檔 > 類別相關性](assets/affinity.png)

1. 選擇所需的類別:

   ![類別相關性 > 類別](assets/affinity-category.png)

   類別包括:

   * 最喜愛的類別
   * 第一個類別
   * 第二個類別
   * 第三個類別
   * 第四個類別
   * 第五個類別

   「最喜愛的類別」和「第一個類別」選項是相同的。

1. 選擇計算器：

   * 包含 (不區分大小寫)
   * 不包含 (不區分大小寫)
   * 等於

1. 以個別一行指定每一個新的值 (例如，&quot;shoes&quot;)。
1. 按一下&#x200B;**[!UICONTROL 儲存]**。

### 在活動中使用類別相關性觀眾 {#section_91526B942D1B4AEBB8FCDF4EBFF931CF}

您可以在任何活動中使用類別相關性對象。 在三步驟引導式工作流程中，於 [!UICONTROL Target] 步驟，選擇所需的對象。

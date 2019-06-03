---
description: 關於新增使用者至您的 Target 實作; 建立工作區、使用者群組和屬性; 更新您的 Target 實作以包括 at_property 參數; 以及指定角色和權限所需工作的資訊。
keywords: 新增使用者; 專案; 使用者群組; 屬性; 工作區; 管理屬性; 屬性; at_property; 角色; 權限
seo-description: 關於新增使用者至您的 Adobe Target 實作; 建立工作區、使用者群組和屬性; 更新您的 Target 實作以包括 at_property 參數; 以及指定角色和權限所需工作的資訊。
seo-title: 設定企業權限
solution: Target
subtopic: 快速入門
title: 設定企業權限
title-outputclass: premium
topic: Premium
uuid: 2f44ecd5-5c43-49c3-b1c3-58d28531c859
badge: premium
translation-type: tm+mt
source-git-commit: 3a36b900ac3d24e515be5028ddee3d8f250023c7

---


# ![PREMIUM](/help/assets/premium.png) 設定企業權限{#configure-enterprise-permissions}

關於新增使用者至您的 Target 實作; 建立工作區、使用者群組和屬性; 更新您的 Target 實作以包括 `at_property` 參數; 以及指定角色和權限所需工作的資訊。

>[!NOTE]
>
>屬性和權限功能屬於 [Target Premium](/help/c-intro/intro.md#premium) 解決方案的一部分。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。

下表列出要建立屬性和指派使用者角色和權限，您應該執行的工作。請參閱以下各節，瞭解各工作的詳細資訊。

| 任務 | 執行於 |
|--- |--- |
| 1. 新增使用者 (可選) | [!DNL Adobe Admin Console for Enterprise] |
| 2. 建立工作區 (產品設定檔) | [!DNL Adobe Admin Console for Enterprise] |
| 3. 建立使用者群組 (可選) | [!DNL Adobe Admin Console for Enterprise] |
| 4. 建立屬性 | [!DNL Target] UI |
| 5: 更新您的實作以包括 `at_property` 參數 | [!DNL Target] UI、at.js 函數、[!DNL Adobe Launch] 或 [!DNL Dynamic Tag Management] |
| 6: 指定角色和權限 | [!DNL Adobe Admin Console for Enterprise] |

針對在 Adobe Admin Console for Enterprise 中執行的這些工作，請遵循這些步驟來存取主控台:

1. 如果您尚未登入，請前往 [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) &gt;使用您的Adobe ID登入。

   或

   如果您已登入Experience Cloud，請前往 [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com)，然後按一下頂端導覽列中的 [!UICONTROL 應用程式] 圖示&gt;按一下 **[!UICONTROL 右邊的「管理員]** 」。

1. (條件式) 如果您可以存取一個以上組織的 [!DNL Admin Console for Enterprise]，請按一下右上角或上方導覽列中的使用者頭像，然後選取需要的組織。

## 步驟 1.新增使用者 (可選) {#section_A92AF0F921B743FEB9E9033433BD816A}

開始使用新的[!UICONTROL 「屬性」]功能時，所有使用者管理必須在 [!DNL Adobe Admin Console for Enterprise] 中執行。不過，[!DNL Target] 中的所有現有使用者將會從 [!DNL Target] 移轉至 [!DNL Admin Console for Enterprise]。

1. [在「管理控制台](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE)」中，按一下頁面頂端的「 **[!UICONTROL 使用者]** 」索引標籤， **[!UICONTROL 新增使用者]** 以建立新使用者或編輯現有使用者。
1. 遵循*《企業使用者指南》*的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示。

## 步驟 2.建立工作區 (產品設定檔) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

工作區 (產品描述檔) 可讓組織將特定一組使用者指派至特定一組屬性。工作區有許多地方皆與 [!DNL Analytics] 中的報表套裝相似。

組織可以透過在 Admin Console 內建立新工作區，指派 Target 屬性至這些工作區，並將使用者從「預設工作區」組態移動至這些較新、限制存取的工作區，藉此開始利用企業權限功能。

客戶可以使用這些工作區，依地區、業務單位、網站區域或透過任何其他選擇的方式來分開存取不同團隊。

使用者可以屬於多個工作區並且甚至可具有每個工作區內不同的角色。

1. 在 Admin Console 中，按一下 **[!UICONTROL ]「產品」**，然後選取所需產品的名稱。

   ![工作區](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 建立需要的工作區 (產品設定檔):

   * **預設存取:** 所有現有活動將合併到稱為「預設存取」的單一專案。這對客戶沒有影響。所有使用者角色和功能將保持與此變更之前完全相同。

      所有透過 [!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] 和 [!DNL Target Classic] 建立的活動也會是「預設存取」工作區的一部分。您目前無法將專案從「預設存取」移動至另一個專案。

   * **新工作區 (產品設定檔):** 您可以透過下列方式，開始利用新權限功能:

      * 在 [!DNL Admin Console for Enterprise] 內建立新工作區。
      * 對工作區指派 Target 屬性。
   您可以使用這些工作區來依地區、事業單位、網站區段或透過您選擇的任何其他方法來對不同團隊劃分存取權。使用者可以屬於多個工作區並且可具有每個工作區內不同的角色。

1. 遵循*《企業使用者指南》*的[建立和管理產品組態](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)中的指示。

>[!NOTE]
>請觀看下方的訓練影片，以瞭解關於設定工作區的詳細資訊。

### 取得您的工作區ID {#workspace-id}

您必須傳遞 Workspace ID，才能在 [Target API](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) 中運用企業權限。

1. 在 [Adobe Admin Console](https://adminconsole.adobe.com) 中，按一下[!UICONTROL 產品]標籤，然後按一下左側功能表中的產品，以顯示 PLC(workspace) 清單。
1. 按一下想要的 PLC(workspace)，然後在 URL 中找出「設定檔」ID，如下所示。

   ![workspaceID](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## 步驟 3.建立使用者群組 (可選) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

您可以建立使用者群組，例如開發人員、分析人員、行銷人員、行政人員等，然後跨多個 Adobe 產品和工作區指派權限。跨不同的 Adobe 產品為新團隊成員指派所有適當的權限，就如同將它們新增至特定使用者群組一樣簡單。

1. 在 Admin Console 中，按一下頁面頂端的 **[!UICONTROL 「使用者」]** 索引標籤 &gt; **「使用者群組」]，以建立新使用者群組或編輯現有的使用者群組。[!UICONTROL **
1. 遵循[《企業使用者指南》](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)的*管理產品設定的使用者和群組*中的指示。

## 步驟 4.建立屬性 {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

屬性的啟用方式是透過新增特定名稱/值組做為參數以搭配對 Target 的任何呼叫 (mbox 和 API 等)。

屬性屬於特定管道 (Web、行動電話、電子郵件和 API/其他)。

**提示**: 請觀看下方的訓練影片，瞭解關於如何建立屬性的詳細資訊。

1. 在 [!DNL Target] 中，按一下 **[!UICONTROL 「設定]** &gt; **[!UICONTROL 屬性」]** 來顯示[!UICONTROL 「屬性」]清單。
1. 按一下 **「建立屬性」**。

   ![新屬性對話方塊](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   填寫欄位: 

   * **頻道：** 選擇屬性的所需頻道：網頁、行動應用程式、電子郵件或其他/API(例如機上盒或PlayStation主控台)。
   * **名稱 (必要):** 指定此屬性的描述性名稱。
   * **說明:** 指定此屬性的可選說明。

1. 按一下 **[!UICONTROL 「產生代碼」]** 來產生在 [5: 更新您的實作以包括 at_property 參數](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8)中執行步驟時將使用的代碼。
1. 將代碼複製到您的剪貼簿。
1. 完成時，按一下 **[!UICONTROL 「儲存」]。**

>[!NOTE]
>請觀看下方的訓練影片，以瞭解關於建立屬性的詳細資訊。

## 步驟 5: 更新您的實作以包括 at_property 參數 {#section_9B17A59807A94712BE642942442EBBC8}

若要使用 [!DNL Target] 使用者權限功能，您必須將 `at_property` 參數新增至點擊 Target (mbox、API 等等) 的任何呼叫。

**若要取得`at_property`參數程式碼:**

1. (條件式) 使用您在執行 [4. 建立屬性](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD)中的步驟時產生並儲存至剪貼簿的實作程式碼，並繼續進行步驟 2。

   或

   在 [!DNL Target] 中，按一下 **[!UICONTROL 「設定]** &gt; **[!UICONTROL 屬性」]** 來顯示[!UICONTROL 「屬性」]清單。

   1. 將滑鼠游標移至所需屬性的[!UICONTROL 「上次更新時間」]欄以顯示[!UICONTROL 「程式碼」]圖示，並按一下該圖示。

      ![屬性暫留程式碼](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. 以滑鼠右鍵按一下醒目提示的實作程式碼，以將它複製到您的剪貼簿。

      ![屬性程式碼](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. 以在先前的步驟中取得的實作程式碼更新您的 Target 實作。

   更新您的 [!DNL Target] 實作有數個方式。例如，下列方法可以用於網頁:

   * **透過「全域參數in[!DNL Adobe Launch]」：**

      如需詳細資訊，請參閱 [Adobe Experience](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension#add-global-mbox-params) Platform *Launch* 說明文件中的新增全域Mbox Params。

   * **透過以下項目中的「全域參數」[!DNL Dynamic Tag Management]：**

      ![](assets/property_token_2.png)

      如需詳細資訊，請參閱*動態標籤管理產品文件*中的[全域參數 - Adobe Target](https://docs.adobe.com/content/help/en/dtm/using/tools-reference/target.html#global-parameters---adobe-target)。

   * **透過 targetPageParams() 函數:** 請將下列程式碼放入 <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> 標籤中，於 at.js 或 mbox.js 參考的上方。

      ![](assets/property_token_1.png)

      如需關於如何對 at.js 執行此動作的資訊，請參閱 [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md)。

   * **透過 mboxCreate() 函數:**

      ![](assets/property_token_3.png)

      如需關於如何對 at.js 執行此動作的資訊，請參閱[targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) 和 [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)。

## 步驟 6: 指定角色和權限 {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. 在 Admin Console 中，按一下 **[!UICONTROL ]「產品」**，然後選取所需產品的名稱。

   ![工作區](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

   >[!NOTE]
   >
   >「屬性與權限」功能僅適用於 [Target Standard/Premium](/help/c-intro/intro.md#premium) 。您無法對[!DNL Target Classic] 使用此功能。

1. 按一下所需設定檔的名稱。
1. 按一下 **[!UICONTROL 「使用者」]**。

   「 [!UICONTROL 使用者] 」標籤會顯示該工作區中的所有使用者。

   ![設定使用者](/help/administrating-target/c-user-management/property-channel/assets/configuration_users_new.png)

1. 使用[!UICONTROL 「產品角色」]欄中每個使用者的下拉式清單，選取需要的權限角色 (核准者、編輯者或觀察者)。

   | 角色 | 說明 |
   |--- |--- |
   | 觀察者 | 可以檢視活動，但無法建立或編輯活動。 |
   | 編輯器 | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
   | 核准者 | 可以建立、編輯和啟動或停止活動。 |

   如需詳細資訊，請參閱*《企業使用者指南》*中的[在 Admin Console 中管理產品權限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 訓練影片

以下影片含有本文章探討之概念的詳細資訊。

### 如何設定 Target 工作區 (6:55)

此影片說明如何建立工作區。

* 從 Adobe Target 介面存取 Adobe Admin Console (3 個方式)
* 在 Adobe Admin Console 中設定工作區

   * 新增使用者至工作區
   * 新增屬性至工作區

* 瞭解預設工作區

>[!VIDEO](https://video.tv.adobe.com/v/19463/?captions=chi_hant)

### 如何在 Adobe Target 中建立屬性 (3:05)

* 如何在 [!DNL Adobe Target] 介面中建立屬性
* 如何產生要包括在您的屬性實作中的屬性 Token
* 讓您自己熟悉這三個實作方法:

   * Web
   * 行動應用程式
   * 電子郵件、電視盒或 API 呼叫

>[!VIDEO](https://video.tv.adobe.com/v/18990/?captions=chi_hant)

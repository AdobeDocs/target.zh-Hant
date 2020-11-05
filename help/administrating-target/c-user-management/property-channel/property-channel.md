---
keywords: workspaces;manage property;permissions;product configuration;product profile;roles;project
description: 關於建立屬性和使用屬性和權限功能的資訊，該功能可讓 Target 管理員在 Target 中建立個別的工作區 (產品設定檔)，然後根據這些工作區指派使用者個別頁面、屬性或網站的不同角色和權限。
title: 企業使用者權限
feature: user management
subtopic: Getting Started
uuid: 1961730d-2357-406f-acac-a36b7a63bd35
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '3053'
ht-degree: 81%

---


# ![PREMIUM](/help/assets/premium.png) 企業使用者權限{#enterprise-user-permissions}

Enterprise user permissions is a means of formal administering enterprise-wide user access to [!DNL Target]. Add users to [!DNL Target], assign permissions based on their roles, and create workspaces for teams based on different departments, global locations, channels, and other logical groupings. You can assign users the roles of [!UICONTROL Observer], [!UICONTROL Editor], or [!UICONTROL Approver].

## 判斷您是否擁有企業使用者權限的存取權

>[!NOTE]
>
>屬性和權限功能屬於  Premium 解決方案的一部分。[!DNL Target]在沒有 [!DNL Target] Premium 授權的 [!DNL Target] Standard 中無法使用。
>
>Your [!DNL Target] implementation can be using any version of at.js or mbox.js.

You can tell whether your organization has a Standard or Premium license by clicking the [!UICONTROL Administration] link at the top of the [!DNL Target] UI.

* **[!DNL Target Standard]客戶**:如果您看到「使 [!UICONTROL 用者] 」標籤([!UICONTROL 「管理>使用者]」)（而非「屬性」標籤），則您的組織會擁有 [!DNL Target Standard] 授權。 [!DNL Target Standard]客戶應依照「使用者」中的 [指示](/help/administrating-target/c-user-management/c-user-management/user-management.md) ，在中新增使用者並指派權限 [!DNL Adobe Admin Console]。

* **[!DNL Target Premium]客戶**:如果您看到「屬 [!UICONTROL 性] 」標籤([!UICONTROL 「管理」>「屬性]」)和「使用者」標籤 [!UICONTROL ，則您的組織會擁有][!DNL Target Premium] 授權。 [!DNL Target Premium] 客戶應該遵循本文和[設定企業權限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)中的指示。

## 開始使用企業權限之前

>[!IMPORTANT]
>
>Ensure that you read the [Caveats](/help/administrating-target/c-user-management/property-channel/property-channel.md#section_9714311B1CD9497A86F4910F8AE635E2) section below before proceeding with enterprise permissions.

## Terms and definitions used in this section {#section_F8D229544FEA41C3BC2EFD1F95AA0116}

The following terms are used throughout this section and might be new to users wanting to use the Properties and Permissions functionality in [!DNL Target] Premium.

### 屬性

Properties are similar in nature to those within [!DNL Adobe Platform Launch] in that they use a unique snippet of code to differentiate them.

Web 屬性是一組規則加上一個內嵌代碼。Web 屬性可以是一或多個網域和子網域的任何群組。

透過新增特定名稱／值對作為參數與任何呼叫（Target呼叫、api呼叫等）來啟用屬性 到 [!DNL Target].

屬性屬於特定管道 (Web、行動電話、電子郵件或 API/其他)。

### 工作區 (產品設定檔)

工作區可讓組織將特定一組使用者指派至特定一組屬性。工作區有許多地方皆與 [!DNL Adobe Analytics] 中的報表套裝相似。

Note: Workspaces are known as [!UICONTROL Product Profiles] in the [!DNL Adobe Admin Console for Enterprise].

如果您屬於多國組織，可能會有一個工作區用於歐洲網頁、屬性或網站，以及另一個工作區用於美洲網頁、屬性或網站。如果您屬於多品牌組織，則可能會有每個品牌的個別工作區。

使用者可以屬於多個工作區並且甚至可具有每個工作區內不同的角色。

Users can have different views of [!DNL Adobe Target] by moving between workspaces, similar to how [!DNL Analytics] users have different views of [!DNL Analytics] by moving between Report Suites.

工作區可以包含完全不同的對象、代碼選件和活動。

在新企業權限模型移轉之前建立的所有對象和活動將於「預設工作區」中群組在一起，以下會討論。

All activities created via [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services], and [!DNL Adobe Target Classic] will be part of the &quot;Default Workspace.&quot;

### 預設工作區

All existing workspaces (product profiles) within [!DNL Admin Console] are merged into a single workspace called &quot;Default Workspace&quot; during your organization&#39;s migration to the new Enterprise Permissions model.

>[!IMPORTANT]
>
>請勿刪除預設工作區。

All user roles and access to all [!DNL Target] functionality remains exactly the same as they were prior to the migration to the new Enterprise Permissions model.

### 使用者群組

您可以建立使用者群組，例如開發人員、分析人員、行銷人員、行政人員等，然後跨多個 Adobe 產品和工作區指派權限。跨不同的 Adobe 產品為新團隊成員指派所有適當的權限，就如同將它們新增至特定使用者群組一樣簡單。

### 角色和權限

角色和權限會決定使用者在您的 [!DNL Target] 實作中建立和管理活動所具備的存取層級。在 [!DNL Target] 中，角色包括下列:

| 角色 | 說明 |
|--- |--- |
| 核准者 | 可以建立、編輯和啟動或停止活動。 |
| 編輯器 | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
| 觀察者 | 可以檢視活動，但無法建立或編輯活動。 |
| 發行者 | 類似於「觀察者」角色（可以查看活動，但無法建立或編輯活動）。 不過，「發佈者」角色具有啟動活動的額外權限。 |

### 管道

管道是指您的 [!DNL Target] 活動傳送所在的內容類型: 網頁、行動應用程式、電子郵件訊息等。

建立新活動時，它是在目前選取的工作區中建立。您將在第一個對話方塊中看到通道選取選項，讓您選擇活動需要的通道: Web、行動應用程式、電子郵件或其他/API。

## Permissions overview {#section_DC2172520DA84605B218A5E9FB6D187A}

下列資訊說明先前在 [!DNL Target] 中執行權限的方式，以及如何使用[!UICONTROL 屬性]和[!UICONTROL 權限]功能來加以執行。

新的[!UICONTROL 權限]功能可讓您建立不同的專案 (在 [!DNL Adobe Admin Console for Enterprise] 中稱為「產品設定檔」)，以允許您為單一使用者指派不同權限，支配該使用者對每個專案的存取權利。這些獨特的專案可與 [!DNL Adobe Analytics] 中報表套裝的運作方式比較。每個專案可以有特定的使用者具有適用一組屬性的特定角色。結果是客戶將可以限制檢視、編輯和核准對其使用者的存取權根據區域、環境 (dev/stage/prod)、管道，或其他自訂條件，如下所示:

![](assets/permissions.png)

例如，特定使用者可能會有美國網站的「核准」存取權，但只有歐洲行動應用程式的「檢視」存取權。該相同使用者可能沒有 APAC 區域中 Web 和行動屬性上提供的活動的任何存取權 (甚至是檢視)。

目前的 [!DNL Target][!UICONTROL  權限]模型有三個權限角色 (觀察者、編輯者和核准者)，如下圖所示:

![](assets/permissions_1.png)

每個角色有不同層級的權限:

| 角色 | 說明 |
|--- |--- |
| 核准者 | 可以建立、編輯和啟動或停止活動。 |
| 編輯器 | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
| 觀察者 | 可以檢視活動，但無法建立或編輯活動。 |
| 發行者 | 類似於「觀察者」角色（可以查看活動，但無法建立或編輯活動）。 不過，「發佈者」角色具有啟動活動的額外權限。 |

務必注意，每個使用者的角色會套用至您的帳戶中包含 [!DNL Target] 標記的每個頁面、屬性或網站上，如下所示:

![](assets/permissions_2.png)

新的 [!DNL Target][!UICONTROL  權限]模型有相同的三個權限角色 (觀察者、編輯者和核准者)；不過，您可以為個別頁面、屬性或網站個別指派使用者的權限角色，如下所示:

![](assets/permissions_3.png)

在此範例中，Jan 具有美國首頁和美國網站的核准者權限，以及法國網站的觀察者權限。

再者，Jan 將看不到 [!DNL Target] 中她沒有權限可查看的頁面、屬性或網站，如下所示:

![](assets/permissions_4.png)

在此範例中，Jan 看不到產品頁面、俄羅斯網站和求職網站。

## 使用案例案例案例 {#section_F3CE8576959E4F4CB13BEEED38311DD8}

下列使用案例有助於瞭解屬性、專案、角色和權限如何能協助您使用 [!DNL Target] 達成您的行銷目標:

### 多國組織

如果您屬於多國組織，可能會有一個工作區用於歐洲網頁、屬性或網站，以及另一個工作區用於美洲網頁、屬性或網站。重新組織之後，使用上圖中的角色，您可以設定類似於以下的工作區和權限:

* **Jan**: Jan 是組織的美國網頁、屬性和網站的 Center of Excellence 的最佳化領導者。她很可能具有 Adobe Experience Cloud 中的系統管理員權限。

   在她的角色中，她具有美國首頁和美國網站的核准者權限。利用核准者權限，她可以建立、編輯和啟動或停止活動。

   Jan 也洽詢了法國的最佳化團隊，因此，具有法國網站的觀察者權限，該權限提供她對活動的唯讀存取。Jan 可以檢視活動，但無法建立或編輯活動。

   因為 Jan 沒有需要她看到產品頁面、俄羅斯網站或求職網站的角色，她看不到這些網站的活動。

* **Ernie**: Ernie 是組織的行銷經理，負責在美國的行銷。

   因為 Ernie 是組織的新人，並且對 Target 沒什麼經驗，他具有美國首頁、美國網站和產品頁面的編輯者權限。利用編輯者權限，Ernie 可以建立活動並在活動上線之前加以編輯，但無法核准活動的啟動—具有核准權限的某人，比方說 Jan，必須先核准活動，之後才可以將活動放入生產。

   因為 Ernie 沒有需要他看到俄羅斯網站、法國網站或求職網站的角色，他看不到這些網站的活動。

* **Diana**: Diana 現在是組織的分析師，並且已獲得美國首頁、美國網站、產品頁面、俄羅斯網站和法國網站的觀察者權限，該權限提供她對活動的唯讀存取。Diana 可以檢視活動，但無法建立或編輯活動。

   因為 Diana 沒有需要她看到求職網站的角色，她看不到這些網站的活動。

### 多品牌組織

如果您屬於多品牌組織，則可能會有每個品牌的網頁、屬性或網站的個別工作區。

重新組織之後，使用上圖中的角色，您可以設定類似於以下的專案和權限:

* **Jan**: Jan 是在醫院產品和消費者產品領域營運的醫療組織的 Center of Excellence 的最佳化領導者。她很可能具有 Adobe Experience Cloud 中的系統管理員權限。

   在她的角色中，她具有醫院網站的核准者權限。利用核准者權限，她可以建立、編輯和啟動或停止活動。

   Jan 也洽詢了消費者產品空間的最佳化團隊，因此，具有該網站的觀察者權限，該權限提供她對活動的唯讀存取。Jan 可以檢視活動，但無法建立或編輯活動。

* **Ernie**: Ernie 是組織的行銷經理，負責消費者產品領域的行銷。

   因為 Ernie 是組織的新人，並且對 Target 沒什麼經驗，他具有消費者網站的編輯者權限。利用編輯者權限，Ernie 可以建立活動並在活動上線之前加以編輯，但無法核准活動的啟動—具有消費者網站核准權限的某人，但在此情況下並非 Jan，必須先核准活動，之後才可以將活動放入生產。

   因為 Ernie 沒有需要他看到醫院網站的角色，他看不到該網站的活動。

* **Diana**: Diana 現在是組織的分析師，並且已獲授與醫院網站和消費者網站的觀察者權限，該權限提供她對活動的唯讀存取。Diana 可以檢視活動，但無法建立或編輯活動。

## Target UI Property and Permissions touchpoints {#section_3414371393BB42999A268628B5456EC9}

您可以在 [!DNL Target] UI 的多個位置看到新的權限功能。

* **工作區 (產品設定檔) 下拉式清單:**「工作區」下拉式清單顯示在[!UICONTROL 「活動」]、[!UICONTROL 「對象」]和[!UICONTROL 「選件」]頁面的頂部。選取所需的工作區以篩選清單，以僅顯示所選取工作區中的項目。

   ![](assets/workspace_drop-down.png)

* **活動建立:** 建立新活動時，它是在目前選取的工作區中建立。您將在第一個對話方塊中看到通道選取選項，讓您選擇活動需要的通道: Web、行動應用程式、電子郵件或其他/API。

   ![](assets/channel_options.png)

* **受眾建立:**&#x200B;當您建立新的受眾時，會建立在目前選取的工作區中。
* **選件建立:**&#x200B;當您建立新的選件時，會建立在目前選取的工作區中。
* **屬性頁（管理>屬性）:** 您可以使用「搜 [!UICONTROL 尋] 」方塊來搜尋 [!UICONTROL 「屬性] 」清單。

   ![](assets/properties_list.png)

## 注意事項 {#section_9714311B1CD9497A86F4910F8AE635E2}

Consider the following when using or configuring properties and permissions in [!DNL Target] Premium:

* **重要**: 請勿刪除具有活動的工作區。如果發生此情況，請洽詢客戶服務來復原這些活動。
* 使用「所有我的工作區」檢視時:

   * 您可以查看具有適當角色和權限可存取之所有工作區的活動、對象和選件。
   * 當您選取「所有我的工作區」檢視時，會在「活動」、「對象」和「選件」頁面中新增一欄，其列出與項目相關聯之該項目的工作區，以及與該項目相關聯的使用者權限 (觀察者、編輯者或核准者)，
   * 在「所有我的工作區」檢視中建立活動、對象或選件時，您必須選取要建立項目的工作區。只能選取您具有「編輯者」或「核准者」權限的工作區。
   * 在「所有我的工作區」檢視中複製活動、對象或選件時，您必須選取要複製項目的工作區。只能選取您具有「編輯者」或「核准者」權限的工作區。

* 以下「管理」頁面上的任何設定都可由任何工作區中的任何「批准者」控制：

   * 可視化體驗撰寫器
   * 報表
   * Scene7設定
   * 實施
   * 屬性
   * 主機
   * 環境
   * 回應 Token
   * 使用者

* 使用者無法將資源從一個工作區 (產品設定檔) 移動至另一個。不過支援複製。
* 從 [!DNL Audiences] 頁面檢視對象時，頁面載入的速度會低於預期。如果您以任何方式與搜尋列互動，對象會較快顯示。這是已知問題，將會在隨後的更新中修正。此問題不會影響在活動建立工作流程期間選取對象。
* 下列資源屬於新企業權限模型:

   * 在啟用客戶的權限之後，於 Target Standard/Premium 內建立的活動、對象和代碼選件。(注意: 客戶必須取得使用 Target Premium 的授權。)
   * 您可以將屬性新增至「預設工作區」中的現有活動; 不過，這可能變更。
   * 只有在 Target Premium (啟用企業權限之後) 內建立的新資源 (例如活動、代碼選件和對象) 將可供透過權限限制使用。
   * 外部資源僅可供預設工作區中的使用者使用。預設工作區中的使用者的角色將全域適用 (所有 Target 要求 和所有 Target 資源)。

* 下列資源&#x200B;*不*&#x200B;屬於新企業權限模型:

   * 影像選件
   * 所有建議資源，包括條件資料庫、設計資料庫、目錄、建議設定。
   * 在啟用企業權限之前於 Target Premium 內建立的現有資源 (例如活動、代碼選件和對象) 可供複製，但無法移至其他工作區。
   * 使用下列解決方案或方法建立的活動、對象、代碼選件、影像選件或任何其他資源，無法透過企業權限模型控制，但將成為預設工作區的一部分: Target Classic、Adobe Experience Manager (AEM)、Adobe Mobile Services 和透過 API 建立的資源。透過 API 建立的資源包括活動、對象、代碼選件和影像選件。
   * 影像選件 (儲存在 `https://[tenantName].marketing.adobe.com/content/mac/[tenantName]/target/offers.html#image-library` 下的資產) 目前無法透過企業權限模型控制。
   * clickTracking 和重新導向，只有在目的地連結或目的地頁面屬於活動中所包含屬性的一部分時才有作用。此外，使用 `targetPageParams()` 函數時，clickTracking 可能無法使用。`targetPageParamsAll()` 為建議的函數。

   [!DNL Target] 目前需要在發生追蹤所在的任何頁面上具有 `at_property` Token。In the event that the token is (1) not present, (2) not detected at the time of activity setup (within the VEC), or (3) not passed to the clickTracking Target call via the `targetPageParamsAll()` function, the metric will not be incremented and will appear as &quot;0.&quot;

   對於使用重新導向的活動也是相同的情況。目的地頁面必須具有 `at_property` Token，並且需在 VEC 內設定時辨識。

   在未來的版本中，Target 將處理不存在 `at_property` Token 的頁面或存在不同的 `at_property` Token 的頁面。

* [Adobe I/O API 呼叫](https://developers.adobetarget.com)不支援「企業使用者權限」功能。

## 常見問題 {#faqs}

企業權限相關常見問題集包括下列內容:

### 我可以將活動從一個工作區移動至另一個工作區嗎?

很抱歉，您無法將活動從一個工作區移動至另一個工作區。不過，您可以將活動複製到任何工作區，知道該報表資料將不會繼續存在。如需詳細資訊，請參閱[使用工作區時複製/編輯活動](/help/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6)中的「使用工作區時複製/編輯活動」。

移轉之前建立的活動會繼續在「預設工作區」中以相同方式執行，除非它們是經過編輯和指派的屬性。在特定工作區下的活動將採用指派給該工作區的屬性，因此，行為可能不會與移轉之前的相同。

### 即使在已指派屬性的情況下，為何仍出現錯誤訊息，指出沒有任何與此活動相關聯的屬性?

如果您已使用 [!DNL Adobe Launch] 實作 [!DNL Target]，而系統出現錯誤訊息，指出沒有任何與此活動相關聯的屬性，請使用 `targetPageParams` 函數傳送 `at_property` 參數。

### 如果重新導向頁面和活動 URL 屬於不同屬性，是否會記錄點擊追蹤轉換?

如果頁面上的頁面和活動 URL 屬於不同屬性，系統則不會記錄點擊追蹤。

假設情況如下 (同時適用於 at.js 和 mbox.js):

* Page1 屬於 Property1。
* Page2 屬於 Property2。
* 在活動中，Page1 會重新導向到 Page2，這包含點擊追蹤。

當訪客在瀏覽器中開啟 Page1 時，系統會將他重新導向至 Page2。因為 Page2 沒有傳送活動的資格，其 Target 呼叫在其回應中不會包含點擊追蹤。

如果重新導向頁面和活動 URL 屬於相同的屬性，點擊追蹤會如運期般運作。如需詳細資訊，請參閱[點擊追蹤](/help/c-activities/r-success-metrics/click-tracking.md)。

## 訓練影片

以下影片含有本文章探討之概念的詳細資訊。

### Training Video: Enterprise Permissions Training Video ![Overview badge](/help/assets/overview.png)

學習目標:

* Adobe Target 使用者可以擁有的三個角色層級
* 屬性和工作區的概念，以及這些限制和分組工作如何讓您控制使用者的存取層級
* 供您的組織考慮的不同屬性範例

>[!VIDEO](https://video.tv.adobe.com/v/19042/)

### 辦公時間：Target Premium工作區

這支影片記錄了「營業時間」，這是一項 Adobe 客戶服務團隊主導的計劃。

* 建立工作區（產品設定檔）
* 建立屬性
* 新增使用者
* 更新實作

>[!NOTE]
>
>「管 [!DNL Target] 理」功能表UI(舊稱 [!UICONTROL Setup])已重新設計，以提供改善的效能、減少發佈新功能時所需的維護時間，並改善整個產品的使用體驗。 以下視頻中的資訊通常正確；不過，選項可能位於稍微不同的位置。 更新的影片將很快發佈。

>[!VIDEO](https://video.tv.adobe.com/v/23643/)

---
keywords: 工作區；管理屬性；許可權；產品設定；產品設定檔；角色；專案；觀察者；編輯器；核准者；發佈者
description: 瞭解如何創建單獨的工作區（產品配置檔），然後為各個頁面、屬性或網站為使用者分配不同的角色和許可權。
title: 什麼是企業用戶權力，如何使用這些許可權？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Administration & Configuration
role: Admin
exl-id: 838abe87-dba7-4274-97b4-31a7905846dc
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '3165'
ht-degree: 48%

---

# 企業使用者權限

企業使用者許可權是一種正式管理整個企業的[!DNL Adobe Target]使用者存取許可權的方法。 根據不同的部門、全域位置、管道和其他邏輯群組，將使用者新增至[!DNL Target]、根據其角色指派許可權，以及建立團隊的工作區。 您可以將角色[!UICONTROL Observer]、[!UICONTROL Editor]、[!UICONTROL Approver]或[!UICONTROL Publisher]指派給使用者。

{{permissions-update}}

## 判斷您是否擁有企業使用者許可權的存取權

>[!NOTE]
>
>[!UICONTROL Properties and Permissions] 該功能屬於 Premium 解決方案的一部分 [!DNL Target] 。 如果沒有 [!DNL Target] Premium 授權，就無法在 [!DNL Target] Standard 中使用它們。 
>
>您的[!DNL Target]實作可以使用任何版本的at.js或[!DNL Adobe Experience Platform Web SDK]。

您可以區分您的組織具有的Standard或Premium授權，方法是按一下[!DNL Target] UI上方的[!UICONTROL Administration]連結。

* **[!DNL Target Standard]客戶**：如果您看見[!UICONTROL Users]標籤([!UICONTROL Administration > Users]) （而非[!UICONTROL Properties]標籤），則您的組織有[!DNL Target Standard]授權。 [!DNL Target Standard]客戶應該遵循[使用者](/help/main/administrating-target/c-user-management/c-user-management/user-management.md)中的指示，在[!DNL Adobe Admin Console]中新增使用者並指派許可權。

* **[!DNL Target Premium]客戶**：如果您看見[!UICONTROL Properties]標籤([!UICONTROL Administration > Properties])和[!UICONTROL Users]標籤，則您的組織有[!DNL Target Premium]授權。 [!DNL Target Premium] 客戶應該遵循本文和[設定企業權限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)中的指示。

## 開始使用企業許可權之前

>[!IMPORTANT]
>
>在繼續使用企業許可權之前，請務必閱讀 [下面的注意事項](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#section_9714311B1CD9497A86F4910F8AE635E2) 部分。

## 此小節中使用的字詞和定義 {#section_F8D229544FEA41C3BC2EFD1F95AA0116}

以下術語貫穿本部分，對於想要使用 Premium 中的 [!DNL Target] 屬性和許可權功能的用戶來說，這些術語可能不熟悉。

### 屬性

屬性的本質類似於[!DNL Adobe Experience Platform]中的屬性，因為它們使用唯一的程式碼片段來加以區分。

Web 屬性是一組規則加上一個內嵌代碼。Web 屬性可以是一或多個網域和子網域的任何群組。

屬性是透過將特定名稱/值組新增為引數，並搭配任何呼叫（Target呼叫、API呼叫等）來啟用[!DNL Target]。

屬性屬於特定管道 (Web、行動電話、電子郵件或 API/其他)。

### 工作區 (產品設定檔) {#workspace}

工作區可讓組織將特定一組使用者指派至特定一組屬性。工作區有許多地方皆與 [!DNL Adobe Analytics] 中的報表套裝相似。

注意：工作區在[!DNL Adobe Admin Console for Enterprise]中稱為[!UICONTROL Product Profiles]。

如果您屬於多國組織，可能會有一個工作區用於歐洲網頁、屬性或網站，以及另一個工作區用於美洲網頁、屬性或網站。如果您屬於多品牌組織，則可能會有每個品牌的個別工作區。

使用者可以屬於多個工作區並且甚至可具有每個工作區內不同的角色。

使用者可在工作區之間移動，以擁有不同的[!DNL Adobe Target]檢視，這類似於[!DNL Analytics]使用者在報表套裝之間移動，以擁有不同的[!DNL Analytics]檢視。

工作區可包含完全不同的對象、代碼選件和活動。

新企業許可權模型移轉前建立的所有對象和活動，都會分組到「預設Workspace」，如下所述。

所有透過[!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services]和[!DNL Adobe Target Classic]建立的活動都是「預設Workspace」的一部分。

### 預設工作區

在您組織移轉至新的企業許可權模型期間，[!DNL Admin Console]中的所有現有工作區（產品設定檔）都會合併至名為「預設Workspace」的單一工作區。

>[!IMPORTANT]
>
>請勿刪除預設工作區。

所有使用者角色和對所有[!DNL Target]功能的存取權，會維持與移轉至新企業許可權模型之前相同。

### 使用者群組

您可以建立使用者群組，例如開發人員、分析人員、行銷人員和高階主管。 然後您可以在多個Adobe產品和工作區之間指派許可權。 跨不同的 Adobe 產品為新團隊成員指派所有適當的權限，就如同將它們新增至特定使用者群組一樣簡單。

### 角色和許可權 {#roles-permissions}

角色和許可權決定使用者在您的實施中創建 [!DNL Target] 和管理活動所需的訪問級別。 在 中 [!DNL Target]，角色包括下列：

| 角色 | 說明 |
|--- |--- |
| [!UICONTROL Approver] | 可以建立、編輯和啟動或停止活動。 |
| [!UICONTROL Editor] | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
| [!UICONTROL Observer] | 可以檢視活動，但無法建立或編輯活動。 |
| [!UICONTROL Publisher] | 類似[!UICONTROL Observer]角色（可以檢視活動，但不能建立或編輯活動）。 但是，[!UICONTROL Publisher]角色具有啟用活動的額外許可權。 |

### 頻道

頻道是指您的[!DNL Target]活動傳送所在的內容型別：網頁、行動應用程式、電子郵件訊息等。

建立活動時，會在目前選取的工作區中建立該活動。 您會在第一個對話方塊中看到頻道選擇選項，讓您為活動選擇所需的頻道：網頁、行動應用程式、電子郵件或其他/API。

## 許可權總覽 {#section_DC2172520DA84605B218A5E9FB6D187A}

下列資訊說明先前在[!DNL Target]中強制執行許可權的方式，以及如何使用[!UICONTROL Properties]和[!UICONTROL Permissions]功能強制執行許可權。

新的[!UICONTROL Permissions]功能可讓您建立不同的專案（在[!DNL Adobe Admin Console for Enterprise]中稱為「產品設定檔」）。 專案可讓您為單一使用者指派不同許可權，且這些許可權指定該使用者存取每個專案的許可權。 這些獨特的專案可與 [!DNL Adobe Analytics] 中報表套裝的運作方式比較。每個專案可以有特定的使用者具有適用一組屬性的特定角色。結果，客戶能夠根據區域、環境（開發/舞台/prod）、頻道或其他自訂條件，限制其使用者的檢視、編輯和核准存取權，如下所示：

![許可權影像](assets/permissions.png)

例如，特定使用者可能會有美國網站的「核准」存取權，但只有歐洲行動應用程式的「檢視」存取權。該相同使用者可能沒有 APAC 區域中 Web 和行動屬性上提供的活動的任何存取權 (甚至是檢視)。

模型[!DNL Target][!UICONTROL Permissions]具有下列權限角色 （觀察者、编辑者、核准者及觀察者）。本文的插圖中未顯示觀察者角色。

![permissions_1影像](assets/permissions_1.png)

每個角色有不同層級的權限:

| 角色 | 說明 |
|--- |--- |
| 核准者 | 可以建立、編輯和啟動或停止活動。 |
| 編輯者 | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
| 觀察者 | 可以檢視活動，但無法建立或編輯活動。 |
| 發佈者 | 類似於觀察者角色 (可以查看活動，但不能建立或編輯活動)。 不過，發佈者角色具有啟用活動的額外權限。 |

務必注意，每個使用者的角色會套用至您的帳戶中包含 [!DNL Target] 標記的每個頁面、屬性或網站上，如下所示:

![permissions_2影像](assets/permissions_2.png)

新[!DNL Target][!UICONTROL Permissions]模型具有相同的三個權限角色（觀察者、編輯者和審批者）;不過，您可以為各個頁面、屬性或網站分別指派用戶的許可權角色，如下所示：

![permissions_3影像](assets/permissions_3.png)

在此範例中，Jan 具有美國首頁和美國網站的核准者權限，以及法國網站的觀察者權限。

此外，Jan在[!DNL Target]中看不到她沒有許可權檢視的頁面、屬性或網站，如下所示：

![許可權_4影像](assets/permissions_4.png)

在此範例中，Jan 看不到產品頁面、俄羅斯網站和求職網站。

## 使用案例情境 {#section_F3CE8576959E4F4CB13BEEED38311DD8}

下列使用案例有助於瞭解屬性、專案、角色和權限如何能協助您使用 [!DNL Target] 達成您的行銷目標:

### 多國組織

如果您屬於多國組織，可能會有一個工作區用於歐洲網頁、屬性或網站，以及另一個工作區用於美洲網頁、屬性或網站。重新組織之後，使用上圖中的角色，您可以設定類似於以下的工作區和權限:

* **Jan**: Jan 是組織的美國網頁、屬性和網站的 Center of Excellence 的最佳化領導者。她很可能具有 Adobe Experience Cloud 中的系統管理員權限。

  在她的角色中，她具有美國首頁和美國網站的核准者權限。透過核准者許可權，她可以建立、編輯、啟動或停止活動。

  Jan 也洽詢了法國的最佳化團隊，因此，具有法國網站的觀察者權限，該權限提供她對活動的唯讀存取。Jan 可以檢視活動，但無法建立或編輯活動。

  因為 Jan 沒有需要她看到產品頁面、俄羅斯網站或求職網站的角色，她看不到這些網站的活動。

* **Ernie**: Ernie 是組織的行銷經理，負責在美國的行銷。

  因為Ernie是組織的新人，並且對Target沒有經驗，他具有美國首頁、美國網站和產品頁面的編輯者許可權。 擁有編輯器許可權，Ernie可以在活動上線之前建立和編輯活動。 他無法核准活動的啟動 — 具有核准許可權的人（例如Jan）必須先核准活動，才能將其投入生產。

  因為 Ernie 沒有需要他看到俄羅斯網站、法國網站或求職網站的角色，他看不到這些網站的活動。

* **Diana**: Diana 現在是組織的分析師，並且已獲得美國首頁、美國網站、產品頁面、俄羅斯網站和法國網站的觀察者權限，該權限提供她對活動的唯讀存取。Diana 可以檢視活動，但無法建立或編輯活動。

  因為 Diana 沒有需要她看到求職網站的角色，她看不到這些網站的活動。

### 多品牌組織

如果您屬於多品牌組織，則可能會有每個品牌的網頁、屬性或網站的個別工作區。

重新組織之後，使用上圖中的角色，您可以設定類似於以下的專案和權限:

* **Jan**: Jan 是在醫院產品和消費者產品領域營運的醫療組織的 Center of Excellence 的最佳化領導者。她很可能具有 Adobe Experience Cloud 中的系統管理員權限。

  在她的角色中，她具有醫院網站的核准者權限。透過核准者許可權，她可以建立、編輯、啟動或停止活動。

  Jan 也洽詢了消費者產品空間的最佳化團隊，因此，具有該網站的觀察者權限，該權限提供她對活動的唯讀存取。Jan 可以檢視活動，但無法建立或編輯活動。

* **Ernie**: Ernie 是組織的行銷經理，負責消費者產品領域的行銷。

  因為Ernie是組織的新人，並且對Target沒有經驗，他具有消費者網站的編輯者許可權。 擁有編輯器許可權，Ernie可以在活動上線之前建立和編輯活動。 他無法核准活動的啟動 — 對此情境中非Jan具有「消費者網站」核准許可權的人，必須先核准活動，才能將其投入生產。

  因為 Ernie 沒有需要他看到醫院網站的角色，他看不到該網站的活動。

* **Diana**: Diana 現在是組織的分析師，並且已獲授與醫院網站和消費者網站的觀察者權限，該權限提供她對活動的唯讀存取。Diana 可以檢視活動，但無法建立或編輯活動。

## Target UI屬性和許可權接觸點 {#section_3414371393BB42999A268628B5456EC9}

您可以在 [!DNL Target] UI 的多個位置看到新的權限功能。

* **Workspace （產品設定檔）下拉式清單：** Workspace下拉式清單會顯示在[!UICONTROL Activities]、[!UICONTROL Audiences]和[!UICONTROL Offers]頁的頂端。 選取所需的工作區以篩選清單，以僅顯示所選取工作區中的項目。

* **活動建立：**&#x200B;當您建立活動時，會在目前選取的工作區中建立。 您會在第一個對話方塊中看到頻道選擇選項，讓您為活動選擇所需的頻道：網頁、行動應用程式、電子郵件或其他/API。

* **對象建立：**&#x200B;當您建立對象時，會在目前選取的工作區中建立。
* **對象清單：**&#x200B;您可以使用[!UICONTROL Audiences]頁面上的[!UICONTROL More Actions] > [!DNL Move]選項，在工作區之間移動對象。
* **優惠方案建立：**&#x200B;當您建立優惠方案時，會在目前選取的工作區中建立。
* **屬性頁面（管理>屬性）：**&#x200B;您可以使用[!UICONTROL Search]方塊來搜尋[!UICONTROL Property]清單。

## 注意事項 {#section_9714311B1CD9497A86F4910F8AE635E2}

在高級版中使用 [!DNL Target] 或配置屬性和許可權時，請考慮以下事項：

* **重要**: 請勿刪除具有活動的工作區。如果您刪除具有活動的工作區，請和Client Care合作復原這些活動。
* 使用「所有我的工作區」檢視時:

   * 您可以查看具有適當角色和權限可存取之所有工作區的活動、對象和產品建議。
   * 選取[!UICONTROL All My Workspaces]檢視時，新欄會新增至「活動」、「對象」和「選件」頁面。 此欄列示專案的工作區以及您與該專案相關聯的使用者許可權（觀察者、編輯者或核准者），
   * 在「所有我的工作區」檢視中建立活動、對象或產品建議時，您必須選取要建立項目的工作區。只能選取您具有「編輯者」或「核准者」權限的工作區。
   * 在「所有我的工作區」檢視中複製活動、對象或產品建議時，您必須選取要複製項目的工作區。只能選取您具有「編輯者」或「核准者」權限的工作區。

* 下列[!UICONTROL Administration]頁面上的任何設定可由任何工作區中的任何[!UICONTROL Approver]控制：

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
* 從 [!DNL Audiences] 頁面檢視客群時，頁面載入的速度會低於預期。如果您以任何方式與搜尋列互動，對象會較快顯示。此問題已知，並將在即將推出的更新中修正。 此問題不會影響在活動建立工作流程期間選取對象。
* 下列資源屬於新企業權限模型:

   * 在[!DNL Target Standard/Premium]內建立的活動、對象和代碼選件，可在客戶啟用許可權後使用。 （注意：客戶必須有權使用[!DNL Target Premium]。）
   * 屬性可以新增到預設Workspace中的現有活動；但是，此方法可能會有所變更。
   * 只有在Target Premium內建立的新資源（例如活動、代碼選件和對象）才能使用許可權加以限制（啟用企業許可權後）。
   * 外部資源僅可供預設工作區中的使用者使用。預設工作區中的使用者的角色將全域適用 (所有 Target 要求 和所有 Target 資源)。

* 下列資源&#x200B;*不*&#x200B;屬於新企業權限模型:

   * 影像產品建議
   * 所有建議資源，包括條件資料庫、設計資料庫、目錄、建議設定。
   * 在啟用企業許可權之前在 Target Premium 中創建的現有資源（例如活動、代碼選件和受眾）可以複製，但不能移動到其他工作區。
   * 使用下列解決方案或方法創建的活動、受眾、代碼選件、映像選件或任何其他資源不能由企業許可權模型控制，而是預設工作環境的一部分：Target經典、Adobe Experience Manager （AEM）、Adobe Systems行動服務以及通過 API 創建的資源。 透過 API 建立的資源包括活動、客群、代碼產品建議和影像產品建議。
   * 影像選件（儲存在`https://[tenantName].marketing.adobe.com/content/mac/[tenantName]/target/offers.html#image-library`下的資產）目前無法透過企業許可權模型控制。
   * 當目的地連結或目的地頁面屬於活動中所包含屬性的一部分時，clickTracking和重新導向功能就會運作。 此外，使用`targetPageParams()`函式時，clickTracking可能無法運作。 `targetPageParamsAll()` 為建議的函數。

  [!DNL Target]目前需要在發生追蹤所在的任何頁面上具有`at_property`權杖。 如果Token (1)不存在，(2)未在活動設定（VEC內）時偵測到，或(3)未透過`targetPageParamsAll()`函式傳遞至clickTracking Target呼叫，則量度不會遞增，並會顯示為「0」。

  對於使用重新導向的活動也是相同的情況。目的地頁面必須具有 `at_property` Token，並且需在 VEC 內設定時辨識。

  在未來的版本中，Target 將處理不存在 `at_property` Token 的頁面或存在不同的 `at_property` Token 的頁面。

* Adobe Developer API呼叫不支援「企業使用者許可權」功能。

## 常見問題集 {#faqs}

企業權限相關常見問題集包括下列內容:

### 如果使用者具有多個角色和權限，會如何？ {#multiple-roles}

如果使用者擁有多個角色和許可權，則會套用具有階層許可權的角色。 例如，如果使用者具有[!UICONTROL Observer]和[!UICONTROL Approver]角色，則會套用[!UICONTROL Approver]角色。

### 我可以將活動從一個工作區移動至另一個工作區嗎?

很抱歉，您無法將活動從一個工作區移動至另一個工作區。不過，您可以將活動複製到任何工作區，只要知道報告資料不會延續。 如需詳細資訊，請參閱[使用工作區時複製/編輯活動](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6)中的「使用工作區時複製/編輯活動」。

移轉之前建立的活動會繼續在「預設工作區」中以相同方式執行，除非它們是經過編輯和指派的屬性。特定工作區底下的活動會尊重指派給該工作區的屬性，因此，行為可能不會維持移轉前的狀態。

### 我能否將客群從一個工作區移動至另一個工作區？ {#move-audience}

可以，您可以使用[!UICONTROL Audiences]頁面上的[!UICONTROL More Actions]選項，在工作區之間移動對象。

1. 按一下&#x200B;**[!UICONTROL More Actions]**&#x200B;按鈕（三個點），然後按一下&#x200B;**[!UICONTROL Move]**。

   ![更多動作>移動](/help/main/administrating-target/c-user-management/property-channel/assets/move-audience.png)

1. 從&#x200B;**[!UICONTROL Workspace]**&#x200B;下拉式清單中選取所需的工作區，然後按一下&#x200B;**[!UICONTROL Move]**。

   ![選取要移至新工作區的所需對象](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-move.png)

>[!NOTE]
>
>您必須有適當的許可權才能編輯對象。 此外，對象不得用於其他活動。 如果對象正用於其他活動，而您仍想要將對象移至其他工作場所，請從正在使用對象的其他活動中移除對象。

### 即使在已指派屬性的情況下，為何仍出現錯誤訊息，指出沒有任何與此活動相關聯的屬性?

如果使用標記[!DNL Adobe Experience Platform]進行實施[!DNL Target]，並收到一條錯誤消息，指示沒有與活動關聯的屬性，請將參數與函數一起`targetPageParams`傳遞`at_property`。

### 如果重新導向的頁面和活動URL屬於不同屬性，是否會記錄點選追蹤轉換？

如果頁面上的頁面和活動 URL 屬於不同屬性，系統則不會記錄點擊追蹤。

假設有下列情況:

* Page1 屬於 Property1。
* Page2 屬於 Property2。
* 在活動中，Page1 會重新導向到 Page2，這包含點擊追蹤。

當訪客在瀏覽器中開啟 Page1 時，訪客會被重新導向至 Page2。 因為 Page2 沒有傳送活動的資格，其 Target 呼叫在其回應中不會包含點擊追蹤。

如果重新導向頁面和活動 URL 屬於相同的屬性，點擊追蹤會如運期般運作。如需詳細資訊，請參閱[點擊追蹤](/help/main/c-activities/r-success-metrics/click-tracking.md)。

## 培訓影片

以下影片含有本文章探討之概念的詳細資訊。

### 訓練 影片： 企業許可權 訓練影片 ![概覽徽章](/help/main/assets/overview.png)

學習目標:

* Adobe Target 使用者可以擁有的三個角色層級
* 屬性和工作區的概念，以及這些限制和分組工作如何讓您控制使用者的存取層級
* 供您的組織考慮的不同屬性範例

>[!VIDEO](https://video.tv.adobe.com/v/19042/)

### 辦公時間： [!DNL Target] 高級Workspaces

這支影片記錄了「辦公時間」，「辦公時間」是一項由 Adobe 客戶服務團隊主導的計劃。

* 建立工作區 (產品設定檔)
* 選擇屬性。
* 新增使用者
* 更新實施

>[!NOTE]
>
>[!DNL Target] [!UICONTROL Administration]功能表UI （先前稱為[!UICONTROL Setup]）已經過重新設計，可提供改良的效能、縮短發布新功能所需的維護時間，並改善整個產品的使用者體驗。 下列影片中的資訊正確；不過，選項的位置可能稍有不同。

>[!VIDEO](https://video.tv.adobe.com/v/23643/)

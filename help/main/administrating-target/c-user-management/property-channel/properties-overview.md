---
keywords: 新增使用者; 專案; 使用者群組; 屬性; 工作區; 管理屬性; 屬性; at_property; 角色; 權限
description: 瞭解如何向Adobe Target添加用戶；建立工作區、用戶組和屬性；更新實施；並指定角色和權限。
title: 如何配置企業權限？
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '1444'
ht-degree: 67%

---

# ![PREMIUM](/help/main/assets/premium.png) 設定企業權限

有關將用戶添加到您的 [!DNL Target] 實施；建立工作區、用戶組和屬性；更新 [!DNL Target] 包括 `at_property` 參數；並指定角色和權限。

>[!NOTE]
>
>屬性和權限功能屬於 [Target Premium](/help/main/c-intro/intro.md#premium) 解決方案的一部分。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。

下表列出要建立屬性和指派使用者角色和權限，您應該執行的工作。請參閱以下各節，瞭解各工作的詳細資訊。

| 任務 | 執行於 |
|--- |--- |
| 1。添加用戶（可選） | [!DNL Adobe Admin Console for Enterprise] |
| 2.建立工作區（產品配置檔案） | [!DNL Adobe Admin Console for Enterprise] |
| 3.建立用戶組（可選） | [!DNL Adobe Admin Console for Enterprise] |
| 4.建立屬性 | [!DNL Target] UI |
| 5:更新實施以包括 `at_property` 參數 | [!DNL Target] UI、at.js函式或中的標籤 [!DNL Adobe Experience Platform] |
| 6: 指定角色和權限 | [!DNL Adobe Admin Console for Enterprise] |

對於在 [!DNL Adobe Admin Console for Enterprise]，按照以下步驟訪問控制台：

1. 在Adobe Target，按一下 **[!UICONTROL 管理]** > **[!UICONTROL 屬性]** > **[!UICONTROL 將屬性分配給工作區]**。

   或

   轉到 [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) >如果尚未登錄，請使用Adobe ID登錄。


1. (條件式) 如果您可以存取一個以上組織的 [!DNL Admin Console for Enterprise]，請按一下右上角或上方導覽列中的使用者頭像，然後選取需要的組織。

## 步驟 1.添加用戶（可選） {#section_A92AF0F921B743FEB9E9033433BD816A}

開始使用新的[!UICONTROL 「屬性」]功能時，所有使用者管理必須在 [!DNL Adobe Admin Console for Enterprise] 中執行。不過，[!DNL Target] 中的所有現有使用者將會從 [!DNL Target] 移轉至 [!DNL Admin Console for Enterprise]。

1. [在 Admin Console 中](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE)，按一下頁面頂端的&#x200B;**[!UICONTROL 使用者]**&#x200B;索引標籤 > **[!UICONTROL 新增使用者]**，以建立新使用者或編輯現有的使用者。
1. 依照&#x200B;*企業版使用手冊*&#x200B;中的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示進行。

## 步驟 2.建立工作區（產品配置檔案） {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

工作區（產品配置檔案）允許組織將特定用戶集分配給特定的屬性集。 工作區有許多地方皆與 [!DNL Analytics] 中的報表套裝相似。

組織可以通過在以下位置建立新工作區來開始利用企業權限功能 [!DNL Admin Console]，分配 [!DNL Target] 將用戶從「預設工作區」配置移至這些較新、訪問受限的工作區。

客戶可以使用這些工作區來依地區、事業單位、網站區段或透過其選擇的任何其他方法來對不同團隊區分存取權。

使用者可以屬於多個工作區並且甚至可具有每個工作區內不同的角色。

1. 在 [!DNL Admin Console] 中，按一下&#x200B;**[!UICONTROL 產品]**，然後選取所需的產品名稱。

   ![工作區](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 建立需要的工作區 (產品設定檔):

   * **預設存取:** 所有現有活動將合併到稱為「預設存取」的單一專案。這對客戶沒有影響。所有使用者角色和功能將保持與此變更之前完全相同。

      所有透過 [!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] 和 [!DNL Target Classic] 建立的活動也會是「預設存取」工作區的一部分。您目前無法將專案從「預設存取」移動至另一個專案。

   * **新工作區 (產品設定檔):** 您可以透過下列方式，開始利用新權限功能:

      * 在 [!DNL Admin Console for Enterprise] 內建立新工作區。
      * 對工作區指派 Target 屬性。

   您可以使用這些工作區來依地區、事業單位、網站區段或透過您選擇的任何其他方法來對不同團隊劃分存取權。使用者可以屬於多個工作區並且可具有每個工作區內不同的角色。

1. 遵循&#x200B;*《企業使用者指南》*&#x200B;的[建立和管理產品組態](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)中的指示。

>[!NOTE]
>請觀看下方的訓練影片，以瞭解關於設定工作區的詳細資訊。

### 獲取工作區ID {#workspace-id}

您必須傳遞 Workspace ID，才能在 [Target API](https://developer.adobe.com/target/implement/server-side/) 中運用企業權限。

1. 在 [Adobe Admin Console](https://adminconsole.adobe.com)/tw 中，按一下[!UICONTROL 產品]標籤，然後按一下左側功能表中的產品，以顯示 PLC(workspace) 清單。
1. 按一下想要的 PLC(workspace)，然後在 URL 中找出「設定檔」ID，如下所示。

   ![workspaceID](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## 步驟 3.建立用戶組（可選） {#section_5F5CB9AA7A9F4D26953E22016DA59605}

您可以建立使用者群組，例如開發人員、分析人員、行銷人員、行政人員等，然後跨多個 Adobe 產品和工作區指派權限。跨不同的 Adobe 產品為新團隊成員指派所有適當的權限，就如同將它們新增至特定使用者群組一樣簡單。

1. 在 Admin Console 中，按一下頁面頂端的&#x200B;**[!UICONTROL 「使用者」]**&#x200B;索引標籤 > **[!UICONTROL 「使用者群組」]**，以建立新使用者群組或編輯現有的使用者群組。
1. 遵循[《企業使用者指南》](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)的&#x200B;*管理產品設定的使用者和群組*&#x200B;中的指示。

## 步驟 4.建立屬性 {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

通過將特定名稱/值對添加為帶有任何調用（目標調用、api調用等）的參數來啟用屬性 對 Target 的任何呼叫 (mbox 和 API 等)。

屬性屬於特定管道 (Web、行動電話、電子郵件和 API/其他)。

**提示**: 請觀看下方的訓練影片，瞭解關於如何建立屬性的詳細資訊。

1. 在 [!DNL Target]按一下 **[!UICONTROL 管理]** > **[!UICONTROL 屬性]** 顯示 [!UICONTROL 屬性] 清單框。
1. 按一下&#x200B;**「建立屬性」**。

   填寫欄位: 

   * **屬性名稱（必需）:** 指定屬性的描述性名稱。
   * **說明:** 指定此屬性的可選說明。
   * **管道:** 選取屬性需要的管道: Web、行動應用程式、電子郵件或其他/API (例如電視盒或 PlayStation 主控台)。

1. 按一下 **[!UICONTROL 複製]** 將代碼複製到剪貼簿中執行中的步驟時將使用的代碼 [5:更新實現以包括at_property參數](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8)。
1. 完成時，按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>請觀看下方的訓練影片，以瞭解關於建立屬性的詳細資訊。

## 第5步：更新實現以包括at_property參數 {#section_9B17A59807A94712BE642942442EBBC8}

使用 [!DNL Target] 用戶權限功能，必須添加 `at_property` 指向任何調用的參數 [!DNL Target] （目標調用、api調用等）。

**若要取得 `at_property` 參數程式碼:**

1. (條件式) 使用您在執行 [4. 建立屬性](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD)中的步驟時產生並儲存至剪貼簿的實作程式碼，並繼續進行步驟 2。

   或

   在 [!DNL Target]按一下 **[!UICONTROL 管理]** > **[!UICONTROL 屬性]** 顯示 [!UICONTROL 屬性] 清單框。

   1. 將滑鼠游標移至所需屬性的[!UICONTROL 「上次更新時間」]欄以顯示[!UICONTROL 「程式碼」]圖示，並按一下該圖示。

      ![屬性暫留程式碼](/help/main/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. 以滑鼠右鍵按一下醒目提示的實作程式碼，以將它複製到您的剪貼簿。

1. 更新 [!DNL Target] 實現代碼。

   更新您的 [!DNL Target] 實作有數個方式。例如，下列方法可以用於網頁:

   * **通過標籤中的「自定義參數」 [!DNL Adobe Experience Platform]:**

      有關詳細資訊，請參見 [添加Mbox參數](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=en#add-mbox-params) 的 *標籤概述* 文檔。

   * **通過targetPageParamsAll()函式：** 在 `<head>` 標籤，位於at.js引用上方。

      ```javascript
      <script>
       function targetPageParamsAll() {
        return {
         "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
        };
       }
      </script>
      ```

      有關如何使用at.js進行此操作的詳細資訊，請參見 [targetPageParamsAll](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/)。

## 步驟6:指定角色和權限 {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. 在 Admin Console 中，按一下&#x200B;**[!UICONTROL 產品]**，然後選取所需的產品名稱。

   ![工作區](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 按一下所需配置檔案的名稱(例如，「預設工作區」(Default Workspace))。

   ![預設工作區](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. 按一下&#x200B;**[!UICONTROL 「使用者」]**。

   [!UICONTROL 使用者]索引標籤會顯示該工作區中的所有使用者。

   ![設定使用者](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. 使用中每個用戶的下拉清單來選擇所需的權限角色（批准者、編輯器、觀察者或發佈者） [!UICONTROL 產品角色] 的雙曲餘切值。

   ![「產品角色」下拉式清單](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 角色 | 說明 |
   |--- |--- |
   | 核准者 | 可以建立、編輯和啟動或停止活動。 |
   | 編輯者 | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
   | 觀察者 | 可以檢視活動，但無法建立或編輯活動。 |
   | 發佈者 | 類似於觀察者角色 (可以查看活動，但不能建立或編輯活動)。 不過，發佈者角色具有啟用活動的額外權限。 |

   如需詳細資訊，請參閱&#x200B;*企業版使用手冊*&#x200B;中的[在 Admin Console 中管理產品權限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 培訓影片

以下影片含有本文章探討之概念的詳細資訊。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL 管理]選單 UI (之前稱為[!UICONTROL 設定]) 已經過重新設計，可提供改良的效能、縮短發佈新功能所需的維護時間，並改善整個產品的使用者體驗。 以下視頻中的資訊通常是正確的；但是，選項可能位於稍有不同的位置。 我們很快就會發佈更新的影片。

### 如何配置Adobe Target工作區(6:55) ![教程徽章](/help/main/assets/tutorial.png)

此影片說明如何建立工作區。

* 從 Adobe Target 介面存取 Adobe Admin Console (3 個方式)
* 在 Adobe Admin Console 中設定工作區

   * 新增使用者至工作區
   * 新增屬性至工作區

* 瞭解預設工作區

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### 如何在Adobe Target建立屬性(3:05) ![教程徽章](/help/main/assets/tutorial.png)

* 如何在 [!DNL Adobe Target] 介面中建立屬性
* 如何產生要包括在您的屬性實作中的屬性 Token
* 讓您自己熟悉這三個實作方法:

   * Web
   * 行動應用程式
   * 電子郵件、電視盒或 API 呼叫

>[!VIDEO](https://video.tv.adobe.com/v/18990/)

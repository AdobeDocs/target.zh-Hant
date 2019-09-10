---
description: 關於授予Adobe I/整合存取權以存取具有所需角色之所有工作區的資訊。
keywords: 整合；角色；使用者權限；admin Console
seo-description: 有關授予現有Adobe I/整合的資訊，請使用Adobe Target中所需角色的所有工作區
seo-title: 授予Adobe I/O整合存取工作區並指派Adobe Target中的角色
solution: Target
subtopic: 快速入門
title: 授予Adobe I/O整合存取工作區並指派角色
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![PREMIUM](/help/assets/premium.png) 授予Adobe I/整合存取工作區的權限並指派角色

[!UICONTROL 企業權限] 允許 [!DNL Target] 客戶使用單一組織，但將其分為不同團隊或工作流程的工作區。

>[!NOTE]
>
>屬性和權限功能屬於 [Target Premium](/help/c-intro/intro.md#premium) 解決方案的一部分。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。

[!UICONTROL 企業權限] 功能可協助您有效擴展團隊內部的最佳化程式。雖然此功能可在 [!DNL Target] UI中使用，但是Admin API會將對應的支援點按至2019年之前。在2019 [!DNL Target] 年月發行的版本中，Adobe已更新管理API，讓您可以使用整合帳戶存取組織中建立的所有工作區。因此，在舊版中，管理員API僅限於預設工作區，2019年月更新授予所有具有 [!UICONTROL 核准者] 存取權的工作區存取權。

在2019 [!DNL Target] 年月發行的版本中 [!DNL Target][!UICONTROL ，企業權限] 為客戶提供下列存取控制：

* 您可以選擇可套用整合的工作區
* 您可以將角色套用至Adobe I/整合： [!UICONTROL 核准者]、 [!UICONTROL 編輯者]或 [!UICONTROL 觀察員]。

此更新支援下列使用案例：

* 將所有工作區的Adobe I/O整合存取權授與 [!UICONTROL 「觀察員」] 角色，而不具有建立或編輯資源的權限。
* 授予Adobe I/O存取權，以適當的角色選取工作區，讓中央團隊只在少數工作區中進行API驅動的變更。
* 當團隊準備好要探索API並據以選擇角色時，讓每個團隊都擁有自己的工作區，以便自行整合。
* 混合並比對上述任何藍本。

**需要的動作**：目前針對所有工作區運用API for資源(活動、對象、選件和報告)的客戶，需要將現有的Adobe I/整合存取權授與所有工作區，以依其使用案例使用所需角色。您可以選取「產品描述檔」中的每個 [!DNL Target][!UICONTROL 「產品描述檔][!DNL Adobe Admin Console] 」，並在「 [!UICONTROL 整合] 」索引標籤中新增整合。在月發行版本之前，所有使用 [!UICONTROL 核准者] 存取的整合都會使用，無論 [!UICONTROL 「產品角色」] 下拉式清單中所做的選擇為何。您現在可以選擇所要的角色。

>[!NOTE]
>
>如果未執行此動作，則在2019 [!DNL Target] 年月發行的版本中，存取控制將會啓動，而且如果您目前的設定方式符合此條件，您將會看到存取權限。預先設定整合並無負面反應。您越早越好。視組織中的工作區數而定，此程序只需按幾下滑鼠，即可將現有的整合新增至具有所需角色的工作區。

**若要授予Adobe I/整合存取工作區及指派角色的權限：**

1. 開啓 **[Adobe Admin Console](https://adminconsole.adobe.com)**。

1. 按一下 **[!UICONTROL 「產品]** 」索引標籤，然後選取所需產品的名稱。

   ![在Adobe Admin Console中選擇產品](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 選取所要的工作區(產品描述檔)。

   ![選取產品描述檔](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![整合標籤](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (條件性)若要新增整合，請按一下 **[!UICONTROL 「新增整合]**」、選取所需的整合，然後按一下 **[!UICONTROL 「儲存]**」。

1. 從 **[!UICONTROL 「產品角色」]** 下拉式清單中，選取該工作區所要的角色：

   * [!UICONTROL 核准者]
   * [!UICONTROL 編輯器]
   * [!UICONTROL 觀察者]
   ![選擇產品描述檔角色](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)

---
description: 將Adobe I/O整合存取權授予具有所需角色的所有工作區的相關資訊。
keywords: 整合；角色；用戶權限；管理控制台
seo-description: 將現有的Adobe I/O整合存取權授與Adobe Target中所需角色的所有工作區的相關資訊
seo-title: 將Adobe I/O整合存取權授與Adobe Target中的工作區並指派角色
solution: Target
subtopic: 快速入門
title: 將Adobe I/O整合存取權授與工作區並指派角色
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![PREMIUM](/help/assets/premium.png) 授與Adobe I/O整合工作區的存取權並指派角色

[!UICONTROL 「企業權限] 」可 [!DNL Target] 讓客戶使用單一組織，但可將其分為不同團隊或工作流程的工作區。

>[!NOTE]
>
>屬性和權限功能屬於 [Target Premium](/help/c-intro/intro.md#premium) 解決方案的一部分。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。

「企 [!UICONTROL 業權限] 」功能有助於跨團隊有效縮放最佳化計畫。 雖然UI中提供此功能， [!DNL Target] 但管理員API直到2019年早些時候都未提供相應的支援。 在2019 [!DNL Target] 年2月發行版本中，Adobe更新了管理API，讓您可以使用整合帳戶存取組織中建立的所有工作區。 因此，雖然之前的管理API僅限預設工作區，但2019年2月的更新會授與具有核准者存取權的所有工作區 [!UICONTROL 的存] 取權。

在2019年9 [!DNL Target] 月發行 [!DNL Target] 時， [!UICONTROL 「企業權限] 」為客戶提供下列存取控制：

* 您可以選擇可套用整合的工作區
* 您可以將角色套用至Adobe I/O整合：核 [!UICONTROL 準者]、 [!UICONTROL 編輯者]或觀 [!UICONTROL 察者]。

此更新支援下列使用案例：

* 將Adobe I/O整合存取權授與具有 [!UICONTROL Observer] （觀察員）角色的所有工作區，以用於報告用途，但無權建立或編輯資源。
* 授與Adobe I/O整合以適當角色存取選取的工作區，讓中央團隊僅在少數幾個工作區中進行API導向的變更。
* 每當團隊準備探索API並據以選擇角色時，允許擁有其工作區的每個團隊擁有自己的整合。
* 混搭上述任何案例。

**Action Needed: Those customers who are currently leveraging APIs for CRUD operations on resources (activities, audiences, offers, and reporting) across all workspaces need to grant their existing Adobe I/O integration access to all workspaces with the desired role as per their use case.** You can do so by selecting each  Product Profile in the  and adding the integration(s) in the Integration tab. [!DNL Target][!DNL Adobe Admin Console]Prior to the September release, all integrations operated using Approver access, regardless of choice made from the Product Role drop-down list. You can now choose the desired role.

>[!NOTE]
>
>If this action is not performed, after the  September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. [!DNL Target]There is no adverse reaction to setting up integrations in advance. The sooner you make this change, the better. Depending on the number of workspaces in your organization, this process takes only a few clicks to add an existing integration into workspaces with the desired role.

**To grant Adobe I/O integrations access to workspaces and to assign roles:**

1. Open the Adobe Admin Console.**[](https://adminconsole.adobe.com)**

1. 按一下「 **[!UICONTROL 產品]** 」標籤，然後選取所要產品的名稱。

   ![Choose product in Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 選擇所要的工作區（產品設定檔）。

   ![Select the product profile](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Integrations tab](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. （條件性）若要新增整合，請按一下「新 **[!UICONTROL 增整合」]**，選取所需的整合，然後按一下「 **[!UICONTROL 儲存」]**。

1. From the Product Role drop-down list, select the desired role for that workspace:****

   * [!UICONTROL 核准者]
   * [!UICONTROL 編輯器]
   * [!UICONTROL 觀察者]
   ![選擇產品描述檔角色](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)

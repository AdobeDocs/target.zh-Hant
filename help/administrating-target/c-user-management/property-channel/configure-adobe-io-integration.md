---
description: 關於授予Adobe I/整合存取權以存取具有所需角色之所有工作區的資訊。
keywords: 整合；角色；使用者權限；admin Console
seo-description: 有關授予現有Adobe I/整合的資訊，請使用Adobe Target中所需角色的所有工作區
seo-title: 授予Adobe I/O整合存取工作區並指派Adobe Target中的角色
solution: Target
subtopic: 快速入門
title: 授予Adobe I/O整合存取工作區並指派角色
translation-type: tm+mt
source-git-commit: e1174aacc5610878c8671e88fbd20d51fedffe6c

---


# ![PREMIUM](/help/assets/premium.png) 授予Adobe I/整合存取工作區的權限並指派角色

[!UICONTROL 企業權限] 允許 [!DNL Target] 客戶使用單一組織，但將其分為不同團隊或工作流程的工作區。

>[!NOTE]
>
>屬性和權限功能屬於 [Target Premium](/help/c-intro/intro.md#premium) 解決方案的一部分。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。

[!UICONTROL 企業權限] 功能可協助您有效擴展團隊內部的最佳化程式。Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier in 2019. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, [!DNL Target] [!UICONTROL Enterprise Permissions] will provide customers with the following access controls:

* 您可以選擇可套用整合的工作區
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

此更新支援下列使用案例：

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* 授予Adobe I/O存取權，以適當的角色選取工作區，讓中央團隊只在少數工作區中進行API驅動的變更。
* 當團隊準備好要探索API並據以選擇角色時，讓每個團隊都擁有自己的工作區，以便自行整合。
* 混合並比對上述任何藍本。

**需要的動作**：目前針對所有工作區運用API for資源(活動、對象、選件和報告)的客戶，需要將現有的Adobe I/整合存取權授與所有工作區，以依其使用案例使用所需角色。You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of choice made from the [!UICONTROL Product Role] drop-down list. 您現在可以選擇所要的角色。

This action should be performed during the month of **August 2019** to not face any disruption on your end. If this action is not performed, after the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. 預先設定整合並無負面反應。您越早越好。視組織中的工作區數目而定，需要少許時間來設定此設定。此程序只需按幾下滑鼠，即可將現有的整合新增至具有所需角色的工作區。

**若要授予Adobe I/整合存取工作區及指派角色的權限：**

1. Open the **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Click the **[!UICONTROL Products]** tab, then select the name of the desired product.

   ![在Adobe Admin Console中選擇產品](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 選取所要的工作區(產品描述檔)。

   ![選取產品描述檔](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![整合標籤](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Conditional) To add a new integration, click **[!UICONTROL Add Integration]**, select the desired integration, then click **[!UICONTROL Save]**.

1. From the **[!UICONTROL Product Role]** drop-down list, select the desired role for that workspace:

   * [!UICONTROL 核准者]
   * [!UICONTROL 編輯器]
   * [!UICONTROL 觀察者]
   ![選擇產品描述檔角色](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)

---
keywords: 整合;角色;使用者權限;admin console
description: 瞭解如何以Adobe Target中所需的角色授與現有Adobe I/O整合功能對所有工作區的存取權。
title: 如何授予Adobe I/O對工作區的存取權並指派角色？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
source-git-commit: fa11f93058b69e5e59e0ee20c65cffa4a1344ca0
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 87%

---

# 授予 Adobe I/O 整合功能對工作區的存取權並指派角色

[!UICONTROL 企業權限]可讓 [!DNL Target] 客戶使用單一組織，但將其分割為多個工作區以供其不同團隊或工作流程使用。

>[!NOTE]
>
>屬性和權限功能屬於 [Target Premium](/help/main/c-intro/intro.md#premium) 解決方案的一部分。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。

[!UICONTROL 企業權限]功能可促進跨團隊最佳化程式的有效資源調度。雖然 [!DNL Target] UI 提供了此功能，不過 Admin API 在 2019 年初之前一直都缺乏對應的支援。在 [!DNL Target] 2019 年 2 月版本中，Adobe 已更新 Admin API，讓您能夠使用整合帳戶來存取組織中建立的所有工作區。因此，雖然之前 Admin API 限制為僅限預設工作區，但 2019 年 2 月更新已授予可使用[!UICONTROL 核准者]存取權來存取所有工作區。

使用 [!DNL Target] 2019年9月發行版本， [!DNL Target] [!UICONTROL 企業許可權] 為客戶提供下列存取控制：

* 您可以選擇要將整合套用到哪個工作區
* 您可以將角色套用至 Adobe I/O 整合功能: [!UICONTROL 核准者]、[!UICONTROL 編輯者]或[!UICONTROL 觀察者]。

此更新支援下列使用案例:

* 授予 Adobe I/O 整合功能可使用[!UICONTROL 觀察者]角色存取所有工作區的權限，以用於報表用途，但沒有建立或編輯資源的權限。
* 授予 Adobe I/O 整合功能可使用適當角色選取工作區的存取權，以允許中央團隊只在少數幾個工作區中進行 API 導向的變更。
* 每當團隊準備好探索 API 並據此選擇角色時，允許擁有其工作區的每個團隊擁有各自的整合。
* 混合並比對任何上述案例。

**需要採取動作**: 如果客戶目前運用 API 在所有工作區的資源 (活動、受眾、選件和報表) 上執行 CRUD 作業，則須授予其現有 Adobe I/O 整合功能可根據其使用案例使用所需角色存取所有工作區的權限。若要這麼做，請選取 [!DNL Adobe Admin Console] 中的每個 [!DNL Target] [!UICONTROL 產品設定檔]，然後在[!UICONTROL 整合功能]索引標籤中新增整合功能。在 9 月版本之，無論是否從[!UICONTROL 產品角色]下拉式清單進行選擇，所有整合功能都是使用[!UICONTROL 核准者]存取權來執行作業。您現在可以選擇所需角色。

>[!NOTE]
>
>如果未執行此動作，在 [!DNL Target] 2019 年 9 月版之後，存取控制將啟用，而如果這是您目前設定的方式，您將只能以觀察者角色存取預設工作區。事先設定整合功能並不會有任何不利的反應。此變更越早進行越好。根據您組織內的工作區數量，此程式只需按幾下，即可使用所需角色將現有整合新增至工作區。

**如何授予 Adobe I/O 整合功能對工作區的存取權並指派角色:**

1. 開啟 **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. 按一下&#x200B;**[!UICONTROL 產品]**&#x200B;索引標籤，然後選取所需的產品名稱。

   ![在 Adobe Admin Console 中選擇產品](/help/main/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 選取所需的工作區 (產品設定檔)。

   ![選取產品設定檔](/help/main/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. 按一下&#x200B;**[!UICONTROL 整合功能]**&#x200B;索引標籤。

   ![整合功能索引標籤](/help/main/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (視條件而定) 若要新增整合功能，請按一下&#x200B;**[!UICONTROL 新增整合功能]**，選取所需的整合功能，然後按一下&#x200B;**[!UICONTROL 儲存]**。

1. 從&#x200B;**[!UICONTROL 產品角色]**&#x200B;下拉式清單中，選取該工作區的所需角色。

   | 角色 | 說明 |
   |--- |--- |
   | 核准者 | 可以建立、編輯和啟動或停止活動。 |
   | 編輯者 | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
   | 觀察者 | 可以檢視活動，但無法建立或編輯活動。 |
   | 發佈者 | 類似於觀察者角色 (可以查看活動，但不能建立或編輯活動)。 不過，發佈者角色具有啟用活動的額外權限。 |

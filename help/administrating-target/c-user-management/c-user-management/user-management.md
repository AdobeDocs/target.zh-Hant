---
keywords: add user;manage user;user permissions
description: 將使用者新增至Adobe Target，並在Adobe Admin Console中管理其權限。
title: 使用者
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 46%

---


# 使用者{#users}

在[!DNL Adobe Admin Console]中新增使用者並管理其權限。

>[!NOTE]
>
>[!UICONTROL 屬性和權限功能屬於 ] Premium 解決方案的一部分。[!DNL Target]在沒有 [!DNL Target] Premium 授權的 [!DNL Target] Standard 中無法使用。
>您可以按一下[!DNL Target] UI頂端的[!UICONTROL 管理]連結，來判斷您的組織是否擁有Standard或Premium授權。
>
>* **[!DNL Target]標準客戶**:如果您看到  Userstab([!UICONTROL 管理>使用者])(而非屬 **** 性表)，您的組織會擁有 [!DNL Target] Standard授權。[!DNL Target] Standard 客戶應該遵循本文的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。
   >
   >
* **[!DNL Target]Premium客戶**:如果您看到  Userstab和  Propertiesstab([!UICONTROL 管理>屬性])，您的組織會擁有 [!DNL Target] Premium授權。[!DNL Target] Premium 客戶應該遵循[企業使用者權限](/help/administrating-target/c-user-management/property-channel/property-channel.md)和[設定企業權限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)中的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。
>
>
如需如何管理使用者和權限的詳細資訊，請參閱&#x200B;*企業與團隊使用指南*&#x200B;中的[管理產品和設定檔](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html)。

當您開始使用 [!DNL Adobe Target] 時，您可以找到 [!DNL Adobe Experience Cloud] 帳戶中預先填入的 ID (結尾是 Adobe.com)。這些ID適用於[!DNL Adobe]團隊的成員，以便他們能夠協助您建立新帳戶，並在您需要協助時使用[!DNL Adobe Target]。 若要取得協助，請像平常一樣聯絡 Adobe 團隊。

在使用者使用[!DNL Adobe Experience Cloud]帳戶登入，然後登入[!DNL Target Standard/Premium]之前，您不會在[!UICONTROL 使用者]頁面上看到新使用者。

依預設，所有 [!DNL Target] 使用者一開始都具有觀察者權限。

管理員用戶在[!UICONTROL Users]清單中標識。 如果您需要變更存取層級，請連絡其中一個系統管理員使用者。

## 從Target檢視使用者資訊

您可以在Target環境中檢視目前使用者的清單，包括其每個工作區的角色，以及直接從Target內部傳送的電子郵件地址。

要查看「用戶」頁，請按一下「管理」>「**** > **[!UICONTROL 用戶」。]**

![Target中的使用者清單](/help/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>若要管理現有使用者或新增使用者，您必須使用[!UICONTROL Adobe Admin Console]，如下所述。

## 存取 Adobe Admin Console {#access}

若為 Adobe Admin Console 中執行的工作，請遵循下列步驟來存取控制台:

1. 在[!DNL Target]中，按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 用戶]** > **[!UICONTROL 用戶管理]**。

   或

   前往[https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)，然後使用您的Adobe ID登入（如果您尚未登入）。

1. (條件式) 如果您可以存取一個以上組織的 [!DNL Admin Console for Enterprise]，請按一下右上角或上方導覽列中的使用者頭像，然後選取需要的組織。

## 新增使用者{#add-users}

所有使用者管理都必須在 [!DNL Adobe Admin Console for Enterprise] 中執行。不過，[!DNL Target] 中的所有現有使用者將會從 [!DNL Target] 移轉至 [!DNL Admin Console for Enterprise]。

1. [在「管理控制台](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)」中，按一 **[!UICONTROL 下「使]** 用者>使 **** 用者」以建立新使用者或編輯現有使用者。
1. 遵循&#x200B;*《企業使用者指南》*&#x200B;的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示。

## 建立用戶組{#user-groups}

您可以建立使用者群組，例如開發人員、分析人員、行銷人員、行政人員等，然後跨多個 Adobe 產品和工作區指派權限。跨不同的 Adobe 產品為新團隊成員指派所有適當的權限，就如同將它們新增至特定使用者群組一樣簡單。

1. [在「管理控制台](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)」中，按一 **[!UICONTROL 下「使用者]** > **[!UICONTROL 使用者]** 群組」以建立新的使用者群組或編輯現有群組。
1. 遵循&#x200B;*《企業使用者指南》*&#x200B;的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示。

## 指定角色和權限{#roles-permissions}

只有系統管理員可以在 [!DNL Target] 中設定使用者角色。例如，標準審批者使用者若沒有[!DNL Experience Cloud]管理權限，就無法將觀察員變更為審批者。

系統管理員使用者必須將使用者新增至系統。系統不會自動新增使用者。他們會收到[!DNL Experience Cloud]的電子郵件邀請，而且必須先確認其電子郵件地址，才能註冊其帳戶。

1. [](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)在 Admin Console 中，按一下&#x200B;**[!UICONTROL 「產品」]**，然後選取所需產品的名稱。

   ![產品索引標籤](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 按一下所要的工作區（例如「預設工作區」）。

   ![預設工作區](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   [!UICONTROL 使用者]索引標籤會顯示該工作區中的所有使用者。

   ![設定使用者](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. 使用[!UICONTROL 「產品角色」]欄中每個使用者的下拉式清單，選取需要的權限角色 (核准者、編輯者或觀察者)。

   ![產品角色下拉式清單](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 角色 | 說明 |
   |--- |--- |
   | 核准者 | 可以建立、編輯和啟動或停止活動。 |
   | 編輯器 | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
   | 觀察者 | 可以檢視活動，但無法建立或編輯活動。 |
   | 發行者 | 類似於「觀察者」角色（可以查看活動，但無法建立或編輯活動）。 不過，「發佈者」角色具有啟動活動的額外權限。 |

如需詳細資訊，請參閱&#x200B;*《企業使用者指南》*&#x200B;中的[在 Admin Console 中管理產品權限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 訓練影片：如何配置目標工作區![教程徽章](/help/assets/tutorial.png)

學習目標:

* 從 Adobe Target 介面存取 Adobe Admin Console (三個方式)
* 在 Adobe Admin Console 中設定工作區
   * 新增使用者至工作區
   * 新增屬性至工作區
* 瞭解預設工作區

>[!NOTE]
>
>[!DNL Target] [!UICONTROL Administration]功能表UI（先前稱為[!UICONTROL Setup]）已重新設計，以提供改善的效能、縮短發布新功能時所需的維護時間，並改善整個產品的使用者體驗。 以下視頻中的資訊通常正確；不過，選項可能位於稍微不同的位置。 更新的影片將很快發佈。

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

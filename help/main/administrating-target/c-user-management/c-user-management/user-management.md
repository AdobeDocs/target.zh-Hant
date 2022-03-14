---
keywords: 新增使用者; 管理使用者; 使用者權限
description: 瞭解如何在Adobe Target使用Adobe Admin Console管理用戶及其權限。
title: 如何添加用戶和管理權限？
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 47%

---

# 使用者

在中添加用戶並管理其權限 [!DNL Adobe Admin Console]。

>[!NOTE]
>
>[!UICONTROL 屬性和權限功能屬於 ] Premium 解決方案的一部分。[!DNL Target]在沒有 [!DNL Target] Premium 授權的 [!DNL Target] Standard 中無法使用。
>通過按一下 [!UICONTROL 管理] 在 [!DNL Target] UI。
>
>* **[!DNL Target]標準客戶**:如果你看到 [!UICONTROL 用戶] 頁籤[!UICONTROL 管理>用戶])(而不是 **[!UICONTROL 屬性]** 頁籤)，您的組織具有 [!DNL Target] 標准許可證。 [!DNL Target] Standard 客戶應該遵循本文的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。
>
>* **[!DNL Target]高級客戶**:如果你看到 [!UICONTROL 用戶] 頁籤 [!UICONTROL 屬性] 頁籤[!UICONTROL 管理>屬性])，您的組織 [!DNL Target] 高級許可證。 [!DNL Target] Premium 客戶應該遵循[企業使用者權限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)和[設定企業權限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)中的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。
>
>有關如何管理用戶和權限的詳細資訊，請參見 [管理產品和配置檔案](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) 的 *企業和團隊使用手冊*。

當您開始使用 [!DNL Adobe Target] 時，您可以找到 [!DNL Adobe Experience Cloud] 帳戶中預先填入的 ID (結尾是 Adobe.com)。這些ID用於 [!DNL Adobe] 團隊，以便他們能夠幫助您完成新帳戶和使用 [!DNL Adobe Target]，是否需要幫助。 若要取得協助，請像平常一樣聯絡 Adobe 團隊。

您將看不到列在 [!UICONTROL 用戶] 頁面，直到用戶使用 [!DNL Adobe Experience Cloud] 帳戶，然後登錄 [!DNL Target Standard/Premium]。

依預設，所有 [!DNL Target] 使用者一開始都具有觀察者權限。

管理員用戶在 [!UICONTROL 用戶] 清單框。 如果需要更改訪問級別，請與系統管理員用戶之一聯繫。

## 查看目標內的用戶資訊

您可以查看目標環境中當前用戶的清單，包括其每個工作區的角色以及直接從目標內部發送的電子郵件地址。

要查看「用戶」頁，請按一下 **[!UICONTROL 管理]** > **[!UICONTROL 用戶]**。

![目標內的用戶清單](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>要管理現有用戶或添加新用戶，必須使用 [!UICONTROL Adobe Admin Console]，如下所述。

## 存取 Adobe Admin Console {#access}

若為 Adobe Admin Console 中執行的工作，請遵循下列步驟來存取控制台:

1. 從 [!DNL Target]按一下 **[!UICONTROL 管理]** > **[!UICONTROL 用戶]** > **[!UICONTROL 用戶管理]**。

   或

   轉到 [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)，如果尚未登錄，則使用Adobe ID登錄。

1. (條件式) 如果您可以存取一個以上組織的 [!DNL Admin Console for Enterprise]，請按一下右上角或上方導覽列中的使用者頭像，然後選取需要的組織。

## 添加用戶 {#add-users}

所有使用者管理都必須在 [!DNL Adobe Admin Console for Enterprise] 中執行。不過，[!DNL Target] 中的所有現有使用者將會從 [!DNL Target] 移轉至 [!DNL Admin Console for Enterprise]。

1. [在Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)按一下 **[!UICONTROL 用戶]** > **[!UICONTROL 用戶]** 建立新用戶或編輯現有用戶。
1. 遵循&#x200B;*《企業使用者指南》*&#x200B;的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示。

## 建立用戶組 {#user-groups}

您可以建立使用者群組，例如開發人員、分析人員、行銷人員、行政人員等，然後跨多個 Adobe 產品和工作區指派權限。跨不同的 Adobe 產品為新團隊成員指派所有適當的權限，就如同將它們新增至特定使用者群組一樣簡單。

1. [在Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)按一下 **[!UICONTROL 用戶]** > **[!UICONTROL 用戶組]** 建立新用戶組或編輯現有組。
1. 遵循&#x200B;*《企業使用者指南》*&#x200B;的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示。

## 指定角色和權限 {#roles-permissions}

只有系統管理員可以在 [!DNL Target] 中設定使用者角色。例如，標準審批者用戶不能將觀察者更改為審批者，而且 [!DNL Experience Cloud] 管理員權限。

系統管理員使用者必須將使用者新增至系統。系統不會自動新增使用者。他們會收到來自 [!DNL Experience Cloud] 必須在註冊其帳戶之前確認其電子郵件地址。

1. [](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)在 Admin Console 中，按一下&#x200B;**[!UICONTROL 「產品」]**，然後選取所需產品的名稱。

   ![產品索引標籤](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 按一下所需的工作區(例如，「預設工作區」(Default Workspace))。

   ![預設工作區](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   [!UICONTROL 使用者]索引標籤會顯示該工作區中的所有使用者。

   ![設定使用者](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. 使用[!UICONTROL 「產品角色」]欄中每個使用者的下拉式清單，選取需要的權限角色 (核准者、編輯者或觀察者)。

   ![產品角色下拉清單](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 角色 | 說明 |
   |--- |--- |
   | 核准者 | 可以建立、編輯和啟動或停止活動。 |
   | 編輯器 | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
   | 觀察者 | 可以檢視活動，但無法建立或編輯活動。 |
   | 發行者 | 與「觀察者」角色類似（可以查看活動，但無法建立或編輯它們）。 但是，發佈者角色具有激活活動的附加權限。 |

如需詳細資訊，請參閱&#x200B;*《企業使用者指南》*&#x200B;中的[在 Admin Console 中管理產品權限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 培訓視頻：如何配置Adobe Target工作區 ![教程徽章](/help/main/assets/tutorial.png)

學習目標:

* 從 Adobe Target 介面存取 Adobe Admin Console (三個方式)
* 在 Adobe Admin Console 中設定工作區
   * 新增使用者至工作區
   * 新增屬性至工作區
* 瞭解預設工作區

>[!NOTE]
>
>的 [!DNL Target] [!UICONTROL 管理] 菜單UI（以前） [!UICONTROL 設定])已重新設計，以提供改進的效能，減少發佈新功能時所需的維護時間，並改善整個產品的用戶體驗。 以下視頻中的資訊一般是正確的；但是，選項可能位於稍有不同的位置。 更新的視頻將很快發佈。

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

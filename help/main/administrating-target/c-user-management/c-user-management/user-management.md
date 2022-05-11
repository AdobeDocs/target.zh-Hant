---
keywords: 新增使用者; 管理使用者; 使用者權限
description: 了解如何使用 Adobe Admin Console 來管理使用者，並直接在 Adobe Target 中管理使用者權限。
title: 該如何新增使用者及管理權限？
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: ht
source-wordcount: '911'
ht-degree: 100%

---

# 使用者

在 [!DNL Adobe Admin Console] 中新增使用者及管理使用者權限。

>[!NOTE]
>
>[!UICONTROL 屬性]和[!UICONTROL 權限]功能當作 [!DNL Target] Premium 解決方案的一部分來提供。 如果沒有 [!DNL Target] Premium 授權，就無法在 [!DNL Target] Standard 中使用它們。 
>您可以分辨貴組織是擁有 Standard 還是 Premium 授權，方法是按一下 [!DNL Target] UI 上方的[!UICONTROL 管理]連結。
>
>* **[!DNL Target]Standard 客戶**：如果您看到[!UICONTROL 使用者]索引標籤 ([!UICONTROL 管理 > 使用者]) (而不是&#x200B;**[!UICONTROL 屬性]**&#x200B;索引標籤)，就表示貴組織擁有 [!DNL Target] Standard 授權。 [!DNL Target] Standard 客戶應該依照本文的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。
>
>* **[!DNL Target]Premium 客戶**：如果您看到[!UICONTROL 使用者]索引標籤和[!UICONTROL 屬性]索引標籤 ([!UICONTROL 管理 > 屬性])，就表示貴組織擁有 [!DNL Target] Premium 授權。 [!DNL Target] Premium 客戶應該依照[企業使用者權限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)和[設定企業權限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)中的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。
>
>如需有關如何管理使用者和權限的詳細資訊，請參閱&#x200B;*企業和團隊使用手冊*&#x200B;中的[管理產品和描述檔](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html)。

當您開始使用 [!DNL Adobe Target] 時，您可以找到 [!DNL Adobe Experience Cloud] 帳戶中預先填入的 ID (結尾是 Adobe.com)。 若您需要協助，這些 ID 可供 [!DNL Adobe] 團隊成員使用，好讓他們可以協助處理您的新帳戶及協助您使用 [!DNL Adobe Target]。 若要取得協助，請像平常一樣聯絡 Adobe 團隊。

在新使用者使用其 [!DNL Adobe Experience Cloud] 帳戶登入，然後登入 [!DNL Target Standard/Premium] 之後，您才會看到該使用者列在[!UICONTROL 使用者]頁面上。

根據預設，所有 [!DNL Target] 使用者一開始都具有觀察者權限。

在[!UICONTROL 使用者]清單中可識別管理員使用者。 如果您需要變更存取等級，請聯絡其中一位系統管理員使用者。

## 從 Target 檢視使用者資訊

您可以直接在 Target 中檢視 Target 環境中的目前使用者清單，包括他們在每個工作區的角色以及電子郵件地址。

若要檢視「使用者」頁面，請按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 使用者]**。

![從 Target 檢視使用者清單](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>若要管理現有使用者或新增使用者，您必須使用 [!UICONTROL Adobe Admin Console]，如下所述。

## 存取 Adobe Admin Console {#access}

若要在 Adobe Admin Console 中執行工作，請遵循下列步驟來存取它：

1. 在 [!DNL Target] 中按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 使用者]** > **[!UICONTROL 使用者管理]**。

   或

   移至 [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)，然後使用 Adobe ID 登入 (如果尚未登入)。

1. (有條件性) 如果您可以存取一個以上組織的 [!DNL Admin Console for Enterprise]，請按一下右上角或上方導覽列中的使用者頭像，然後選取所要的組織。

## 新增使用者 {#add-users}

所有使用者管理都必須在 [!DNL Adobe Admin Console for Enterprise] 中執行。不過，[!DNL Target] 中的所有現有使用者將會從 [!DNL Target] 移轉至 [!DNL Admin Console for Enterprise]。

1. [在 Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) 中，按一下&#x200B;**[!UICONTROL 使用者]** > **[!UICONTROL 使用者]**，以建立新使用者或編輯現有的使用者。
1. 依照&#x200B;*企業版使用手冊*&#x200B;中的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示進行。

## 建立使用者群組 {#user-groups}

您可以建立使用者群組，例如開發人員、分析人員、行銷人員、行政人員等，然後跨多個 Adobe 產品和工作區指派權限。跨不同的 Adobe 產品為新團隊成員指派所有適當的權限，就如同將它們新增至特定使用者群組一樣簡單。

1. [在 Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) 中，按一下&#x200B;**[!UICONTROL 使用者]** > **[!UICONTROL 使用者群組]**，以建立新使用者群組或編輯現有的群組。
1. 依照&#x200B;*企業版使用手冊*&#x200B;中的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示進行。

## 指定角色和權限 {#roles-permissions}

只有系統管理員可以在 [!DNL Target] 中設定使用者角色。 例如，Standard 核准者使用者也必須擁有 [!DNL Experience Cloud] 管理員權限，才能將觀察者變更為核准者。

系統管理員使用者必須將使用者新增至系統。系統不會自動新增使用者。使用者要收到來自 [!DNL Experience Cloud] 的電子郵件邀請，而且在註冊其帳戶之前必須先確認電子郵件位址。

1. [在 Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) 中，按一下&#x200B;**[!UICONTROL 產品]**，然後選取所需的產品名稱。

   ![「產品」索引標籤](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 按一下所需的工作區 (例如預設工作區)。

   ![預設工作區](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   [!UICONTROL 使用者]索引標籤會顯示該工作區中的所有使用者。

   ![設定使用者](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. 使用[!UICONTROL 產品角色]欄中每個使用者的下拉式清單，選取所需的權限角色 (核准者、編輯者或觀察者)。

   ![「產品角色」下拉式清單](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 角色 | 說明 |
   |--- |--- |
   | 核准者 | 可以建立、編輯和啟動或停止活動。 |
   | 編輯者 | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
   | 觀察者 | 可以檢視活動，但無法建立或編輯活動。 |
   | 發佈者 | 類似於觀察者角色 (可以查看活動，但不能建立或編輯活動)。 不過，發佈者角色具有啟用活動的額外權限。 |

如需詳細資訊，請參閱&#x200B;*企業版使用手冊*&#x200B;中的[在 Admin Console 中管理產品權限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 培訓影片：如何設定 Adobe Target 工作區 ![教學課程徽章](/help/main/assets/tutorial.png)

學習目標:

* 從 Adobe Target 介面存取 Adobe Admin Console (三個方式)
* 在 Adobe Admin Console 中設定工作區
   * 新增使用者至工作區
   * 新增屬性至工作區
* 瞭解預設工作區

>[!NOTE]
>
>[!DNL Target] [!UICONTROL 管理]選單 UI (之前稱為[!UICONTROL 設定]) 已經過重新設計，可提供改良的效能、縮短發佈新功能所需的維護時間，並改善整個產品的使用者體驗。 以下影片中的資訊通常是正確的，但是選項的位置可能略有不同。 我們很快就會發佈更新的影片。

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

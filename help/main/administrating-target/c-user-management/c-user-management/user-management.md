---
keywords: 新增使用者; 管理使用者; 使用者權限
description: 了解如何使用  [!DNL Adobe Admin Console]  來管理  [!DNL Adobe Target Standard] 中的使用者及其權限和權利。
title: 如何為  [!DNL Target Standard]  帳戶新增使用者並管理權限？
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: 8560fa828fac91170fd295c9ef9a9b0e6ce1651c
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 63%

---

# 使用者

在 [!DNL Adobe Admin Console] 中為 [!DNL Target Standard] 帳戶新增使用者並管理其權限。

>[!NOTE]
>
>[!UICONTROL Properties]和[!UICONTROL Permissions]功能屬於[!DNL Target Premium]解決方案的一部分。 如果沒有 [!DNL Target] Premium 授權，就無法在 [!DNL Target] Standard 中使用它們。 
>
>您可以區分您的組織是否有[!UICONTROL Standard]或[!UICONTROL Premium]授權，方法是按一下[!DNL Target] UI上方的[!UICONTROL Administration]連結。
>
>* **[!DNL Target][!UICONTROL Standard]客戶**：如果您看見[!UICONTROL Users]標籤([!UICONTROL Administration > Users]) （而非&#x200B;**[!UICONTROL Properties]**&#x200B;標籤），則您的組織有[!DNL Target] [!UICONTROL Standard]授權。 [!DNL Target] [!UICONTROL Standard]客戶應該依照本文的指示，在[!DNL Adobe Admin Console]中新增使用者並指派許可權。
>
>* **[!DNL Target]Premium客戶**：如果您看到[!UICONTROL Users]標籤和[!UICONTROL Properties]標籤([!UICONTROL Administration > Properties])，表示貴組織擁有[!DNL Target] Premium授權。 [!DNL Target] Premium 客戶應該依照[企業使用者權限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)和[設定企業權限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)中的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。
>
>如需有關如何管理使用者和權限的詳細資訊，請參閱&#x200B;*企業和團隊使用手冊*&#x200B;中的[管理產品和描述檔](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html)。

當您開始使用 [!DNL Adobe Target] 時，您可以找到 [!DNL Adobe Experience Cloud] 帳戶中預先填入的 ID (結尾是 Adobe.com)。 若您需要協助，這些 ID 可供 [!DNL Adobe] 團隊成員使用，好讓他們可以協助處理您的新帳戶及協助您使用 [!DNL Adobe Target]。 若要取得協助，請像平常一樣聯絡 Adobe 團隊。

在新使用者使用其[!DNL Adobe Experience Cloud]帳戶登入，然後登入[!DNL Target]之前，您不會在[!UICONTROL Users]頁面上看見新使用者列出。

依預設，所有[!DNL Target]使用者一開始皆具有[!UICONTROL Observer]許可權。

已在[!UICONTROL Users]清單中識別管理員使用者。 如果您需要變更存取等級，請聯絡其中一位系統管理員使用者。

## 從 [!DNL Target] 檢視使用者資訊

您可以在 [!DNL Target] UI 中查看目前使用者的清單，包括他們在每個工作區和電子郵件地址中的角色。

若要檢視[!UICONTROL Users]頁面，請按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Users]**。

![從 Target 檢視使用者清單](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>若要管理現有使用者或新增使用者，您必須使用[!UICONTROL Adobe Admin Console]，如下所述。

## 存取 [!DNL Adobe Admin Console] {#access}

對於 [!DNL Adobe Admin Console] 中執行的任務，請依照下列步驟存取主控台：

1. 從[!DNL Target]中，按一下「**[!UICONTROL Administration]** > **[!UICONTROL Users]** > **[!UICONTROL Users Management]**」。

   或

   移至 [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)，然後使用 Adobe ID 登入 (如果尚未登入)。

1. (有條件性) 如果您可以存取一個以上組織的 [!DNL Admin Console for Enterprise]，請按一下右上角或上方導覽列中的使用者頭像，然後選取所要的組織。

## 新增使用者 {#add-users}

所有使用者管理都必須在 [!DNL Adobe Admin Console for Enterprise] 中執行。不過，[!DNL Target] 中的所有現有使用者將會從 [!DNL Target] 移轉至 [!DNL Admin Console for Enterprise]。

1. [在Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)中，按一下&#x200B;**[!UICONTROL Users]** > **[!UICONTROL Users]**&#x200B;以建立新使用者或編輯現有的使用者。
1. 依照&#x200B;*企業版使用手冊*&#x200B;中的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示進行。

## 建立使用者群組 {#user-groups}

您可以建立使用者群組，例如開發人員、分析人員、行銷人員、行政人員等，然後跨多個 [!DNL Adobe] 產品和工作區指派權限。跨不同的 [!DNL Adobe] 產品為新團隊成員指派所有適當的權限，就如同將它們新增至特定使用者群組一樣簡單。

1. [在Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)中，按一下&#x200B;**[!UICONTROL Users]** > **[!UICONTROL User Groups]**&#x200B;以建立新使用者群組或編輯現有的群組。
1. 依照&#x200B;*企業版使用手冊*&#x200B;中的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示進行。

## 指定角色和權限 {#roles-permissions}

只有系統管理員可以在 [!DNL Target] 中設定使用者角色。 例如，[!UICONTROL Standard]核准者使用者也必須擁有[!DNL Experience Cloud]管理員許可權，才能將觀察者變更為核准者。

系統管理員使用者必須將使用者新增至系統。系統不會自動新增使用者。使用者要收到來自 [!DNL Experience Cloud] 的電子郵件邀請，而且在註冊其帳戶之前必須先確認電子郵件位址。

>[!NOTE]
>
>若要在[!DNL Target]中檢視活動，必須將使用者直接指派給至少具有[!UICONTROL Observer]角色的工作區。 僅透過使用者群組進行指派是不夠的。 通常建議授予使用者對預設工作區的存取權。

1. [在Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)中，按一下&#x200B;**[!UICONTROL Products]**，然後選取所要產品的名稱。

   ![「產品」索引標籤](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 按一下所需的工作區 (例如預設工作區)。

   ![預設工作區](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   [!UICONTROL Users]索引標籤會顯示該工作區中的所有使用者。

   ![設定使用者](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. 使用[!UICONTROL Product Role]欄中每個使用者的下拉式清單，選取所需的許可權角色（[!UICONTROL Approver]、[!UICONTROL Editor]、[!UICONTROL Observer]或[!UICONTROL Publisher]）。

   ![「產品角色」下拉式清單](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 角色 | 說明 |
   |--- |--- |
   | [!UICONTROL Approver] | 可以建立、編輯和啟動或停止活動。 |
   | [!UICONTROL Editor] | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
   | [!UICONTROL Observer] | 可以檢視活動，但無法建立或編輯活動。 |
   | [!UICONTROL Publisher] | 類似[!UICONTROL Observer]角色（可以檢視活動，但不能建立或編輯活動）。 但是，[!UICONTROL Publisher]角色具有啟用活動的額外許可權。 |

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
>[!DNL Target] [!UICONTROL Administration]功能表UI （先前稱為[!UICONTROL Setup]）已經過重新設計，可提供改良的效能、縮短發布新功能所需的維護時間，並改善整個產品的使用者體驗。 以下影片中的資訊通常是正確的，但是選項的位置可能略有不同。 我們很快就會發佈更新的影片。

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

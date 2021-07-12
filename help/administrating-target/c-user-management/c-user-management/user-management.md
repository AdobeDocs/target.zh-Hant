---
keywords: 新增使用者; 管理使用者; 使用者權限
description: 了解如何使用Adobe Admin Console直接在Adobe Target中管理使用者及其權限。
title: 如何新增使用者和管理權限？
feature: 管理與設定
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 47%

---

# 使用者

在[!DNL Adobe Admin Console]中新增使用者並管理其權限。

>[!NOTE]
>
>[!UICONTROL 屬性和權限功能屬於 ] Premium 解決方案的一部分。[!DNL Target]在沒有 [!DNL Target] Premium 授權的 [!DNL Target] Standard 中無法使用。
>您可以區分您的組織具有的Standard或Premium授權，方法是按一下[!DNL Target] UI頂端的[!UICONTROL Administration]連結。
>
>* **[!DNL Target]標準客戶**:如果您看到  Userstab([!UICONTROL 管理>使用者])(而非屬性 **** 資料表)，則您的組織擁有標準 [!DNL Target] 授權。[!DNL Target] Standard 客戶應該遵循本文的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。
   >
   >
* **[!DNL Target]Premium客戶**:如果您看到  Userstab和Propertiesstab(  管理>屬性[!UICONTROL )，則您的組] [!DNL Target] 織具有Premium授權。[!DNL Target] Premium 客戶應該遵循[企業使用者權限](/help/administrating-target/c-user-management/property-channel/property-channel.md)和[設定企業權限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)中的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。
>
>
如需如何管理使用者和權限的詳細資訊，請參閱&#x200B;*企業與團隊使用手冊*&#x200B;中的[管理產品和設定檔](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html)。

當您開始使用 [!DNL Adobe Target] 時，您可以找到 [!DNL Adobe Experience Cloud] 帳戶中預先填入的 ID (結尾是 Adobe.com)。若您需要協助，這些ID可供[!DNL Adobe]團隊的成員使用，讓他們可協助您處理新帳戶及協助您使用[!DNL Adobe Target]。 若要取得協助，請像平常一樣聯絡 Adobe 團隊。

在新使用者使用其[!DNL Adobe Experience Cloud]帳戶登入，然後登入[!DNL Target Standard/Premium]之前，您不會在[!UICONTROL 使用者]頁面上看見新使用者列出。

依預設，所有 [!DNL Target] 使用者一開始都具有觀察者權限。

在[!UICONTROL 使用者]清單中識別管理員使用者。 如果您需要變更存取層級，請連絡其中一位系統管理員使用者。

## 從Target內檢視使用者資訊

您可以在Target環境中檢視目前使用者的清單，包括他們在每個工作區中的角色，以及直接從Target內檢視電子郵件地址。

要查看「用戶」頁，請按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Users]**。

![Target內的使用者清單](/help/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>若要管理現有使用者或新增使用者，您必須使用[!UICONTROL Adobe Admin Console]，如下所述。

## 存取 Adobe Admin Console {#access}

若為 Adobe Admin Console 中執行的工作，請遵循下列步驟來存取控制台:

1. 從[!DNL Target]內，按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Users]** > **[!UICONTROL Users Management]**。

   或

   前往[https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)，然後使用Adobe ID（如果尚未登入）登入。

1. (條件式) 如果您可以存取一個以上組織的 [!DNL Admin Console for Enterprise]，請按一下右上角或上方導覽列中的使用者頭像，然後選取需要的組織。

## 新增使用者 {#add-users}

所有使用者管理都必須在 [!DNL Adobe Admin Console for Enterprise] 中執行。不過，[!DNL Target] 中的所有現有使用者將會從 [!DNL Target] 移轉至 [!DNL Admin Console for Enterprise]。

1. [在Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)中，按一下「 **[!UICONTROL 使用者]**  >  **** 使用者」以建立新使用者或編輯現有使用者。
1. 遵循&#x200B;*《企業使用者指南》*&#x200B;的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示。

## 建立使用者群組 {#user-groups}

您可以建立使用者群組，例如開發人員、分析人員、行銷人員、行政人員等，然後跨多個 Adobe 產品和工作區指派權限。跨不同的 Adobe 產品為新團隊成員指派所有適當的權限，就如同將它們新增至特定使用者群組一樣簡單。

1. [在Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)中，按一下「 **[!UICONTROL 使用者]**  >  **[!UICONTROL 使用者]** 群組」以建立新使用者群組或編輯現有群組。
1. 遵循&#x200B;*《企業使用者指南》*&#x200B;的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示。

## 指定角色和權限 {#roles-permissions}

只有系統管理員可以在 [!DNL Target] 中設定使用者角色。例如，標準核准者使用者若沒有[!DNL Experience Cloud]管理權限，就無法將觀察者變更為核准者。

系統管理員使用者必須將使用者新增至系統。系統不會自動新增使用者。他們會收到來自[!DNL Experience Cloud]的電子郵件邀請，且必須先確認其電子郵件地址，才能註冊其帳戶。

1. [](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)在 Admin Console 中，按一下&#x200B;**[!UICONTROL 「產品」]**，然後選取所需產品的名稱。

   ![產品索引標籤](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 按一下所需的工作區（例如預設工作區）。

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
   | 發行者 | 類似觀察者角色（可以檢視活動，但無法建立或編輯活動）。 但是，發佈者角色具有激活活動的附加權限。 |

如需詳細資訊，請參閱&#x200B;*《企業使用者指南》*&#x200B;中的[在 Admin Console 中管理產品權限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 訓練影片：如何設定Adobe Target工作區![教學課程徽章](/help/assets/tutorial.png)

學習目標:

* 從 Adobe Target 介面存取 Adobe Admin Console (三個方式)
* 在 Adobe Admin Console 中設定工作區
   * 新增使用者至工作區
   * 新增屬性至工作區
* 瞭解預設工作區

>[!NOTE]
>
>已重新設計[!DNL Target] [!UICONTROL Administration]功能表UI（原稱[!UICONTROL Setup]），以提供改善的效能、減少發行新功能時所需的維護時間，並改善整個產品的使用者體驗。 以下視頻中的資訊通常正確；不過，選項可能位於稍微不同的位置。 更新的影片即將發佈。

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

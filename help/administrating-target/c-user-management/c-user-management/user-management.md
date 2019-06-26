---
description: 您可以在 Adobe Admin Console 中新增使用者並管理其權限。
keywords: 新增使用者; 管理使用者; 使用者權限
seo-description: 您可以在 Adobe Admin Console 中新增使用者並管理其權限。
seo-title: 使用者
solution: Target
subtopic: 快速入門
title: 使用者
topic: Standard
uuid: 9b311dd3-b8fa-483d-aedd-96761cfcd67e
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 使用者{#users}

您可以在 Adobe Admin Console 中新增使用者並管理其權限。

>[!NOTE]
>
>[!UICONTROL ][!UICONTROL 屬性和權限功能屬於 ] Premium 解決方案的一部分。[!DNL Target]在沒有 [!DNL Target] Premium 授權的 [!DNL Target] Standard 中無法使用。
>您可以區分您的組織具有的 Standard 或 Premium 授權，方法是按一下 UI 上方的[!UICONTROL 「設定」]連結。[!DNL Target]
>
>**[!DNL Target]Standard 客戶:** 如果您看見[!UICONTROL 「使用者」]標籤 ([!UICONTROL 「設定 &gt; 使用者」])，表示您的組織具備 [!DNL Target] Standard 授權。[!DNL Target Standard 客戶應該遵循本文的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。
>
>**[!DNL Target]Premium 客戶:** 如果您看見[!UICONTROL 「屬性」]標籤 ([!UICONTROL 「設定 &gt; 屬性」])，表示您的組織具備 [!DNL Target] Premium 授權。[!DNL Target] Premium 客戶應該遵循[企業使用者權限](/help/administrating-target/c-user-management/property-channel/property-channel.md)和[設定企業權限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)中的指示，在 [!DNL Adobe Admin Console] 中新增使用者並指派權限。

只有系統管理員使用者可以新增使用者和管理其權限。系統管理員角色是在 [!DNL Experience Cloud] 層級上指派。[!DNL Experience Cloud] 角色與每個解決方案中管理的角色不同。

當您開始使用 [!DNL Adobe Target] 時，您可以找到 [!DNL Adobe Experience Cloud] 帳戶中預先填入的 ID (結尾是 Adobe.com)。若您需要協助，這些 ID 可供 Adobe 團隊的成員使用，讓他們可以協助處理您的新帳戶及協助您使用 [!DNL Adobe Target]。若要取得協助，請像平常一樣聯絡 Adobe 團隊。

在新使用者使用其 Adobe Experience Cloud 帳戶登入，然後透過按一下[!UICONTROL 「」卡片來登入 ] 之前，您不會在[!DNL Target Standard/Premium]「使用者」[!DNL Target]頁面上看見新使用者列出。

依預設，所有 [!DNL Target] 使用者一開始都具有觀察者權限。

在「使用者」清單中可識別系統管理使用者。如果需要變更您的存取層級，請聯絡其中一位系統管理員使用者。

## 存取 Adobe Admin Console {#access}

若為 Adobe Admin Console 中執行的工作，請遵循下列步驟來存取控制台:

1. 移至 [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) &gt; 使用 Adobe ID 登入 (如果尚未登入)。

   或

   如果您已登入 Experience Cloud，請前往 [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com)，然後按一下頂端導覽列中的[!UICONTROL 應用程式]圖示 &gt; 按一下右側的 **[!UICONTROL 管理]**。

1. (條件式) 如果您可以存取一個以上組織的 [!DNL Admin Console for Enterprise]，請按一下右上角或上方導覽列中的使用者頭像，然後選取需要的組織。

## 新增使用者 {#add-users}

所有使用者管理都必須在 [!DNL Adobe Admin Console for Enterprise] 中執行。不過，[!DNL Target] 中的所有現有使用者將會從 [!DNL Target] 移轉至 [!DNL Admin Console for Enterprise]。

1. [在 Admin Console 中](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，按一下 **[!UICONTROL 使用者]** &gt; **[!UICONTROL 使用者]**，以建立新使用者或編輯現有的使用者。
1. 遵循*《企業使用者指南》*的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示。

## 建立使用者群組 {#user-groups}

您可以建立使用者群組，例如開發人員、分析人員、行銷人員、行政人員等，然後跨多個 Adobe 產品和工作區指派權限。跨不同的 Adobe 產品為新團隊成員指派所有適當的權限，就如同將它們新增至特定使用者群組一樣簡單。

1. [在 Admin Console 中](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，按一下 **[!UICONTROL 使用者]** &gt; **[!UICONTROL 使用者群組]**，以建立新使用者群組或編輯現有的使用者群組。
1. 遵循*《企業使用者指南》*的[在 Experience Cloud 中管理使用者和群組](https://helpx.adobe.com/enterprise/help/users.html)中的指示。

## 指定角色和權限 {#roles-permissions}

只有系統管理員可以在 [!DNL Target] 中設定使用者角色。例如，Standard 核准者使用者也必須有 Experience Cloud 管理員權限，才能將觀察者變更為核准者。

系統管理員使用者必須將使用者新增至系統。系統不會自動新增使用者。使用者要收到來自 Experience Cloud 的電子郵件所邀請，而且在註冊其帳戶之前必須先確認電子郵件位址。

1. [在 Admin Console 中](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，按一下 **[!UICONTROL 「產品」]**，然後選取所需產品的名稱。

   ![產品索引標籤](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 按一下所需組態的名稱。
1. 按一下 **[!UICONTROL 「使用者」]**。

   [!UICONTROL 使用者]索引標籤會顯示該工作區中的所有使用者。

   ![設定使用者](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new.png)

1. 針對每一個使用者，使用[!UICONTROL 「產品角色」]欄的下拉式清單選取所需的權限角色 (觀察者、編輯者或核准者)。

   | 角色 | 說明 |
   |--- |--- |
   | 觀察者 | 可以檢視活動，但無法建立或編輯活動。 |
   | 編輯器 | 可以在活動上線之前建立和編輯活動，但無法核准活動的啟動。 |
   | 核准者 | 可以建立、編輯和啟動或停止活動。 |

如需詳細資訊，請參閱*《企業使用者指南》*中的[在 Admin Console 中管理產品權限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 訓練影片: 如何設定 Target 工作區

學習目標:

* 從 Adobe Target 介面存取 Adobe Admin Console (三個方式)
* 在 Adobe Admin Console 中設定工作區
   * 新增使用者至工作區
   * 新增屬性至工作區
* 瞭解預設工作區

>[!VIDEO](https://video.tv.adobe.com/v/19463/?captions=chi_hant)

---
keywords: 管理;核准者角色;核准者
description: 在收到Adobe Experience Cloud的電子郵件邀請後，執行Adobe Target管理員應該採取的首要工作。
title: 我該從哪裡開始管理[!DNL Target]？
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
TQID: 'https://experienceleague.adobe.com/GfadY-knTwzXCB-n1AZ9u3PtoAyJokn1OXu3elRhgXk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 9%
---
# 管理員入門

在透過[!DNL Adobe Experience Cloud]收到加入[!DNL Adobe Target]的邀請後，請完成這些步驟。 當您準備好設定帳戶預設值時，請參閱[如何管理Target？](/help/main/administrating-target/administrating-target.md)。 如需在UI中尋找&#x200B;**[!UICONTROL 管理]**&#x200B;的協助，請參閱[瞭解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)。

**工作流程總覽**

1. [受邀加入Target](#task_3E0817630774431983FAA3D2CB2E75BD)：系統管理員已將您加入[!DNL Adobe Admin Console]。
1. [接受邀請](#task_24FE66659E634B24AB61DB8497772E17)：登入[!DNL Experience Cloud]並連結您的[!DNL Target]帳戶。
1. [將核准者角色指派給您自己](#task_15CAA437A71444E2932B333D5E66A3C7)：確認您授權型別的存取權和許可權。
1. [使用者管理](/help/main/administrating-target/c-user-management/user-management.md)：新增使用者並指派[!DNL Target Standard]或[!DNL Target Premium]的角色。

## 受邀加入[!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

[!DNL Adobe Admin Console]中的系統管理員必須藉由邀請您加入，將您新增為[!DNL Target]中的使用者。 管理員也應該將您新增至一或多個特定角色的產品設定檔（使用者群組）。 這兩項工作都是在[Adobe Admin Console](https://adminconsole.adobe.com)中完成。

如需逐步指南，請參閱Adobe Enterprise檔案中的[瞭解如何管理使用者和產品設定檔](https://helpx.adobe.com/enterprise/using/users.html)。

管理員完成這些步驟後，您會收到一封邀請電子郵件。

## 接受邀請 {#task_24FE66659E634B24AB61DB8497772E17}

收到加入[!DNL Adobe Experience Cloud]的邀請之後，請接受邀請、登入並接受[!UICONTROL 使用者授權合約] (EULA)。

請使用下列步驟接受邀請，並將[!DNL Target]連結至您的[!DNL Experience Cloud]帳戶：

1. 接受 [!DNL Adobe Experience Cloud] 的邀請。
1. 如果您還沒有 Adobe ID，即會提示您建立 ID。

   如果您已有Adobe ID，請在出現提示時登入。

1. 接受[!UICONTROL 使用條款]。

1. 檢閱您目前已完成的摘要，然後按一下[繼續前往Experience Cloud] **&#x200B;**。

1. 登入[!DNL Adobe Experience Cloud]並按一下&#x200B;**[!UICONTROL 連結帳戶]**。

   >[!NOTE]
   >
   >如果您未連結您的帳戶，則無法存取[!DNL Target]。

   所有[!UICONTROL Experience Cloud]產品都會出現在連結的頁面上。 按一下&#x200B;**[!UICONTROL 連結目標]**，然後輸入您的[!DNL Target]使用者名稱和密碼。
1. 按一下&#x200B;**[!UICONTROL 繼續前往Experience Cloud]**。

   此時，您可能還沒有擁有可連結許可權的產品設定檔；您的系統管理員可以在[!DNL Adobe Admin Console]中指派這些設定檔。
1. 或者，您可以觀看介紹[!DNL Adobe Experience Cloud]的影片。
1. 若要重新整理您的許可權並開啟產品，請登出[!DNL Adobe Experience Cloud]，然後重新登入。
1. 繼續[指派核准者角色](#task_15CAA437A71444E2932B333D5E66A3C7)給您自己。

## 指派核准者角色給您自己 {#task_15CAA437A71444E2932B333D5E66A3C7}

接受邀請並登入之後，請確認[!DNL Target]出現在您的[!DNL Experience Cloud]帳戶中，然後為您自己指派[!DNL Target]的[!UICONTROL 核准者]角色。

選擇符合您授權規範的指引：

* 如果您的組織有[Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905)授權，請參閱[瞭解如何在&#x200B;*使用者*&#x200B;中指定角色和許可權](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。
* 如果您的組織有 [Target Premium](/help/main/c-intro/intro.md#premium) 授權，請參閱&#x200B;*設定企業權限*&#x200B;中的[步驟 6: 指定角色和權限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80)。

然後您可以設定[!DNL Target Standard]或[!DNL Target Premium]的使用者。 請參閱[使用者管理](/help/main/administrating-target/c-user-management/user-management.md)，以取得授權之正確工作流程的概覽和連結。

## 編輯[!UICONTROL 管理]設定所需的許可權 {#admin-permissions}

**在2025年4月22日之前**：在[!DNL Adobe Admin Console]中擁有[!UICONTROL 核准者]許可權的使用者可以在[!DNL Target]中的[[!UICONTROL 管理]](/help/main/administrating-target/administrating-target.md)頁面上編輯或變更所有設定，無論他們的[!DNL Target]角色為何。

**自2025年4月22日起生效**：只有[!UICONTROL 產品]和[!UICONTROL 解決方案]管理員可以更新[[!UICONTROL 管理]](/help/main/administrating-target/administrating-target.md)區段中的設定，無論他們在[!DNL Target]工作區中的角色為何。 沒有此許可權的使用者擁有[!UICONTROL 管理]區段的唯讀存取權。

此變更改善了組織對[!DNL Target]執行個體設定的控制，並有助於防止可能影響跨測試和個人化團隊的活動交付的意外更新。

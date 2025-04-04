---
keywords: 管理;核准者角色;核准者
description: 在收到 [!DNL Adobe Experience Cloud]的電子郵件邀請後，執行 [!DNL Adobe Target] 管理員應該採取的第一個工作。
title: 我該從哪裡開始管理 [!DNL Target]？
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
source-git-commit: 0618d39fc5966c64cceea8f5bcccb625fc243ebb
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 32%

---

# 管理員入門

本文包含[!DNL Adobe Target]管理員在收到電子郵件寄送的[!DNL Adobe Experience Cloud]加入邀請時應採取的前幾個步驟。

## 受邀加入[!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

[!DNL Adobe Admin Console]中的系統管理員必須藉由邀請您加入，將您新增為[!DNL Target]中的使用者。 然後，系統管理員應將您新增至一或多個角色特定群組。 這兩項工作都是在[Adobe Admin Console](https://adminconsole.adobe.com)中執行。

如需詳細資訊，請參閱&#x200B;*Experience Cloud與核心服務說明*&#x200B;中的[管理Experience Cloud使用者和產品](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)。

系統管理員執行這些步驟後，您將會收到一封邀請電子郵件。

## 接受邀請 {#task_24FE66659E634B24AB61DB8497772E17}

收到加入[!DNL Adobe Experience Cloud]的邀請之後，請接受邀請、登入並接受[!UICONTROL End User License Agreement] (EULA)。

1. 接受 [!DNL Adobe Experience Cloud] 的邀請。
1. 如果您還沒有 Adobe ID，即會提示您建立 ID。

   如果您有Adobe ID，則會辨識您的Adobe ID，並提示您登入。
1. 接受[!UICONTROL Terms of Use]。
1. 檢閱您目前已完成的摘要，然後按一下&#x200B;**[!UICONTROL Continue to Experience Cloud]**。
1. 登入[!DNL Adobe Experience Cloud]並按一下&#x200B;**[!UICONTROL Link Account]**。

   >[!NOTE]
   >
   >如果您並未連結您的帳戶，將無法存取 [!DNL Target]。

   所有[!UICONTROL Experience Cloud]產品都會出現在連結的頁面上。 按一下`Link Target`並輸入您的[!DNL Target]使用者名稱和密碼以存取[!DNL Target]。
1. 按一下 **[!UICONTROL Continue to Experience Cloud]**。

   此時，您還沒有任何群組設定了供您連結的權利。
1. 如果需要，可觀看為您介紹 [!DNL Adobe Experience Cloud] 的影片。
1. 若要查看您的新權限和存取產品，請從 [!DNL Adobe Experience Cloud] 登出，然後重新登入。
1. 繼續下一個步驟，[指派核准者角色給您自己](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)。

## 指派核准者角色給您自己 {#task_15CAA437A71444E2932B333D5E66A3C7}

接受加入[!DNL Adobe Experience Cloud]的邀請並登入之後，請確認[!DNL Target]已新增至您的[!DNL Experience Cloud]帳戶，然後為您自己指派[!DNL Target]的[!UICONTROL Approver]角色。

如果您的組織有 [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) 授權，請參閱&#x200B;*使用者*&#x200B;中的[指定角色和權限](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。

如果您的組織有 [Target Premium](/help/main/c-intro/intro.md#premium) 授權，請參閱&#x200B;*設定企業權限*&#x200B;中的[步驟 6: 指定角色和權限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80)。

下一步應該是在[!DNL Target Standard]和[!DNL Target Premium]中設定使用者。 如需詳細資訊，請參閱[使用者管理](/help/main/administrating-target/c-user-management/user-management.md)。

## 編輯[!UICONTROL Administration]設定所需的許可權 {#admin-permissions}

**在2025年4月22日之前**：在[!DNL Adobe Admin Console]中擁有[!UICONTROL Approvers]許可權的使用者可以編輯或變更[!DNL Target]的[[!UICONTROL Administration]頁面](/help/main/administrating-target/administrating-target.md)頁面上的所有設定，無論他們的[!DNL Target]角色為何。

**自2025年4月22日起生效**：只有[!UICONTROL Product]和[!UICONTROL Solutions]管理員能夠更新[[!UICONTROL Administration]](/help/main/administrating-target/administrating-target.md)區段中的設定，無論他們在[!DNL Target]工作區中的角色為何。 沒有此許可權的使用者將擁有[!UICONTROL Administration]區段的唯讀存取權。

此更新加強了組織對[!DNL Target]執行個體設定的控制，防止了可能影響跨各種測試和個人化團隊的活動傳送的意外更新。

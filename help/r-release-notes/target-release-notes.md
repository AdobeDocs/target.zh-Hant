---
description: 發行說明，提供最新或即將到來[！DNL Adobe Target]發行。
keywords: 版本說明
seo-description: 發行說明，提供最新或即將到來[！DNL Adobe Target]發行。
seo-title: Adobe Target發行說明(搶鮮版)
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a6aae8602b8f3c3f879bd6e3e37591f330197cf8

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新日期: 2019 年 7 月 31 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## 公告

**2019年月31日**

[!UICONTROL 企業權限] 可讓 [!DNL Target] 客戶使用單一組織，但將其分為不同團隊或工作流程的工作區。[!UICONTROL 企業權限] 功能可協助您有效擴展團隊內部的最佳化程式。Although this feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until the [!DNL Target] February 2019 release. Adobe已更新管理員API，讓您可以使用整合帳戶存取組織中建立的所有工作區。So, while earlier, Admin APIs were restricted to the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, [!UICONTROL Enterprise Permissions] will provide customers with the following access controls:

* 您可以選擇可套用整合的工作區
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

**必要動作**：目前針對所有工作區運用API for資源(活動、對象、選件和報告)的客戶，都需要將現有的Adobe I/整合存取權授與所有工作區的所需角色。Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of the role selected from the [!UICONTROL Product Role] drop-down list. 在即將推出的版本中，您現在可以選取所需的角色。

This action should be performed before **September 4, 2019**. After the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. 預先設定整合角色並沒有負面影響。

For step-by-step instructions and more information, see [Grant Adobe I/O integrations access to workspaces and assign roles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.8.1 (2019 年 8 月 20 日) {#tgt-19-8-1}

此維護發行包含下列增強功能：

* 數個安全性修正，包括對Visual Experience Composer(CMS)中Rich Text Editor(RTE)的安全性更新。(TGT-35383)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

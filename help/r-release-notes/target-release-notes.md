---
description: 發行說明，提供最新或即將到來[！DNL Adobe Target]發行。
keywords: 版本說明
seo-description: 發行說明，提供最新或即將到來[！DNL Adobe Target]發行。
seo-title: Adobe Target 版本說明 (發行前)
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 3b21fede9df1ef61da194fac55ffb862c037258a

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新日期: 2019 年 7 月 31 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
>
>括號內的問題編號供 [!DNL Adobe] 內部使用。

## 公告

**2019年月31日**

[!UICONTROL 企業權限] 可讓 [!DNL Target] 客戶使用單一組織，但將其分為不同團隊或工作流程的工作區。[!UICONTROL 企業權限] 功能可協助您有效擴展團隊內部的最佳化程式。雖然此功能可在 [!DNL Target] UI中使用，但是Admin API會在2019 [!DNL Target] 年月發行之前，將其對應的支援失效。Adobe已更新管理員API，讓您可以使用整合帳戶存取組織中建立的所有工作區。因此，在舊版中，管理員API僅限於預設工作區，2019年月更新授予所有具有 [!UICONTROL 核准者] 存取權的工作區存取權。

在即將 [!DNL Target] 推出的2019年月發行版本中 [!UICONTROL ，企業權限] 將為客戶提供下列存取控制：

* 您可以選擇可套用整合的工作區
* 您可以將角色套用至Adobe I/整合： [!UICONTROL 核准者]、 [!UICONTROL 編輯者]或 [!UICONTROL 觀察員]。

**必要動作**：目前針對所有工作區運用API for資源(活動、對象、選件和報告)的客戶，都需要將現有的Adobe I/整合存取權授與所有工作區的所需角色。在月發行版本之前，所有使用 [!UICONTROL 核准者] 存取的整合都會使用，不論從 [!UICONTROL 「產品角色」] 下拉式清單中選取的角色為何。在即將發行的版本中，您現在可以選取所需的角色。

此動作應在2019 **年月的月份**&#x200B;執行。在2019 [!DNL Target] 年月發行後，存取控制將會啓動，而且如果這是您目前設定的方式，您將觀察到僅限預設工作區。預先設定整合角色並沒有負面影響。

如需逐步指示和更多資訊，請參閱 [「授予Adobe I/O整合存取工作區並指派角色](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)」。

## Target Standard/Premium 19.9.1 (2019 年 9 月 24 日)

此維護發行包含下列增強功能：

* 數個安全性修正，包括對Visual Experience Composer(CMS)中Rich Text Editor(RTE)的安全性更新。(TGT-35383)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

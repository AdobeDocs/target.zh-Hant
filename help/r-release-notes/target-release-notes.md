---
description: 提供最新或即將發行的[!DNL Adobe Target]版本功能、增強功能和修正資訊的發行說明。
keywords: 版本說明
seo-description: 提供最新或即將發行的[!DNL Adobe Target]版本功能、增強功能和修正資訊的發行說明。
seo-title: Adobe Target 版本說明 (發行前)
solution: Target
title: Target 版本說明 (發行前)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: d675c6875c8474ba490956ea395076eef5b9e58f

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新: 2019 年 9 月 24 日**

>[!NOTE]
>
>以下版本說明包含發行前版本的資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
>
>括號內的問題編號供 [!DNL Adobe] 內部使用。

## 公告

**2019年7月31日**

[!UICONTROL 「企業權限] 」可 [!DNL Target] 讓客戶使用單一組織，但可將其分為適用於不同團隊或工作流程的工作區。 「企 [!UICONTROL 業權限] 」功能有助於跨團隊有效縮放最佳化計畫。 雖然此功能可在UI中使用， [!DNL Target] 但管理API在2019年2月發行之前，都缺乏相 [!DNL Target] 應的支援。 Adobe已更新管理API，讓您可以使用整合帳戶存取組織中建立的所有工作區。 因此，雖然之前的管理API僅限於預設工作區，但2019年2月的更新會授與所有具有核准者存取權的工作區 [!UICONTROL 的存] 取權。

在即將推出的2019 [!DNL Target] 年9月版 [!UICONTROL 本中，「企業權限] 」將為客戶提供下列存取控制：

* You can choose the workspaces to which the integration can be applied
* 您可以將角色套用至Adobe I/O整合：核 [!UICONTROL 準者]、 [!UICONTROL 編輯者]或觀 [!UICONTROL 察者]。

**需要執行的動作**:目前在所有工作區間運用API進行資源（活動、觀眾、優惠和報告）的CRUD作業的客戶，必須授與其現有的Adobe I/O整合存取權給具有所需角色的所有工作區。 在9月發行之前，所有整合都會使用 [!UICONTROL Approver] （核准者）存取權來運作，不論從「產品角色  」下拉式清單中選取的角色為何。 在即將發行的版本中，您現在可以選取所要的角色。

此動作應於2019年8月 **執行**。 After the  September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. [!DNL Target]預先設定整合角色並無不良後果。

如需逐步指示和詳細資訊，請參閱授 [予Adobe I/O整合工作區的存取權並指派角色](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)。

## Target Standard/Premium 19.9.2 (2019 年 9 月 30 日)

此維護髮行包含下列增強功能：

* 數項安全性修正，包括Visual Experience Composer(VEC)中Rich Text Editor(RTE)的安全性更新。 (TGT-35383)

## Target Standard/Premium 19.9.1 (2019 年 9 月 10 日)

| 功能/增強功能 | 說明 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) Enterprise Permissions | 在Target 2019年9月發行中，「企業權限」為客戶提供下列存取控制：<UL><li>您可以選擇可套用整合的工作區。</li><li>您可以將角色套用至Adobe I/O整合：批准者、編輯者或觀察者。</li></ul>如需逐步指示和詳細資訊，請參閱授 [予Adobe I/O整合工作區的存取權並指派角色](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)。 |

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

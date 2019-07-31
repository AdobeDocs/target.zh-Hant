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
source-git-commit: 48cb808283c9b2858e1bd041feb3fe8228253d6a

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

Enterprise Permissions allows [!DNL Target] customers to use a single organization, but divide it into workspaces for their different teams or workflows. 這有助於提高團隊間最佳化計劃的效率。Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier this year. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, Target Enterprise Permissions will provide customers with the following access controls:

* 您可以選擇可套用整合的工作區
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

此更新將支援下列使用案例：

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* 授予Adobe I/O存取權，以適當的角色選取工作區，讓中央團隊只在少數工作區中進行API驅動的變更。
* 每當團隊準備好要探索API並選擇角色時，每位團隊成員都會決定自行整合。
* 混合並比對上述任何藍本。

**需要的動作**：目前針對所有工作區運用API for資源(活動、對象、選件和報告)的客戶，需要將現有的Adobe I/整合存取權授與所有工作區，以依其使用案例使用所需角色。You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, irrespective of choice made in the [!UICONTROL Product Role] drop-down list. 您現在可以選擇所要的角色。

This action *must* be performed before September 4, 2019 to not face any disruption on your end. 如果未執行此動作，在[！DNL Target月發行時，存取控制將會啓動，而且如果這是您目前設定的方式，您將觀察到僅限預設工作區。根據上述准則，事先設定整合並無負面反應。您越早越好。視組織中的工作區數目而定，需要少許時間來設定此設定。此程序只需按幾下滑鼠，即可將現有的整合新增至具有所需角色的工作區。

## Target Standard/Premium 19.8.1 (2019 年 8 月 20 日) {#tgt-19-8-1}

此維護發行包含下列增強功能：

* 數個安全性修正，包括對Visual Experience Composer(CMS)中Rich Text Editor(RTE)的安全性更新。(TGT-35383)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)

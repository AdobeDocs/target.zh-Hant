---
description: 在建立活動時，從三個步驟引導工作流程內建立僅限活動的對象。這些隨選對象可用在相同活動內的其他位置，但不會儲存在對象資料庫而用於其他活動。
keywords: 對象;對象規則;建立對象;建立對象;僅限活動;僅活動;臨機
seo-description: 在建立活動時，從Adobe Target三步驟引導式工作流程建立僅限活動的對象。這些隨選對象可用在相同活動內的其他位置，但不會儲存在對象資料庫而用於其他活動。
seo-title: 建立僅限於此活動的對象在Adobe Target中
solution: Target
title: 建立僅限於此活動的對象
topic: Advanced,Standard,Classic
uuid: 3d0898d0-96e8-4bc9-86bd-3ae39db0e74d
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 建立僅限於此活動的對象{#create-an-activity-only-audience}

在建立活動時，從三個步驟引導工作流程內建立僅限活動的對象。These ad hoc audiences can be used in other places within the same activity, but are not stored in the [!UICONTROL Audiences Library] for use in other activities.

僅限於此活動的對象提供下列優點:

* You can use activity-only audiences to create an audience that you want to use only once and you do not want to store it in the [!UICONTROL Audiences Library]. This prevents the [!UICONTROL Audiences Library] from being cluttered with audiences that you never want to use again.
* Activity-only audiences are not visible in the [!UICONTROL Audiences Library]. 因此這些對象會獲得保護，不會受組織中的其他人不必要的變更。

1. While creating an [activity](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), on the **[!UICONTROL Target]** page, click the three vertical ellipses, then click **[!UICONTROL Replace Audience]**.

   ![步驟結果](assets/edit_audience.png)

1. On the [!UICONTROL Choose Audience] page, click **[!UICONTROL Activity Only Audience]**.

   ![](assets/activity-only-aud.png)

1. 按一下&#x200B;**[!UICONTROL 「建立對象」]**。
1. 輸入描述性的對象名稱。
1. 按一下&#x200B;**[!UICONTROL 「+ 新增規則」]**。

   規則可讓您將對象限制在網站訪客的子集。

1. 選取規則類型。

   每個規則類型都有其專屬的參數。請參閱[對象的類別](../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D)，以取得關於設定每個類型的對象規則的詳細資訊。

1. 定義規則參數。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 考量事項

處理僅限於此活動的對象時，請記得下列資訊:

* 您可以在可視化體驗撰寫器 (VEC) 或表單式體驗撰寫器中建立僅限於此活動的對象。此功能會取代舊版 Target 中的細分規則。
* You can create an activity to store in the [!UICONTROL Audience Library] for reuse in other activities or you create an activity-only audience. 儲存對象之後，您無法變更對象類型。
* 現有活動的細分已移轉至僅限於此活動的對象。
* Activity-only audiences have a status of [!UICONTROL Used] or [!UICONTROL Unused]. 在儲存活動之前，會將僅限於此活動的對象顯示為「未使用」。如果維持未使用而您嘗試儲存活動，會顯示警告訊息，通知您將刪除未使用的僅限於此活動的對象。
* 您可以在可透過對象選擇器存取的快顯卡上檢視對象定義詳細資料，而不需開啟對象。
* 您可以[結合多個對象](../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)以建立僅限於此活動的對象。


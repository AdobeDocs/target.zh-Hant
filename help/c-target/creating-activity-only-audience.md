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
source-git-commit: c853ac9a9447a10b753e53fd707f6f72db2889b0

---


# 建立僅限於此活動的對象{#create-an-activity-only-audience}

在建立活動時，從三個步驟引導工作流程內建立僅限活動的對象。這些臨機對象可用於相同活動內的其他位置，但不會儲存在 [!UICONTROL 「對象庫] 」中，以便用於其他活動。

僅限於此活動的對象提供下列優點:

* 您可以使用僅限活動對象建立對象，只想使用一次，而且不要將其儲存在 [!UICONTROL 「對象庫]」中。這可防止 [!UICONTROL 「對象程式庫] 」雜亂地與您不想重復使用的對象混淆。
* 「 [!UICONTROL 對象庫]」中不會顯示僅限活動的對象。因此這些對象會獲得保護，不會受組織中的其他人不必要的變更。

1. 建立 [活動時](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)，在 **[!UICONTROL 「目標]** 」頁面上按一下三個垂直橢圓形，然後按一下 **[!UICONTROL 「取代對象]**」。

   ![步驟結果](assets/edit_audience.png)

1. 在 [!UICONTROL 「選擇對象] 」頁面上，按一下 **[!UICONTROL 「僅限活動對象]**」。

   ![](assets/activity-only-aud.png)

1. 按一下 **[!UICONTROL 「建立對象」]**。
1. 輸入描述性的對象名稱。
1. 按一下 **[!UICONTROL 「+ 新增規則」]**。

   規則可讓您將對象限制在網站訪客的子集。

1. 選取規則類型。

   每個規則類型都有其專屬的參數。請參閱[對象的類別](../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D)，以取得關於設定每個類型的對象規則的詳細資訊。

1. 定義規則參數。
1. 按一下 **[!UICONTROL 「儲存」]**。

## 考量事項

處理僅限於此活動的對象時，請記得下列資訊:

* 您可以在可視化體驗撰寫器 (VEC) 或表單式體驗撰寫器中建立僅限於此活動的對象。此功能會取代舊版 Target 中的細分規則。
* 您可以建立要儲存在 [!UICONTROL 觀眾程式庫中的活動，] 以便在其他活動中重復使用，或建立僅限活動的對象。儲存對象之後，您無法變更對象類型。
* 現有活動的細分已移轉至僅限於此活動的對象。
* 僅限活動的對象具有 [!UICONTROL 「已使用」] 或「 [!UICONTROL 未使用]」狀態。在儲存活動之前，會將僅限於此活動的對象顯示為「未使用」。如果維持未使用而您嘗試儲存活動，會顯示警告訊息，通知您將刪除未使用的僅限於此活動的對象。
* 您可以在可透過對象選擇器存取的快顯卡上檢視對象定義詳細資料，而不需開啟對象。
* 您可以[結合多個對象](../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)以建立僅限於此活動的對象。


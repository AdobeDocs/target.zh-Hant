---
keywords: 設定; 優先順序
description: 瞭解如何 [!DNL Adobe Target] 會根據要傳送至頁面的活動，以不同方式決定哪些活動（或多個活動） [!DNL Target] 介面以及您使用的活動建立功能。
title: 如何 [!DNL Target] 指派優先順序給不同活動？
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: be6e45ff301f549eb5be24a65b05c4a9c1cd6089
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 37%

---

# 優先順序

[!DNL Adobe Target] 會根據要傳送至頁面的活動，以不同方式決定哪些活動（或多個活動） [!DNL Target] 介面以及活動建立功能([[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) 或 [表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md))。

## [!UICONTROL Visual Experience Composer] 僅限或 [!UICONTROL Form-Based Experience Composer] 使用全域 [!DNL Target] 僅請求 {#section_4A0A317DFED345649B58B0CB5B410C8B}

如果您的公司僅使用VEC，則同一呼叫可傳回多個活動的內容。 活動依據下列決策流程來傳送:

1. 此 [!DNL Target] 伺服器呼叫來到 [!DNL Target] 包含URL的相關資訊。
1. [!DNL Target] 提取在該URL上執行的每個活動。
1. [!DNL Target] 嘗試將訪客比對至活動。

   如果訪客已位於 [!UICONTROL A/B Test] 或 [!UICONTROL Multivariate Test] 活動，會比對至該活動，直到轉換為止。 如果他們先前位於 [!UICONTROL Experience Targeting] 活動，它們必須再次符合它。 如果他們符合對象規則，則訪客會落入這些活動中並進入特定體驗。

1. 訪客符合的所有活動和體驗的內容會傳回至頁面。
1. 如果每個活動的內容參考不同 [CSS選取器](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)，則會顯示所有內容。

   如果有重疊或重複的 CSS 選取器，則會顯示具有最高優先順序的活動內容。在頁面上執行且來自所有活動的結果會計入並反映在報表中。

   >[!IMPORTANT]
   >
   >[!DNL Target] 傳回頁面上所有活動的內容（從最低優先順序內容開始），接著以最低至最高的優先順序，由每個活動依序覆寫。 通常，這會顯示最高優先順序的內容。 但是，如果低優先順序活動改變了頁面的DOM結構，則較高優先順序活動可能無法識別頁面結構，因此會顯示較低優先順序的內容。 在頁面上執行且來自所有活動的結果會計入並反映在報表中。

1. 如果有多個活動共用優先順序層級，則有兩個分界線：

   * 如果只有一個活動有對象鎖定目標，則會顯示該活動。
   * 如果全部或都沒有目標定位，則會顯示先核准的活動。

## [!UICONTROL Form-Based Experience Composer]和[!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

如果您的公司使用 [!UICONTROL Form-Based Experience Composer] *和* VEC，來自多個的內容 [!UICONTROL Form-Based Experience Composer] 和VEC活動可以傳送。 以前，表單式工作流程中只能傳送一個活動。 可提供的表單式活動數量不再有任何限制。

活動傳遞是使用下列決策流程決定:

1. [!DNL Target] 伺服器呼叫來到 [!DNL Target] ，其中包含關於 [!DNL Target] 要求和URL。
1. [!DNL Target] 提取中執行的所有活動 [!DNL Target] 要求。
1. [!DNL Target] 嘗試將訪客比對至活動。

   如果訪客已位於 [!UICONTROL A/B Test] 或 [!UICONTROL Multivariate Test] 活動，會比對至該測試，直到轉換為止。 如果他們先前位於 [!UICONTROL Experience Targeting] 活動，它們必須再次符合它。 如果他們符合對象規則，則訪客會落入這些活動中並進入特定體驗。

1. 如果表單式活動為最高優先順序，則會傳回該活動內容以及VEC活動中的所有相符活動內容。
1. 如果VEC活動是最高優先順序，則會傳回所有相符VEC活動的內容，但不會傳回任何表單式活動內容。

   在頁面上執行且來自所有活動的結果會計入並反映在報表中。

**範例**

如果您有兩個活動，一個是針對品牌搜尋關鍵字「Nike」，第二個是針對非品牌關鍵字「運動鞋」，則會檢查這兩個活動的優先順序。 如果 Nike 活動具有較高的優先順序，則會顯示該內容。同樣地，如果 sneakers 活動具有較高的優先順序，則會顯示其內容。

如果兩個已鎖定的目標活動有相同的優先順序，則會顯示最近檢視的活動。如果訪客是首次前往頁面，則顯示最近啟動的活動。

## [!UICONTROL Form-Based Experience Composer] 與非全域 [!DNL Target] 請求 {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

如果您的公司使用 [!DNL Target] 全域以外的要求 [!DNL Target] 表單式撰寫器中的請求，每次呼叫只能傳回一個活動的內容。 活動傳遞是使用下列決策流程決定:

1. 此 [!DNL Target] 伺服器呼叫來到 [!DNL Target] ，其中包含關於 [!DNL Target] 要求和URL。
1. [!DNL Target] 提取中執行的所有活動 [!DNL Target] 要求。
1. [!DNL Target] 會嘗試將訪客配對至最高優先順序的活動。

   如果訪客已位於 [!UICONTROL A/B Test] 或 [!UICONTROL Multivariate Test] 活動，會比對至該活動，直到轉換為止。 如果他們先前位於 [!UICONTROL Experience Targeting] 活動，它們必須再次符合它。 如果他們符合對象規則，則訪客會落入這些活動中並進入特定體驗。

1. 如果有多個活動共用優先順序層級，則有兩個分界線：

   * 如果只有一個活動有對象鎖定目標，則會顯示該活動。
   * 如果全部或都沒有目標定位，則會顯示先核准的活動。

## 範例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>視您的設定而定，優先順序值會有所不同。您可以使用舊版設定 [!UICONTROL Low]， [!UICONTROL Medium]，或 [!UICONTROL High]，或您可啟用0至999的精細優先順序。 如需詳細資訊，請參閱 [活動設定](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

回應: offer1

**兩個活動只會使用在中建立的選件 [!UICONTROL Visual Experience Composer] 適用於不同的選取器**

* 活動 1: target-global-mbox, selector1, visualExpCompOffer1, 低優先順序
* 活動 2: target-global-mbox，selector2，visualExpCompOffer2，優先順序高

回應: visualExpCompOffer1, visualExpCompOffer2

**兩個活動只會使用在中建立的選件 [!UICONTROL Visual Experience Composer] 針對相同選取器**

* 活動 1: target-global-mbox, selector1, visualExpCompOffer1, 低優先順序
* 活動 2: target-global-mbox，selector1，visualExpCompOffer2，優先順序高

回應: visualExpCompOffer1, visualExpCompOffer2

## 訓練影片: 活動設定 (3: 02)

此影片包括關於活動設定的資訊。

* 輸入活動的目標
* 設定活動的優先順序層級
* 排程活動開始和結束時間
* 新增報表的對象，以建立報表篩選器
* 輸入活動的備註

>[!VIDEO](https://video.tv.adobe.com/v/17381)

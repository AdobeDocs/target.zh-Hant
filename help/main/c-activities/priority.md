---
keywords: 設定; 優先順序
description: 瞭解[!DNL Adobe Target]如何根據您使用的[!DNL Target]介面和活動建立功能，以不同方式決定要傳遞至頁面的活動（或活動）。
title: '[!DNL Target]如何將優先順序指派給不同的活動？'
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
TQID: 'https://experienceleague.adobe.com/KSkJ1CDkd4hgwnLQ1RKn8l8r2MDIO-6flcHcdN0c0oQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 19%
---
# 優先順序 {#priority}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解[!DNL Adobe Target]如何根據體驗撰寫器和使用中的[!DNL Target]請求型別，決定要傳送哪些活動至頁面。

>[!ENDSHADEBOX]

[!DNL Adobe Target]會根據您使用的[!DNL Target]介面以及活動建立功能([**[!UICONTROL 視覺化體驗撰寫器(VEC)]**](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)或[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md))，以不同方式決定要傳遞至頁面的活動（一或多個活動）。 下表總結了三種情況，並在以下各節中詳細說明。

| 藍本 | 可交付的活動 | 返回的內容 |
|---|---|---|
| 僅&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**，或僅具有全域[!DNL Target]請求的&#x200B;**[!UICONTROL 表單式體驗撰寫器]** | 多個 | 所有相符活動的內容。 如果選取器重疊，則會顯示最高優先順序活動的內容。 |
| **[!UICONTROL 表單式體驗撰寫器]**&#x200B;和&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** | 多個 | 如果表單式活動具有最高優先順序，則其內容及所有相符VEC活動的內容。 如果VEC活動具有最高優先順序，則只會顯示所有相符VEC活動的內容。 |
| 具有非全域[!DNL Target]要求的&#x200B;**[!UICONTROL 表單式體驗撰寫器]** | 每個呼叫一個 | 最高優先順序的比對活動的內容。 |

## VEC或具有全域請求的[!UICONTROL 表單式體驗撰寫器] {#section_4A0A317DFED345649B58B0CB5B410C8B}

如果您的公司僅使用VEC，則同一呼叫可傳回多個活動的內容。 活動依據下列決策流程來傳送:

1. [!DNL Target]伺服器呼叫達到[!DNL Target]。 呼叫中攜帶有請求之頁面URL的相關資訊。
1. [!DNL Target]提取該URL上執行的每個活動。 這些活動是傳送的候選專案。
1. [!DNL Target]嘗試將訪客比對至候選活動。

   {{visitor-matching}}

1. 訪客相符的所有活動和體驗的內容會傳回至頁面，以便針對相同呼叫傳送來自數個活動的內容。
1. [!DNL Target]比較每個活動內容參考的[CSS選取器](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)。 如果活動參考不同的選取器，則會顯示所有內容。
1. 如果選取器重疊或重複，則會顯示最高優先順序活動的內容。

   >[!IMPORTANT]
   >
   >[!DNL Target]會從最低優先順序的內容開始，傳回頁面上所有活動的內容，接著以最低至最高的優先順序，由每個活動依序覆寫。 通常，這會顯示最高優先順序的內容。 但是，如果低優先順序活動改變頁面的DOM結構，則高優先順序活動可能無法辨識頁面結構，因此會顯示低優先順序內容。

1. 如果多個活動共用一個優先順序層級，則會套用分層。 如果只有一個活動具有對象目標定位，則會顯示該活動。 如果所有活動或無活動具有目標定位，則會顯示先核准的活動。
1. 在頁面上執行且來自所有活動的結果會計入並反映在報表中。

## [!UICONTROL 表單式體驗撰寫器]和VEC {#section_4620253E1CE942DD830724C7822B175F}

如果您的公司使用[!UICONTROL 表單式體驗撰寫器] *和* VEC，則可以傳遞多個[!UICONTROL 表單式體驗撰寫器]和VEC活動的內容。 以前，表單式工作流程中只能傳送一個活動。 可提供的表單式活動數量不再有任何限制。

活動傳遞是使用下列決策流程決定:

1. [!DNL Target]伺服器呼叫達到[!DNL Target]。 此呼叫攜帶有關[!DNL Target]要求和URL的資訊。
1. [!DNL Target]提取該[!DNL Target]要求中執行的每個活動。 這些活動是傳送的候選專案。
1. [!DNL Target]嘗試將訪客比對至候選活動。

   {{visitor-matching}}

1. [!DNL Target]會檢查哪些相符的活動具有最高優先順序，以及該活動是在[!UICONTROL 表單式體驗撰寫器]中或在VEC中建立。
1. 如果表單式活動具有最高優先順序，則會傳回其內容以及所有相符VEC活動的內容。
1. 如果VEC活動具有最高優先順序，則會傳回所有相符VEC活動的內容，但不會傳回任何表單式活動內容。
1. 在頁面上執行且來自所有活動的結果會計入並反映在報表中。

**範例**

有兩個活動存在：一個是針對品牌搜尋關鍵字「Nike」，另一個是針對非品牌關鍵字「運動鞋」。 系統會檢查兩個活動的優先順序。 如果Nike活動的優先順序較高，則會顯示其內容。 同樣地，如果 sneakers 活動具有較高的優先順序，則會顯示其內容。

如果兩個已鎖定的目標活動有相同的優先順序，則會顯示最近檢視的活動。 如果訪客是首次前往頁面，則顯示最近啟動的活動。

## 具有非全域請求的[!UICONTROL 表單式體驗撰寫器] {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

如果您的公司使用表單式撰寫器中全域[!DNL Target]請求以外的[!DNL Target]請求，則每個呼叫只能傳回一個活動的內容。 活動傳遞是使用下列決策流程決定:

1. [!DNL Target]伺服器呼叫達到[!DNL Target]。 此呼叫攜帶有關[!DNL Target]要求和URL的資訊。
1. [!DNL Target]提取該[!DNL Target]要求中執行的每個活動。 這些活動是傳送的候選專案。
1. [!DNL Target]嘗試將訪客配對至最高優先順序的候選活動。

   {{visitor-matching}}

1. 如果多個活動共用一個優先順序層級，則會套用分層。 如果只有一個活動具有對象目標定位，則會顯示該活動。 如果所有活動或無活動具有目標定位，則會顯示先核准的活動。
1. 該單一活動的內容會傳回至頁面。

## 範例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>視您的設定而定，優先順序值會有所不同。 您可以使用&#x200B;**[!UICONTROL 低]**、**[!UICONTROL Medium]**&#x200B;或&#x200B;**[!UICONTROL 高]**&#x200B;的舊設定，或者您可以啟用從0到999的微調優先順序。 如需詳細資訊，請參閱[活動設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC)。

**兩個活動只會針對不同的選取器，使用在[!UICONTROL 視覺化體驗撰寫器]中建立的選件**

* 活動 1: target-global-mbox, selector1, visualExpCompOffer1, 低優先順序
* 活動 2: target-global-mbox，selector2，visualExpCompOffer2，優先順序高

回應: visualExpCompOffer1, visualExpCompOffer2

**兩個活動只會使用在[!UICONTROL 視覺化體驗撰寫器]中為相同選取器建立的選件**

* 活動 1: target-global-mbox, selector1, visualExpCompOffer1, 低優先順序
* 活動 2: target-global-mbox，selector1，visualExpCompOffer2，優先順序高

回應: visualExpCompOffer1, visualExpCompOffer2

## 訓練影片：活動設定(3:02)

此影片包括關於活動設定的資訊。

* 輸入活動的目標
* 設定活動的優先順序層級
* 排程活動開始和結束時間
* 新增報表的對象，以建立報表篩選器
* 輸入活動的備註

>[!VIDEO](https://video.tv.adobe.com/v/17381)

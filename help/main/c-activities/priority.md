---
keywords: 設定; 優先順序
description: 瞭解如何Adobe [!DNL Target] 確定要將哪些活動（或活動）以不同的方式提交到頁面，具體取決於 [!DNL Target] 介面和您正在使用的活動建立功能。
title: 如何 [!DNL Target] 是否將優先順序分配給不同的活動？
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1162'
ht-degree: 87%

---

# 優先順序

根據您使用的 Target 介面以及活動建立功能類型 (可視化體驗撰寫器或表單式撰寫器)，Target 會針對要傳遞至頁面的活動 (或哪些活動) 進行不同判斷。

## 僅目標標準/高級視覺體驗作曲家或使用全局的基於表單的作曲家 [!DNL Target] 僅請求 {#section_4A0A317DFED345649B58B0CB5B410C8B}

如果您的公司僅使用 Target Standard/Premium 和可視化體驗撰寫器，則同一個呼叫可能傳回多個活動的內容。活動依據下列決策流程來傳送:

1. Target 伺服器呼叫隨附 URL 的相關資訊而傳到 Target。
1. Target 提取該 URL 上執行的每一個活動。
1. Target 會嘗試將訪客匹配到活動。

   如果訪客已在 A/B 測試或多變數測試中，則會將它們匹配到該測試中，直到它們轉換。如果他們先前在體驗鎖定目標活動中，則必須將他們再次匹配到該活動中。如果他們符合對象規則，則訪客會落入這些活動中並進入特定體驗。

1. 訪客符合的所有活動和體驗的內容會傳回至頁面。
1. 如果每一個活動的內容參考不同的 [CSS 選取器](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)，則會顯示所有內容。

   如果有重疊或重複的 CSS 選取器，則會顯示具有最高優先順序的活動內容。在頁面上執行且來自所有活動的結果會計入並反映在報表中。

   >[!IMPORTANT]
   >
   >Target 會從最低優先順序的內容開始，傳回頁面上所有活動的內容，接著以最低至最高的優先順序，由每一個活動依序覆寫。在大部分情況下，這會導致顯示最高優先順序的內容。不過，如果較低優先順序的活動改變頁面的 DOM，則較高優先順序的活動可能無法辨識頁面結構，所以會顯示較低優先順序的內容。在頁面上執行且來自所有活動的結果會計入並反映在報表中。

1. 如果多個活動有相同的優先順序層級，則有兩個延長賽:

   * 如果只有一個活動有對象鎖定目標，則會顯示該活動。
   * 如果所有或全部均無鎖定目標，則顯示先核准的活動。

## 目標標準/高級表單編寫器和 [!DNL Target] 標準/高級視覺體驗作曲家 {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>此資訊也適用在 [!DNL Target Classic] 中建立的任何執行中的促銷活動。

如果您的公司使用 Target Standard/Premium 中的表單式撰寫器和 Target Standard/Premium 可視化體驗撰寫器，則可以傳送來自多個可視化體驗撰寫器活動的內容，但從表單式工作流程只能傳送一個活動的內容。活動傳遞是使用下列決策流程決定:

1. 目標伺服器調用將帶有有關 [!DNL Target] 請求和URL。
1. 目標經典和標準抽取運行在該目標中的每個活動 [!DNL Target] 請求。
1. Target 會嘗試將訪客匹配到活動。

   如果訪客已在 A/B 測試或多變數測試中，則會將它們匹配到該測試中，直到它們轉換。如果他們先前在體驗鎖定目標活動中，則必須將他們再次匹配到該活動中。如果他們符合對象規則，則訪客會落入這些活動中並進入特定體驗。

1. 如果表單式活動有最高優先順序，則會傳回該活動內容，以及來自可視化體驗撰寫器活動中所有相符的活動內容。
1. 如果可視化體驗撰寫器活動有最高優先順序，則會傳回來自所有相符的可視化體驗撰寫器活動的內容，但不會傳回任何 Target Classic 或表單式 活動內容。

   在頁面上執行且來自所有活動的結果會計入並反映在報表中。

**範例**

如果您有兩個活動，一個定位在品牌搜尋關鍵字 Nike，而第二個定位在無品牌關鍵字 sneakers，則系統會先檢查這兩個活動的優先順序。如果 Nike 活動具有較高的優先順序，則會顯示該內容。同樣地，如果 sneakers 活動具有較高的優先順序，則會顯示其內容。

如果兩個已鎖定的目標活動有相同的優先順序，則會顯示最近檢視的活動。如果訪客是首次前往頁面，則顯示最近啟動的活動。

## 目標標準/高級表單編寫器，非全局 [!DNL Target] 請求 {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>此資訊也適用在 Target Classic 中建立的任何執行中的促銷活動。

如果您的公司使用 [!DNL Target] 除全局 [!DNL Target] 請求，每次調用只能返回一個活動的內容。 活動傳遞是使用下列決策流程決定:

1. 的 [!DNL Target] 伺服器呼叫來 [!DNL Target] 以及 [!DNL Target] 請求和URL。
1. [!DNL Target] 拉出每個運行的活動 [!DNL Target] 請求。
1. [!DNL Target] 嘗試匹配訪客和最高優先順序活動。

   如果訪客已在 A/B 測試或多變數測試中，則會將它們匹配到該測試中，直到它們轉換。如果他們先前在體驗鎖定目標活動中，則必須將他們再次匹配到該活動中。如果他們符合對象規則，則訪客會落入這些活動中並進入特定體驗。

1. 如果多個活動有相同的優先順序層級，則有兩個延長賽:

   * 如果只有一個活動有對象鎖定目標，則會顯示該活動。
   * 如果所有或全部均無鎖定目標，則顯示先核准的活動。

## 範例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>視您的設定而定，優先順序值會有所不同。您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。如需詳細資訊，請參閱[活動設定](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02)。

**兩個目標經典市場活動使用非全局目標請求**

* 行銷活動 1: homePageHero，offer1，優先順序高
* 行銷活動 2: homePageHero，offer2，優先順序低

回應: offer1

**兩個活動只使用可視化體驗撰寫器中建立的選件來配合不同的選取器**

* 活動 1: target-global-mbox, selector1, visualExpCompOffer1, 低優先順序
* 活動 2: target-global-mbox，selector2，visualExpCompOffer2，優先順序高

回應: visualExpCompOffer1, visualExpCompOffer2

**兩個活動只使用可視化體驗撰寫器中建立的選件來配合相同的選取器**

* 活動 1: target-global-mbox, selector1, visualExpCompOffer1, 低優先順序
* 活動 2: target-global-mbox，selector1，visualExpCompOffer2，優先順序高

回應: visualExpCompOffer1, visualExpCompOffer2

>[!NOTE]
>
>此回應與上面第二個使用案例中的回應相同，因為 Target Classic 不會處理選取器衝突。當選取器在 DOM 和視覺上可能衝突時，Target Standard 會攔截此行為和其他使用案例 (通常是在體驗編輯器層級上或行銷活動模擬模式下完成)。

**兩個活動使用可視化體驗撰寫器中選件及兩個 Target Classic 行銷活動**

* 活動 1: target-global-mbox，selector1，visualExpCompOffer1，中高
* 活動 2: target-global-mbox，selector2，visualExpCompOffer2，優先順序低
* 行銷活動 1: target-global-mbox，offer1，優先順序高
* 行銷活動 2: target-global-mbox，offer2，優先順序低

回應: offer1，visualExpCompOffer2，visualExpCompOffer1

>[!NOTE]
>
>合併回應的順序是傳統內容先出現 (僅支援一個傳統回應，如同使用案例 1 一樣)，然後是依顛倒優先順序排序的可視化體驗撰寫器選件回應。

## 訓練影片: 活動設定 (3: 02)

此影片包括關於活動設定的資訊。

* 輸入活動的目標
* 設定活動的優先順序層級
* 排程活動開始和結束時間
* 新增報表的對象，以建立報表篩選器
* 輸入活動的備註

>[!VIDEO](https://video.tv.adobe.com/v/17381)

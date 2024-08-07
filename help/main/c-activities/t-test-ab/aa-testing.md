---
keywords: a/b；a/a；aa；
description: 瞭解A/A測試是什麼、為何要執行A/A測試、應執行測試多久以及如何解讀結果。
title: 什麼是A/A測試？
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
source-git-commit: 4f0ebdd06287a438e519d9bccb677ab1a9093396
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 1%

---

# A/A 測試

使用[!DNL Adobe Target]在您的網站上執行A/A測試之前，請務必先瞭解A/A測試是什麼、為何要執行A/A測試、應執行測試多久以及如何解讀結果。

## 什麼是A/A測試？

在說明A/A測試之前，請先檢閱A/B測試，以便我們討論差異。

在標準A/B測試中，流量會分配給兩個或多個不同的體驗。 一種體驗通常是「控制」，會針對控制項測試體驗的變化，以檢視哪個體驗會在指定量度中建立最大的提升度。

然而，A/A測試涉及將流量分配給兩個相同的體驗，通常採用50/50流量分配分割。 使用標準A/B測試時，您通常想要探索轉換中的提升度。 這與A/A測試不同，您的目標通常是判斷相同體驗之間的提升度是否有&#x200B;*no*&#x200B;差異。

## 您為何要測試兩個相同的體驗，以及這會達成什麼目的？

某些組織在實作新的測試工具（例如[!DNL Target]）時執行A/A測試，以判斷：

* 活動已正確設定
* 程式碼已正確實作
* 報表準確

雖然很少有組織執行A/A測試，但實作工具之後或執行可能影響轉換和收入的A/B測試之前，最好將這些測試當做「正常」實驗來執行，以建立信任。

## 當體驗相同時，為何您可能看到某個體驗的提升度？

您可能會看到某個體驗比另一個（相同）體驗有提升度的原因有很多：

### 會持續監視A/A測試

執行任何型別的測試（包括A/A測試）時，常見的問題是持續檢視結果，並在您看到統計顯著性時過早停止測試，以及宣告成功體驗。 分析人員經常會進行「資料窺視」。 資料窺視包括及早及經常檢視測試資料，同時嘗試判斷哪些體驗的執行效能較佳。 風險是過早停止測試，這可能會導致結果失效。

在A/A測試中，資料窺視通常可導致分析師看到單一體驗中的提升度，但實際上應該沒有差異，因為兩個體驗是相同的。 事實上，在連續窺視的情況下，A/A測試在測試期間的某個時間點會有&#x200B;*保證*&#x200B;顯示「統計顯著性」（也就是高於特定臨界值的信賴度，例如95%）。

因此，為了避免此情況，以及在一般A/B測試中，您應該根據最小效果大小（低於此程度的效果對您的業務並不重要）、功率和顯著性等級，預先決定要使用的樣本大小。

在A/A測試中，目標為&#x200B;*不會*&#x200B;在您的測試達到所需的樣本大小後，看到統計顯著的結果。

[!UICONTROL Adobe Target Sample Size Calculator]是重要的工具，可協助您決定要瞄準的樣本大小以及測試執行的時間長度。

* [Adobe Target大小電腦](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

此外，請參閱下列文章以取得關於活動執行時間長短的資訊，以及其他實用秘訣和訣竅：

* [A/B 測試該執行多久？](/help/main/c-activities/t-test-ab/sample-size-determination.md)
* [十個常見的A/B陷阱和避免方法](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### 統計顯著性會影響測試結果

測試的顯著水準會決定測試報告兩個不同選件之間轉換率重大差異的可能性，而事實上並沒有實際差異。 這稱為誤判或Type I錯誤。 顯著水準是使用者指定的臨界值，而且在選擇適當顯著水準時，必須包含於測試中的誤判容許度與訪客數量之間會進行折衷。

A/A和A/B測試中常用的顯著水準是5%，這對應至95%的信賴水準（信賴水準= 100% — 顯著水準）。 95%的信賴度水準表示每次執行測試時，偵測統計顯著提升的機會為5%，即使體驗之間沒有差異亦然。

假設您想透過A/A測試達到95%的信賴水準。 在95%信賴水準下，20分之1的A/A測試可顯示轉換在統計上的顯著提升。 在90%信賴水準下，10分之一的測試在測試相同體驗時可顯示轉換的提升度。

## 最佳做法

如果您認為組織需要進行A/A測試，請注意，相同的體驗可能會暫時與控制項不同。 根據允許執行測試的時間，這可能是正常的。 假設有更多時間和訪客，差異應該會縮小。

最佳實務是使用一般A/B測試方法：使用[Adobe Target大小電腦](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)，根據最小的相關效果大小、所需功率和顯著性預先決定樣本大小。

接著，在得出任何結論之前，請留出充足的時間和訪客，同時請記住，根據測試的重要性層級，某個體驗可能會顯示提升度差異，甚至可能宣告獲勝者。

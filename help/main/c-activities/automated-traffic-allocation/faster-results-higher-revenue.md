---
keywords: 自動流量分配；鎖定目標；自動分配
description: 瞭解 [!DNL Adobe Target] 中的[!UICONTROL Auto Allocate]活動如何從兩個或多個體驗中識別獲勝者，並自動重新分配更多流量給獲勝者。
title: '[!UICONTROL Auto-Allocate]活動可以取得更快的結果和更高的收入嗎？'
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
source-git-commit: e9976135c46f6658030b07fce384364f0c9ff0ed
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# [!UICONTROL Auto-Allocate]提供比手動測試更快的測試結果和更高的收入

使用手動A/B活動時，您可能會失去轉換，因為您無法在活動完成前將成功體驗傳送給整個對象。 即使在您認識到某些體驗勝過其他體驗，以及活動必須執行其整個課程才能對獲勝者採取行動之後，您的流量分配仍會維持固定。

## 自動分配流量

如果您想要讓選項在活動中更頻繁且更早地提供成功體驗，同時移除或減少挑選樣本大小、信賴水準和其他統計概念的設定和計算成本，則[!UICONTROL Auto-Allocate]是您的最佳選項。

## [!UICONTROL Auto-Allocate]如何運作？

[!UICONTROL Auto-Allocate]使用多臂吃角子老虎機原則。 如果這個詞不熟悉，單臂吃角子老虎機就是老虎機的俗語（想想：拉斯維加斯）。 將流量的自動分配視覺化為擁有多部插槽機，在此案例中是測試變異，並在最初平等提取所有控點。 一段時間後，一台或多台電腦或測試變數可能會比其他電腦支付更多費用。 發生這種情況時，賭徒會自然而然地開始拉取勝利的把手。 在流量配置詞語中，[!DNL Target]會為更多訪客提供勝出更多的體驗或體驗。

請考量下列兩週A/B活動的圖例。 透過[!UICONTROL Auto-Allocate]，當成功體驗出現時，[!UICONTROL Target]會在測試初期將更多流量轉給該成功者。

![自動分配插圖](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## [!UICONTROL Auto-Allocate]如何提供更快的結果？

好處顯而易見：更多訪客會看到績效最佳的變數。 此外，由於單一變數領先時，會有更多訪客在測試仍在執行期間，被導向至勝出體驗。 如果執行的A/B活動發生在核心業務時刻（例如假日、產品上市或全球新聞事件），此方法特別實用。

## [!UICONTROL Auto-Allocate]如何提供更高的收入？

[!UICONTROL Auto-Allocate]比手動A/B分割更快找到獲勝者，也可讓您利用獲勝者立即擷取在傳統或手動方法中可能遺失的上行營收。 由於[!UICONTROL Auto-Allocate]會將更多流量導向轉換率最高的體驗，因此可在活動執行和學習時增加您的收入。

在下列範例中，[!UICONTROL Auto-Allocate]將更多流量(40%)推送至轉換率最高的體驗D，在測試期間獲得更多收入。

![自動分配提供較高的收入圖例](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## 在哪些情況下我應該堅持手動流量分配？

當您必須將每個體驗相對於其他體驗的執行方式排序時，手動A/B測試最適用。 [!UICONTROL Auto-Allocate]尋找並開發表現最佳的體驗，但不保證表現較差的體驗之間會有差異。 使用手動流量分配，以完全控制有多少訪客流量會看到每個測試變體，並自訂與您的業務相關的統計臨界值。

## 開始使用

準備好啟動您的第一個[!UICONTROL Auto-Allocate]活動嗎？ [在這裡瞭解如何操作](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。

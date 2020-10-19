---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: 手動輸入一或多個靜態值，以使用Adobe Target Recommendations中的包含規則進行篩選。
title: 依Adobe Target Recommendations中包含規則中的靜態值篩選
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 75%

---


# ![PREMIUM](/help/assets/premium.png) Static Filter

手動輸入一或多個靜態值，以使用Adobe Target Recommendations中的包含規則進行篩選。

例如，僅建議 MPAA 評等為 &quot;G&quot; 或 &quot;PG&quot; 的內容。

可用運算子：

* 等於
* 不等於
* 包含
* 不包含
* 開始於
* 終止於
* 值存在
* 值不存在
* 大於或等於
* 小於或等於

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版 (2017 年 6 月) 之前包含規則的設定方式，您將注意到一些選項和運算子已變更。只會顯示適用於所選取選項的那些運算子，而一些運算子已重新命名 (「符合」現在是「等於」)，以便更為一致且直覺。在此版本之前建立的所有現有排除規則皆已自動移轉至新結構。您不需要重新處理結構。

您可以視需要建立許多包含規則。包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。
---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: 手動輸入一或多個靜態值，以使用Adobe Target Recommendations中的包含規則進行篩選。
title: 依Adobe Target Recommendations中包含規則中的靜態值篩選
feature: criteria
translation-type: tm+mt
source-git-commit: f8311dbc91b74977a11dc9b97a70465ab4493b93
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 48%

---


# ![PERTIMtatic](/help/assets/premium.png) 篩選

手動輸入一個或多個靜態值，以使用[!DNL Adobe Target] [!DNL Recommendations]中的包含規則進行篩選。

例如，僅建議內容的「動態圖片關聯」(MPA)評分為「G」或「PG」。

您可以視需要建立許多包含規則。包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版 (2017 年 6 月) 之前包含規則的設定方式，您將注意到一些選項和運算子已變更。只會顯示適用於所選取選項的那些運算子，而一些運算子已重新命名 (「符合」現在是「等於」)，以便更為一致且直覺。在此版本之前建立的所有現有排除規則皆已自動移轉至新結構。您不需要重新處理結構。

## 建議評等為G或PG的內容

若要建立含靜態值的包含規則，以建議MPA分級為「G」或「PG」的內容（排除「R」和「NC17」內容），您可以建立下列篩選規則：「影片分級等於g-aradied」和「影片分級等於pg-aradied」，如下所示。

![影片評分範例](/help/c-recommendations/c-algorithms/assets/movies.png)


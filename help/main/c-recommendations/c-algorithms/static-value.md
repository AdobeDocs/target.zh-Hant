---
keywords: 包含規則；包含條件；建議；升級；動態過濾；靜態過濾；inclusion rules;inclusion criteria;recommendations;promotions;dynamic filtering;static filter
description: 瞭解如何使用Adobe中的包含規則手動輸入一個或多個靜態值以篩選 [!DNL Target] Recommendations。
title: 如何按Recommendations活動中的靜態值篩選？
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 46%

---

# ![高級](/help/main/assets/premium.png) 靜態篩選器

手動輸入一個或多個靜態值以使用中的包含規則進行篩選 [!DNL Adobe Target] [!DNL Recommendations]。

例如，僅推薦「G」或「PG」等級為「Motion Picture Association(MPA)」的內容。

您可以視需要建立許多包含規則。包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版 (2017 年 6 月) 之前包含規則的設定方式，您將注意到一些選項和運算子已變更。只會顯示適用於所選取選項的那些運算子，而一些運算子已重新命名 (「符合」現在是「等於」)，以便更為一致且直覺。在此版本之前建立的所有現有排除規則皆已自動移轉至新結構。您不需要重新處理結構。

## 推薦分級為G或PG的內容

要建立包含規則，其中包含靜態值，以推薦MPA分級為「G」或「PG」的內容（僅排除「R」和「NC17」內容），可以建立以下篩選規則：「電影分級為g分級」和「電影分級為等pg分級」，如下所示。

![電影分級示例](/help/main/c-recommendations/c-algorithms/assets/movies.png)

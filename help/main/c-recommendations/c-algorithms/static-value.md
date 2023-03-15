---
keywords: 包含規則；包含條件；建議；促銷活動；動態篩選；靜態篩選
description: 了解如何手動輸入一或多個靜態值，以使用Adobe中的包含規則來篩選 [!DNL Target] Recommendations。
title: 如何依Recommendations活動中的靜態值篩選？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 47%

---

# 靜態篩選器

手動輸入一或多個靜態值，以使用 [!DNL Adobe Target] [!DNL Recommendations].

例如，僅建議動作圖片關聯(MPA)評等為&quot;G&quot;或&quot;PG&quot;的內容。

您可以視需要建立許多包含規則。包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版 (2017 年 6 月) 之前包含規則的設定方式，您將注意到一些選項和運算子已變更。只會顯示適用於所選取選項的那些運算子，而一些運算子已重新命名 (「符合」現在是「等於」)，以便更為一致且直覺。在此版本之前建立的所有現有排除規則皆已自動移轉至新結構。您不需要重新處理結構。

## 建議分級為G或PG的內容

若要建立包含規則，其中包含靜態值，以建議MPA評等為「G」或「PG」（僅排除「R」和「NC17」內容）的內容，您可以建立下列篩選規則：「電影評等為g-aged」和「電影評等為pg-aged」，如下所示。

![電影分級示例](/help/main/c-recommendations/c-algorithms/assets/movies.png)

---
keywords: 包含規則；包含條件；建議；促銷活動；促銷活動；動態篩選；靜態；靜態篩選
description: 瞭解如何在Adobe [!DNL Target] Recommendations中手動輸入一或多個靜態值，以使用包含規則進行篩選。
title: 如何在Recommendations活動中依靜態值篩選？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 45%

---

# [!UICONTROL Static Filter]

手動輸入一個或多個靜態值，以使用[!DNL Adobe Target Recommendations]中的包含規則進行篩選。

例如，僅建議電影協會(MPA)評等為&quot;G&quot;或&quot;PG&quot;的內容。

您可以視需要建立許多包含規則。包含規則是以 AND 運算子來結合。必須符合所有規則，才能在建議中納入某個項目。

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版 (2017 年 6 月) 之前包含規則的設定方式，您將注意到一些選項和運算子已變更。只會顯示適用於所選取選項的那些運算子，而一些運算子已重新命名 (「符合」現在是「等於」)，以便更為一致且直覺。在此版本之前建立的所有現有排除規則皆已自動移轉至新結構。您不需要重新處理結構。

## 推薦分級為G或PG的內容

若要使用靜態值建立包含規則，以僅建議MPA評等為「G」或「PG」的內容（排除「R」和「NC17」內容），您可以建立下列篩選規則：「電影評等等於任何g評等」以及「電影評等等於任何pg評等」。

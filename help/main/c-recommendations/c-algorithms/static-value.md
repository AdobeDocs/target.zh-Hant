---
keywords: 包含規則；包含條件；建議；促銷活動；促銷活動；動態篩選；靜態；靜態篩選
description: 瞭解如何在Adobe [!DNL Target] Recommendations中手動輸入一或多個靜態值，以使用包含規則進行篩選。
title: 靜態篩選器
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
TQID: 'https://experienceleague.adobe.com/-HTJO4YFi0-isyA-5LbVUaEPu7YX1WFgPy-OexMSXFY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 2%
---
# 靜態篩選器 {#static-filter}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在[!DNL Adobe Target Recommendations]的包含規則中手動輸入一或多個靜態值，以篩選建議。

>[!ENDSHADEBOX]

**[!UICONTROL 靜態篩選器]**&#x200B;將建議中的專案限製為符合手動輸入之靜態值的專案。 可建立任意數量的包含規則。 包含規則會使用AND運運算元連結，因此必須符合所有規則，才會將專案包含在建議中。 如需包含規則的一般資訊，請參閱[使用動態和靜態包含規則](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)。

## 推薦分級為G或PG的內容

若只要建議電影協會(MPA)評等為&quot;G&quot;或&quot;PG&quot;的內容（不包括&quot;R&quot;和&quot;NC17&quot;內容），請建立一個篩選規則，其運運算元為&quot;movie-rating equals any of&quot;，並輸入&quot;g-rated&quot;和&quot;pg-rated&quot;值。

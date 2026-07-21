---
title: 在對象規則中使用內容
description: 瞭解如何在對象規則中使用內容屬性，以取得標籤中的功能標籤和功能群組。
hide: true
exl-id: 0367f475-9209-4d53-86b4-a739a73a23a7
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# 在對象規則中使用內容 {#context-in-audience-rules}

內容屬性是使用者端應用程式在執行階段提供的值。 它們可讓您根據動態的工作階段層級資訊來鎖定使用者，例如使用者的作用中語言、裝置型別或應用程式狀態。

內容屬性與Web和行動使用者端相關。

## 內容屬性的運作方式 {#how-context-attributes-work}

評估功能標幟時，您的應用程式會將內容屬性傳遞給「標幟」。 您可以在主控台中定義規則來檢查這些值，平台會在評估時使用它們來判斷使用者是否符合條件。

## 新增內容屬性 {#adding-context-attribute}

若要將內容屬性新增至對象規則：

1. 在主控台中開啟功能標幟或功能群組。
2. 前往&#x200B;**對象**&#x200B;標籤。
3. 在&#x200B;**內容**&#x200B;下，新增條件。
4. 選取內容屬性、運運算元和值。

如果您需要的內容屬性未出現在清單中，您可以建立新的內容屬性 — 請參閱[建立您的內容屬性](creating-your-context-attributes.md)。

## 另請參閱 {#see-also}

* [功能標幟和功能群組中的對象](audience-in-feature-flags-and-feature-groups.md)

<!-- -->

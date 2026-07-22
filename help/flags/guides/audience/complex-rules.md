---
title: 複雜的受眾規則
description: 瞭解如何在旗標中使用大型或複雜的受眾規則集，包括大量值限制以及如何跨多個條件分割規則。
badge: label="Beta" type="Informative"
hide: true
exl-id: 37e037b6-45eb-4261-b580-30d94d8e55da
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 3%

---

# 複雜的受眾規則 {#complex-rules}

## 對複雜規則使用巢狀邏輯 {#nested-logic}

巢狀邏輯可讓您結合多個對象條件與精確的AND/OR控制項。 若要啟用此功能：

1. 新增您需要的對象條件。
2. 在對象規則區段中啟用&#x200B;**巢狀邏輯**。
3. 每個條件都會指定一個數字。 輸入參照這些數字的邏輯運算式，例如：
   * `1 and (2 or 3)`
   * `(1 and 2) or 3`
   * `(1 and 2) or (3 and 4)`

## 另請參閱 {#see-also}

* [功能標幟和功能群組中的對象](audience-in-feature-flags-and-feature-groups.md)

<!-- -->

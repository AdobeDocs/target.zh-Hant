---
keywords: 包含規則；包含條件；建議；促銷；動態過濾；動態過濾；profile屬性匹配
description: 瞭解如何在Adobe中動態篩選 [!DNL Target] Recommendations，將項目（實體）與用戶配置檔案中的值進行比較。
title: 如何按配置檔案屬性匹配篩選Recommendations活動？
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 6%

---

# ![高級](/help/main/assets/premium.png) 配置檔案屬性匹配

動態篩選 [!DNL Adobe Target] [!DNL Recommendations] 將項目（實體）與用戶配置檔案中的值進行比較。

使用 [!UICONTROL 配置檔案屬性匹配] 當要顯示與訪問者配置檔案中儲存的值匹配的建議時，例如大小或收藏夾品牌。

>[!NOTE]
>
>的 [建立和使用包含規則的流程](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) 標準和促銷與使用案例和示例相似。

以下方案顯示如何使用 [!UICONTROL 配置檔案屬性匹配]:

* 一家銷售眼鏡的公司，把遊客最喜歡的框顏色當成「胡桃」。 對於該特定訪問者，建議僅返回與彩色「核桃木」匹配的眼鏡框。
* 可以為訪問者瀏覽公司網站時的服裝尺寸（例如，小、中或大）定義配置檔案參數。 可以設定推薦以匹配該輪廓參數並返回僅針對用戶優選服裝尺寸的產品。

## 配置檔案屬性匹配示例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 配置檔案屬性匹配] 允許您僅推薦與訪問者配置檔案中的屬性匹配的項目，如下例所示。

### 從用戶最喜愛的品牌推薦項目

例如，您可以使用 [!UICONTROL 配置檔案屬性匹配] 選項，建立只推薦品牌等於儲存在 `profile.favoritebrand`。 透過此規則，如果訪客在查看特定品牌的慢跑短褲，則只有符合使用者最喜愛品牌 (訪客設定檔中 `profile.favoritebrand` 內儲存的值) 的建議才會出現。

![最喜愛的品牌](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 將工作與求職者匹配

假設你試圖將工作與求職者相匹配。 你只想推薦那些與求職者在同一個城市的工作。

您可以使用包含規則將求職者的位置從其訪問者的個人資料與職務清單相匹配，如下例所示：

![用戶所在城市](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根據大小推薦項目

有關配置檔案屬性匹配如何影響建議的可視示例，請考慮一個銷售電風扇的網站。

當訪問者點擊此網站上的各種粉絲影像時，每個頁面都會設定 `entity.size` 參數，其值取決於影像中風扇的大小是小還是大。

假設您建立了配置檔案指令碼來跟蹤和計數 `entity.size` 設定為小而大。

如果訪問者隨後返回首頁，他或她將看到過濾後的建議，這些建議基於是否點擊了更多小粉絲或大粉絲。

Recommendations網站上的小粉絲數量增加：

![小風扇建議](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations網站上的粉絲數量更多：

![大風扇建議](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)

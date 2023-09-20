---
keywords: 體驗鎖定目標; XT; 量度; 設定量度; 目標量度; 活動設定; 成功量度; 轉換; 收入; 參與
description: 瞭解如何在 [!DNL Adobe Target] [!UICONTROL 體驗鎖定] 用於判斷造訪是否成功的活動，例如 [!UICONTROL 轉換]， [!UICONTROL 收入]，或 [!UICONTROL 參與].
title: 如何在設定目標量度 [!UICONTROL 體驗鎖定] 活動？
feature: Experience Targeting
exl-id: 16249930-8b9c-441c-bd14-5f32332556d2
source-git-commit: d7c1bbbbc8d1dcc45ac09a09f6b3be01f7542384
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 57%

---

# 在中設定量度 [!UICONTROL 體驗鎖定] (XT)活動

在中使用量度 [!DNL Adobe Target] [!UICONTROL 體驗鎖定] (XT)活動，用於判斷造訪是否成功。

如需成功量度的詳細資訊，請參閱 [成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. 指定活動的目標。
1. 選取[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

   ![選取成功量度](/help/main/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   此 [!UICONTROL 選取量度] 頁面列出您可為活動選擇的成功度量。 成功量度可分為下列類別:

   * [!UICONTROL 轉換]
   * [!UICONTROL 收入]
   * [!UICONTROL 參與]

   您可以使用任何預先建立的成功量度，也可以建立自訂成功量度。 您也可以將成功量度標示為主要量度。報表和 Experience Cloud 卡預設會顯示主要量度 (如果有設定的話)。
1. 指定量度的設定。

   可用的設定取決於您使用的成功量度。

   如果已啟用， [!UICONTROL 轉換的預計值] 欄位(不適用於 [!UICONTROL 頁面分數] 量度)為您的目標提供值。 此值可讓 [!DNL Target] 計算收入中預估的提升度。此欄位為可選; 不過，任何非收入量度的遞增收入若沒有它即無法計算。資料類型為貨幣。此欄位會在使用者指出滿足目標所採取的動作之後逐漸顯示。請參閱[預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。

   成功量度的正確組態對於確保您可取得預期的資料來說很重要。

   如需詳細資訊，請參閱[成功度量](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

1. (可選) 增加額外的量度。
1. 完成量度的設定時，請按一下&#x200B;**[!UICONTROL 「繼續」]**。

為量度命名或重新命名時，不得使用下列字元：

| 字元 | 說明 |
|--- |--- |
| `/` | 正斜線 |
| `?` | 問號 |
| `#` | 數字符號 |
| `:` | 冒號 |
| `=` | 等號 |
| `+` | 加號 |
| `-` | 減號 |
| `@` | 「@」符號 |

## 訓練影片: 活動量度 (7:43) ![Tutorial badge](/help/main/assets/tutorial.png)

此影片包括關於使用成功量度的資訊。

* 瞭解「目標」量度
* 瞭解並建置 [!UICONTROL 轉換]， [!UICONTROL 收入]、和 [!UICONTROL 參與] 量度
* 建置點擊追蹤量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)

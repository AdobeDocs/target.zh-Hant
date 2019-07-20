---
description: 在 A/B 活動中使用量度以判斷造訪是否成功。
keywords: A/B; 活動量度; 量度; 設定量度; 目標量度; 活動設定; 成功量度; 轉換; 收入; 參與
seo-description: 在 A/B 活動中使用量度以判斷造訪是否成功。
seo-title: 設定量度
solution: Target (Standard)
title: 設定量度
uuid: 57f84da4-10f9-42f3-b9ce-06cf41007157
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 設定量度{#set-metrics}

在 A/B 活動中使用量度以判斷造訪是否成功。

如需關於成功量度的詳細資訊，請參閱[成功量度](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

1. 指定活動的目標。
1. 選取[成功量度](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

   ![選取成功量度](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_metrics-new.png)

   [!UICONTROL 「選取量度」]頁面會列出您可以為活動選擇的成功量度。成功量度可分為下列類別:

   * 轉換
   * 收入
   * 參與
   您可以使用任何預先建置的成功量度，或是建立自訂成功量度。您也可以將成功量度標示為主要量度。報表和 Experience Cloud 卡預設會顯示主要量度 (如果有設定的話)。
1. 指定量度的設定。

   可用的設定取決於您使用的成功量度。

   如果已啟用，[!UICONTROL 「轉換的預計值」]欄位 (「頁面分數」量度無法使用) 可提供目標的值。此值可讓 Target 計算收入中預估的提升度。此欄位為可選; 不過，任何非收入量度的遞增收入若沒有它即無法計算。資料類型為貨幣。此欄位會在使用者指出滿足目標所採取的動作之後逐漸顯示。請參閱[預估收入中的提升度](../../../administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md#concept_32F875D8F91349CE86AF391F65BEAEEE)以取得詳細資訊。

   成功量度的正確組態對於確保您可取得預期的資料來說很重要。

   如需詳細資訊，請參閱[成功度量](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。
1. (可選) 增加額外的量度。
1. 完成量度的設定時，請按一下&#x200B;**[!UICONTROL 「繼續」]**。

請注意，為量度命名或重新命名時，不得使用下列字元:

| 字元 | 說明 |
|--- |--- |
| / | 正斜線 |
| ? | 問號 |
| # | 數字符號 |
| : | 冒號 |
| = | 等號 |
| + | 加號 |
| - | 減號 |
| @ | 「@」符號 |

## 訓練影片: 活動量度 (7:43)

此影片包括關於使用成功量度的資訊。

* 瞭解「目標」量度
* 瞭解和建置轉換、收入和參與量度
* 建置點擊追蹤量度

>[!VIDEO](https://video.tv.adobe.com/v/17380?captions=chi_hant)

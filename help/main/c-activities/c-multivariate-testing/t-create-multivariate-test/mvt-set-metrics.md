---
keywords: 多變數; MVT; 量度; 設定量度; 目標量度; 活動設定; 成功量度; 轉換; 收入; 參與
description: 瞭解如何在 [!DNL Adobe Target] [!UICONTROL Multivariate Test]活動中指定量度，以判斷造訪是否成功，例如[!UICONTROL Conversion]、[!UICONTROL Revenue]和[!UICONTROL Engagement]。
title: 如何在[!UICONTROL Multivariate Test] (MVT)活動中設定目標量度？
feature: Multivariate Tests
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 60%

---

# 設定[!UICONTROL Multivariate Test]活動的量度

在[!DNL Adobe Target] [!UICONTROL Multivariate Test]中使用量度以判斷造訪是否成功。

如需成功量度的詳細資訊，請參閱[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

1. 指定活動的目標。
1. 選取[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

   ![設定量度清單](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list-new.png)

   [!UICONTROL Select Metrics]頁面列出您可為活動選擇的成功量度。 成功量度可分為下列類別:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   您可以使用任何預先建置的成功量度，或是建立自訂成功量度。您也可以將成功量度標示為主要量度。報表和 Experience Cloud 卡預設會顯示主要量度 (如果有設定的話)。

1. 指定量度的設定。

   可用的設定取決於您使用的成功量度。

   如果已啟用，[!UICONTROL Estimated Value of the Conversion]欄位（[!UICONTROL Page Score]量度無法使用）可提供目標的值。 此值可讓 [!DNL Target] 計算收入中預估的提升度。此欄位為可選; 不過，任何非收入量度的遞增收入若沒有它即無法計算。資料類型為貨幣。此欄位會在使用者指出滿足目標所採取的動作之後逐漸顯示。請參閱[預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。

   成功量度的正確組態對於確保您可取得預期的資料來說很重要。

   如需詳細資訊，請參閱[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

1. (可選) 增加額外的量度。
1. 完成量度的設定時，請按一下&#x200B;**[!UICONTROL Save and Close]**。

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

## 訓練影片：活動量度(7:43) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用成功量度的資訊。

* 瞭解「目標」量度
* 瞭解並建置[!UICONTROL Conversion]、[!UICONTROL Revenue]和[!UICONTROL Engagement]量度
* 建置點擊追蹤量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)

---
keywords: A/B; 活動量度; 量度; 設定量度; 目標量度; 活動設定; 成功量度; 轉換; 收入; 參與
description: 探索如何在A/B活動中設定量度以判斷造訪成功，包括[!UICONTROL 轉換]、[!UICONTROL 收入]和[!UICONTROL 參與]。
title: 如何在A/B活動中設定目標量度？
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
TQID: https://experienceleague.adobe.com/WE27AidwrwYLn-ZlnpxKNfOG2jT07iPYztdrovRl0Qk
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 305
ht-degree: 55%

---

# 設定量度

在[!DNL Adobe Target] A/B活動中使用量度以判斷造訪是否成功。

如需成功量度的詳細資訊，請參閱[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

1. 在&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面的&#x200B;**[!UICONTROL 報告設定]**&#x200B;區段中，選取[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

   [!UICONTROL 選取量度]選項會列出您可為活動選擇的成功量度。 成功量度可分為下列類別:

   * [!UICONTROL 轉換]
   * [!UICONTROL 收入]
   * [!UICONTROL 參與]

   您可以使用任何預先建置的成功量度，或是建立自訂成功量度。 您也可以將成功量度標示為主要量度。 報表和 Experience Cloud 卡預設會顯示主要量度 (如果有設定的話)。

1. 指定量度的設定。

   可用的設定取決於您使用的成功量度。

   如果已啟用，[!UICONTROL 轉換的預計值]欄位（[!UICONTROL 頁面分數]量度無法使用）可提供目標的值。 此值可讓 [!DNL Target] 計算收入中預估的提升度。 此欄位為可選; 不過，任何非收入量度的遞增收入若沒有它即無法計算。 資料類型為貨幣。 此欄位會在使用者指出滿足目標所採取的動作之後逐漸顯示。 請參閱[預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。

   成功量度的正確設定是確保您取得預期資料的關鍵。

   如需詳細資訊，請參閱[成功度量](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

1. (可選) 增加額外的量度。

為量度命名或重新命名時，不得使用下列字元：

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

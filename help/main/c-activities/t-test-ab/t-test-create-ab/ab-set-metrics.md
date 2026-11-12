---
keywords: A/B; 活動量度; 量度; 設定量度; 目標量度; 活動設定; 成功量度; 轉換; 收入; 參與
description: 探索如何在A/B、體驗鎖定目標或多變數測試活動中設定量度以判斷造訪成功，包括[!UICONTROL 轉換]、[!UICONTROL 收入]和[!UICONTROL 參與]。
title: 如何在A/B活動中設定目標量度？
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
TQID: 'https://experienceleague.adobe.com/WE27AidwrwYLn-ZlnpxKNfOG2jT07iPYztdrovRl0Qk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: c87804d95464cc31658be23bc7de051c6e1bc12e
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 24%
---
# 設定量度 {#ab-set-metrics}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何設定A/B、體驗鎖定目標(XT)或多變數測試(MVT)活動的目標量度和其他量度，以及量度名稱中不允許哪些字元。

>[!ENDSHADEBOX]

在[!DNL Adobe Target] A/B、[!UICONTROL 體驗鎖定目標] (XT)或[!UICONTROL 多變數測試] (MVT)活動中使用量度以判斷造訪是否成功。 如需成功量度的詳細資訊，請參閱[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#overview)。

>[!NOTE]
>
>此頁面適用於[!DNL Adobe Target]為報表來源時。 若為其他報表來源，請參閱[[!DNL Adobe Analytics] 作為 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) and [[!DNL Target] 報表的報表來源。

## 設定量度 {#set-a-metric}

1. 在&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面的&#x200B;**[!UICONTROL 報告設定]**&#x200B;區段中，選取[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#overview)。

   **[!UICONTROL 選取量度]**&#x200B;選項會列出您可為活動選擇的成功量度。 成功量度可分為下列類別:

   * **[!UICONTROL 轉換]**
   * **[!UICONTROL 收入]**
   * **[!UICONTROL 參與]**

   您可以使用任何預先建置的成功量度，或是建立自訂成功量度。 您也可以將成功量度標示為主要量度。 報表和 Experience Cloud 卡預設會顯示主要量度 (如果有設定的話)。

   ![](../../assets/metric-1.png)

1. 指定量度的設定。 可用的設定取決於您使用的成功量度。

1. 如果已啟用，**[!UICONTROL 轉換的預計值]**&#x200B;欄位會提供目標的值：

   * 此值可讓[!DNL Target]計算收入的預估提升度。
   * 欄位是選用欄位；但是，沒有它就無法計算任何非收入量度的增量收入。
   * 此欄位不適用於&#x200B;**[!UICONTROL 頁面分數]**&#x200B;量度。
   * 資料類型為貨幣。
   * 當使用者指出為達到目標而採取的動作後，欄位會逐步顯示。

   請參閱[預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。 成功量度的正確設定是確保您取得預期資料的關鍵。

   ![](../../assets/metric-2.png)

1. （選擇性）若要追蹤超過目標量度的專案，請按一下&#x200B;**[!UICONTROL 新增量度]**，然後選取並設定每個額外的量度，如先前步驟所述。

1. 完成量度的設定後，請在XT活動中按一下&#x200B;**[!UICONTROL 繼續]**，或在MVT活動中按一下&#x200B;**[!UICONTROL 儲存並關閉]**。

## 量度名稱中不允許字元 {#metric-name-rules}

![](../../assets/metric-3.png)

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

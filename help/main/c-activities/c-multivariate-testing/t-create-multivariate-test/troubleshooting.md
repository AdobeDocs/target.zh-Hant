---
keywords: 多變數測試；疑難排解；疑難排解； MVT
description: 探索您在[!DNL Adobe Target]中使用[!UICONTROL 多變數測試] (MVT)活動時可能遇到的挑戰，以及建議的解決方案。
title: 如何疑難排解[!UICONTROL 多變數測試]？
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
TQID: 'https://experienceleague.adobe.com/O9lmC1PmICPCOxcMDYVcSdpRoM-bqwKR-79deFIG2mg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 21%
---
# 疑難排解[!UICONTROL 多變數測試]活動

本文包含的一些建議可用來解決在[!DNL Adobe Target]中設計[!UICONTROL 多變數測試] (MVT)時可能會發生的一些問題。

* 編輯活動時，如果您使用[!DNL Analytics]型量度，但報表套裝未載入（顯示旋轉圖示），請將量度切換為[!DNL Target]量度，然後再切換為[!DNL Analytics]型量度。 報表套裝現在應該會載入。
* 如果您變更已執行的測試，可能會重設測試及其資料。

  [!DNL Target]可讓您編輯已上線的活動。 編輯進行中的活動可能會重設測試，因此報表可能無法識別某些變更。

  進行少量變更則很安全，例如編輯現有文字或 html 產品建議。

  重設體驗名稱和報表的特定動作包括：

  * 新增位置
  * 刪除位置
  * 新增產品建議或從現有位置刪除產品建議

---
keywords: Multivariate Tests;troubleshoot;troubleshooting;mvt
description: 本主題包含解決在Adobe Target中設計MVT測試時可能發生之問題的建議。
title: 疑難排解多變數測試
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 45%

---


# 疑難排解多變數測試

本主題包含解決在[!DNL Adobe Target]中設計[!UICONTROL 多變數](MVT)測試時可能發生的問題的建議。

* 編輯活動時，如果您使用[!DNL Analytics]型度量且報表套裝未載入（微調按鈕顯示），請將量度切換為[!DNL Target]型度量，然後再次切換為[!DNL Analytics]型度量。 報表套裝現在應該會載入。
* 如果您變更已執行的測試，則可重設測試及其資料。

   [!DNL Target] 可讓您編輯即時活動。請注意，編輯進行中的活動可能會重設測試，因此報表可能無法辨識部分變更。

   進行少量變更則很安全，例如編輯現有文字或 html 選件。

   重設體驗名稱和報表的特定動作為:

   * 新增位置
   * 刪除位置
   * 新增選件或從現有位置刪除選件


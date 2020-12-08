---
keywords: Mobile Web Experience Editor
description: 本主題包含解決在Adobe Target中設計MVT測試時可能發生之問題的建議。
title: 疑難排解多變數測試
feature: mvt
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 77%

---


# 疑難排解多變數測試{#troubleshoot-multivariate-tests}

本主題包含解決在Adobe Target中設計MVT測試時可能發生之問題的建議。

* 編輯活動時，如果您使用 Analytics 型量度，而報表套裝未載入 (顯示進度環)，請將量度切換至 Target 量度，然後再次切換至 Analytics 型量度。報表套裝現在應該會載入。
* 如果對已在執行的測試進行變更，您可能會重設測試及其資料。

   Target 可讓您編輯即時活動。請注意，編輯進行中的活動可能會重設測試，因此報表可能無法辨識部分變更。

   進行少量變更則很安全，例如編輯現有文字或 html 選件。

   重設體驗名稱和報表的特定動作為:

   * 新增位置
   * 刪除位置
   * 新增選件或從現有位置刪除選件


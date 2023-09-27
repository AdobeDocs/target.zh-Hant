---
keywords: 多變數測試；疑難排解；疑難排解； MVT
description: 探索您在使用時可能面臨的潛在挑戰 [!UICONTROL 多變數測試] 中的(MVT)活動 [!DNL Adobe Target]，以及建議的解決方案。
title: 如何疑難排解 [!UICONTROL 多變數測試]？
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 21%

---

# 疑難排解 [!UICONTROL 多變數測試] 活動

本文包含的一些建議可用來解決設計時可能會發生的一些問題。 [!UICONTROL 多變數測試] (MVT)輸入 [!DNL Adobe Target].

* 編輯活動時，如果您已使用 [!DNL Analytics] — 型量度且報表套裝未載入（顯示旋轉圖示），請將量度切換為 [!DNL Target] 量度，然後再次切換到 [!DNL Analytics]以量度為基礎。 報表套裝現在應該會載入。
* 如果您變更已執行的測試，可能會重設測試及其資料。

  [!DNL Target] 可讓您編輯已上線的活動。 編輯進行中的活動可能會重設測試，因此報表可能無法識別某些變更。

  進行少量變更則很安全，例如編輯現有文字或 html 選件。

  重設體驗名稱和報表的特定動作包括：

   * 新增位置
   * 刪除位置
   * 新增選件或從現有位置刪除選件

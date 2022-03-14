---
keywords: 多元Test；疑難解答；mvt
description: 探索在Adobe Target使用多元Test(MVT)活動時可能面臨的潛在挑戰以及建議的解決方案。
title: 如何診斷多元Test?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 42%

---

# 疑難排解多變數測試

本主題包含一些建議，用於解決設計 [!UICONTROL 多元] (MVT)test [!DNL Adobe Target]。

* 編輯活動時，如果使用 [!DNL Analytics]-based度量且報告套件不載入（spinner顯示），將度量切換到 [!DNL Target] 然後再次切換到 [!DNL Analytics] — 基於度量。 報表套裝現在應該會載入。
* 如果對已運行的test進行更改，則可能會重置test及其資料。

   [!DNL Target] 允許您編輯即時活動。 請注意，編輯進行中的活動可能會重設測試，因此報表可能無法辨識部分變更。

   進行少量變更則很安全，例如編輯現有文字或 html 選件。

   重設體驗名稱和報表的特定動作為:

   * 新增位置
   * 刪除位置
   * 新增選件或從現有位置刪除選件

---
keywords: 多變數測試；疑難排解；疑難排解； mvt
description: 探索您在Adobe Target中使用多變數測試(MVT)活動時可能遇到的挑戰，以及建議的解決方案。
title: 如何疑難排解多變數測試？
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 42%

---

# 疑難排解多變數測試

本主題包含一些建議，可協助您解決在設計 [!UICONTROL 多變數] (MVT)測試於 [!DNL Adobe Target].

* 編輯活動時，如果您使用 [!DNL Analytics] — 型量度且報表套裝未載入（顯示旋轉圖示），請將量度切換為 [!DNL Target] 量度，然後再次切換到 [!DNL Analytics]以為基礎的量度。 報表套裝現在應該會載入。
* 如果您變更已執行的測試，可能會重設測試及其資料。

   [!DNL Target] 可讓您編輯已上線的活動。 請注意，編輯進行中的活動可能會重設測試，因此報表可能無法辨識部分變更。

   進行少量變更則很安全，例如編輯現有文字或 html 選件。

   重設體驗名稱和報表的特定動作為:

   * 新增位置
   * 刪除位置
   * 新增選件或從現有位置刪除選件

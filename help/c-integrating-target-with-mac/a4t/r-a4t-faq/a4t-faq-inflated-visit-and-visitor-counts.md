---
keywords: faq;常見問題集;analytics for target;a4T;膨脹;造訪;訪客;部分點擊;孤立的;孤立
description: 使用Analytics for [!DNL Target] (A4T)時，尋找有關誇大瀏覽和訪客計數的問題解答。 瞭解如何將「部分資料」減到最低。
title: 我可以在哪裡找到有關A4T誇大瀏覽和訪客計數的常見問答集？
feature: 目標分析 (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 61%

---

# 膨脹的造訪和訪客計數 - A4T 常見問題集

此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於膨脹後造訪和訪客計數問題的回答。

## 我的 Analytics 資料為何顯示沒有頁面檢視或其他變數值的造訪? {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

當[!DNL Adobe Analytics]用於測量[!DNL Target]活動（稱為A4T）時，[!DNL Analytics]會收集頁面上沒有[!DNL Target]活動時無法使用的資料。 這是因為 [!DNL Target] 活動會在頁面頂端觸發呼叫，但是 [!DNL Analytics] 一般是在頁面底部觸發其資料收集呼叫。在A4T至今的實作中，當[!DNL Target]活動處於活動狀態時，Adobe會包含此附加資料。

如需詳細資訊，請參閱[在 A4T 中將膨脹後造訪和訪客計數最小化](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 什麼是局部資料點閱? {#section_59A203E289564576BF6821F96B0B9E11}

當頁面頂端的 [!DNL Target] 標記觸發，但頁面底部的 [!DNL Analytics] 標記沒有觸發時，即會發生局部資料點閱。這種情況發生的原因有很多。 在至今的[!DNL A4T]實作中，當[!DNL Target]活動處於活動狀態時，Adobe會包含這些點擊的部分資料。 今後，Adobe將僅在[!DNL Target]和[!DNL Analytics]標籤都已引發時，才會包含此額外資料。

如需詳細資訊，請參閱[在 A4T 中將膨脹後造訪和訪客計數最小化](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 我看到造訪次數激增。如何判斷這些瀏覽是否是部分資料點擊造成的？{#section_28506672C6224ED18AC74F6A02F6F811}

您可以聯絡 [Adobe 客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以擷取「部分資料」報表。[!DNL Analytics] UI 中不直接提供這項資訊。

## 局部資料點閱可能有哪些原因? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

局部資料點閱通常是實作不當造成，例如報表套裝 ID 不對稱。也有合理的原因，包括頁面緩慢、頁面錯誤、活動中的重新導向選件，或程式庫版本太舊。

如需詳細資訊，請參閱以下的「造成局部資料的原因」:[在A4T 中將膨脹後造訪和訪客計數最小化](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 我有局部資料點閱。如何清除我的資料?  {#section_CBE778A9D07A469E8FF98F68BACC7124}

您可以建立實質性報表套裝，將歷史性局部資料從報表中排除。

如需詳細資訊，請參閱「如何才能檢視沒有局部資料的歷史趨勢?」於[在A4T 中將膨脹後造訪和訪客計數最小化](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 怎麼做才能避免頁面產生局部資料點閱? {#section_4B00E7E618444BE98A0798DE98F08B21}

在2016年11月14日之後，Adobe將只在[!DNL Target]和[!DNL Analytics]標籤都已引發時才包含資料。 此變更不溯及既往。如果歷史報表顯示誇大計數，您可以建立虛擬報表套裝，將其從報表中排除。 請參閱「如何在沒有部分資料的情況下檢視歷史趨勢？」 在[中，將A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)中誇大的瀏覽和訪客計數降至最低。

您也可以執行一些步驟來儘量減少局部資料點閱。如需詳細資訊，請參閱「減少部分資料的最佳作法為何?」於[在A4T 中將膨脹後造訪和訪客計數最小化](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 如果部分資料點擊資料已從報告中移除，我是否會遺失有價值的[!DNL Target]或Analytics資料？{#section_EBC39E8A0F6A40E58F51E776936F7D9E}

在[!DNL Analytics]報告中包含部分資料確實提供了額外資訊，但也會在沒有[!DNL Target]活動執行的期間產生與歷史資料不一致的情況。 包含部分點擊資料可能會對分析特定時間趨勢的[!DNL Analytics]使用者造成問題。

您可以執行一些步驟來儘量減少局部資料點閱。如需詳細資訊，請參閱「減少部分資料的最佳作法為何?」於[在A4T 中將膨脹後造訪和訪客計數最小化](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 是否有任何較可能造成部分資料點擊的特定類型的[!DNL Target]活動？{#section_69837442A9B84366BEFDA4588B31E574}

重新導向選件會立即將使用者帶往另一個頁面，這表示在第一頁不會觸發 [!DNL Analytics] 呼叫。

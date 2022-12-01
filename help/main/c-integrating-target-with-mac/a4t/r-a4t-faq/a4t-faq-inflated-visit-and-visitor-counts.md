---
keywords: faq;常見問題集;analytics for target;a4T;膨脹;造訪;訪客;部分點擊;孤立的;孤立
description: 針對使用Analytics時膨脹的造訪和訪客計數，尋找相關問題的解答 [!DNL Target] (A4T)。 了解如何將「部分資料」減到最少。
title: 哪裡可以找到A4T膨脹後造訪和訪客計數的常見問題集？
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 49%

---

# 膨脹的造訪和訪客計數 - A4T 常見問題集

此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於膨脹後造訪和訪客計數問題的回答。

## 我的 Analytics 資料為何顯示沒有頁面檢視或其他變數值的造訪? {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

+++回答時機 [!DNL Adobe Analytics] 用於測量 [!DNL Target] 活動（稱為A4T）、 [!DNL Analytics] 收集沒有可用的資料 [!DNL Target] 活動。 這是因為 [!DNL Target] 活動會在頁面頂端觸發呼叫，但是 [!DNL Analytics] 一般是在頁面底部觸發其資料收集呼叫。在目前的 A4T 實作中，每當 [!DNL Target] 活動作用中時，Adobe 都會包含這項額外資料。 

如需詳細資訊，請參閱[在 A4T 中將膨脹後造訪和訪客計數最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 什麼是局部資料點閱? {#section_59A203E289564576BF6821F96B0B9E11}

+++回答當 [!DNL Target] 頁面頂端的標籤會觸發，但 [!DNL Analytics] 頁面底部的標籤不會引發。 這種情況發生的原因多種多樣。 在 [!DNL A4T] 目前為止的實作中，每當Adobe [!DNL Target] 活動已啟用。 未來，Adobe僅會在 [!DNL Target] 和 [!DNL Analytics] 標籤已引發。

如需詳細資訊，請參閱[在 A4T 中將膨脹後造訪和訪客計數最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 我看到造訪次數激增。如何判斷這些造訪是否是局部資料點閱所致？ {#section_28506672C6224ED18AC74F6A02F6F811}

+++回答您可以聯繫 [Adobe客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 來擷取「部分資料」報表。 [!DNL Analytics] UI 中不直接提供這項資訊。

+++

## 局部資料點閱可能有哪些原因? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++回答局部資料點閱通常是不當實施的結果，例如報表套裝ID不相符。 也有合理的原因，包括頁面緩慢、頁面錯誤、活動中的重新導向選件，或程式庫版本太舊。

如需詳細資訊，請參閱以下的「造成局部資料的原因」:[在A4T 中將膨脹後造訪和訪客計數最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 我有局部資料點閱。如何清除我的資料? {#section_CBE778A9D07A469E8FF98F68BACC7124}

+++答案您可以建立虛擬報表套裝，從報表中排除歷史部分資料。

如需詳細資訊，請參閱「如何才能檢視沒有局部資料的歷史趨勢?」於[在A4T 中將膨脹後造訪和訪客計數最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 怎麼做才能避免頁面產生局部資料點閱? {#section_4B00E7E618444BE98A0798DE98F08B21}

+++答案在2016年11月14日後，Adobe僅會在 [!DNL Target] 和 [!DNL Analytics] 標籤已引發。 此變更不溯及既往。 如果您的歷史報表顯示膨脹的計數，您可以建立虛擬報表套裝，從報表中排除這些計數。 請參閱「如何檢視沒有部分資料的歷史趨勢？」 in [在A4T中將膨脹的造訪和訪客計數減到最少](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

您也可以執行一些步驟來儘量減少局部資料點閱。如需詳細資訊，請參閱「減少部分資料的最佳作法為何?」於[在A4T 中將膨脹後造訪和訪客計數最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 如果「局部資料點閱」資料從報表中移除，不會失去有價值的 [!DNL Target] 還是Analytics資料？ {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

+++回答，包括 [!DNL Analytics] 報表不會提供額外資訊，但若沒有 [!DNL Target] 活動執行中。 包含局部點擊資料可能會造成 [!DNL Analytics] 分析隨時間變化趨勢的使用者。

您可以執行一些步驟來儘量減少局部資料點閱。如需詳細資訊，請參閱「減少部分資料的最佳作法為何?」於[在A4T 中將膨脹後造訪和訪客計數最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

+++

## 是否有任何特定類型 [!DNL Target] 更可能造成局部資料點閱的活動？ {#section_69837442A9B84366BEFDA4588B31E574}

+++回答重新導向選件會立即將使用者傳送至不同的頁面，這表示 [!DNL Analytics] 第一個頁面上不會觸發呼叫。

+++
---
keywords: faq;常見問題集;analytics for target;a4T;膨脹;造訪;訪客;部分點擊;孤立的;孤立
description: 針對使用Analytics時膨脹的造訪和訪客計數，尋找相關問題的解答 [!DNL Target] (A4T)。 了解如何將「部分資料」減到最少。
title: 哪裡可以找到A4T膨脹後造訪和訪客計數的常見問題集？
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 45%

---

# 膨脹的造訪和訪客計數 - A4T 常見問題集

此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於膨脹後造訪和訪客計數問題的回答。

## 我看到造訪次數激增。如何判斷這些造訪是否是局部資料點閱所致？ {#section_28506672C6224ED18AC74F6A02F6F811}

+++回答您可以聯繫 [Adobe客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 來擷取「部分資料」報表。 [!DNL Analytics] UI 中不直接提供這項資訊。

+++

## 局部資料點閱可能有哪些原因? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++回答局部資料點閱通常是不當實施的結果，例如報表套裝ID不相符。 也有合理的原因，包括頁面緩慢、頁面錯誤、活動中的重新導向選件，或程式庫版本太舊。

+++

## 是否有任何特定類型 [!DNL Target] 更可能造成局部資料點閱的活動？ {#section_69837442A9B84366BEFDA4588B31E574}

+++回答重新導向選件會立即將使用者傳送至不同的頁面，這表示 [!DNL Analytics] 第一個頁面上不會觸發呼叫。

+++
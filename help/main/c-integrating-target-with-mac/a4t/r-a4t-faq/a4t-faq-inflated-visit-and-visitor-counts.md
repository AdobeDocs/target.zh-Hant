---
keywords: faq;常見問題集;analytics for target;a4T;膨脹;造訪;訪客;部分點擊;孤立的;孤立
description: 為尋找有關使用Analytics時膨脹的造訪和訪客計數問題的解答 [!DNL Target] (A4T)。 瞭解如何將「部分資料」最小化。
title: 我可以在哪裡找到有關A4T膨脹後造訪和訪客計數的常見問題集？
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 45%

---

# 膨脹的造訪和訪客計數 - A4T 常見問題集

此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於膨脹後造訪和訪客計數問題的回答。

## 我看到造訪次數激增。如何判斷這些造訪是否由部分資料點選所造成？ {#section_28506672C6224ED18AC74F6A02F6F811}

+++回答您可以聯絡的人 [Adobe客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 以擷取「部分資料」報表。 [!DNL Analytics] UI 中不直接提供這項資訊。

+++

## 局部資料點閱可能有哪些原因? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++回答部分資料點選通常是因實施不當所造成，例如報表套裝ID未對齊。 也有合理的原因，包括頁面緩慢、頁面錯誤、活動中的重新導向選件，或程式庫版本太舊。

+++

## 是否有任何特定型別的 [!DNL Target] 可能造成部分資料點選的活動？ {#section_69837442A9B84366BEFDA4588B31E574}

+++回應重新導向選件會立即將使用者傳送到其他頁面，這表示 [!DNL Analytics] 呼叫不會在第一個頁面上觸發。

+++
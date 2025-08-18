---
keywords: faq;常見問題集;analytics for target;a4T;膨脹;造訪;訪客;部分點擊;孤立的;孤立
description: 尋找使用Analytics for [!DNL Target] (A4T)時膨脹的造訪和訪客計數問題的解答。 瞭解如何將「部分資料」最小化。
title: 我可以在哪裡找到有關A4T膨脹後造訪和訪客計數的常見問題集？
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 69%

---

# 膨脹的造訪和訪客計數 - A4T 常見問題集

此主題包含使用 Analytics 做為 Target 報表來源 (A4T) 時經常詢問關於膨脹後造訪和訪客計數問題的回答。

## 我看到造訪次數激增。我如何判斷這些造訪是否起因於區域性資料點選？ {#section_28506672C6224ED18AC74F6A02F6F811}

+++回答
您可以聯絡 [Adobe 客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以擷取「部分資料」報表。[!DNL Analytics] UI 中不直接提供這項資訊。

+++

## 局部資料點閱可能有哪些原因? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++回答
局部資料點閱通常是實作不當造成，例如報表套裝 ID 不對稱。也有合理的原因，包括頁面緩慢、頁面錯誤、活動中的重新導向產品建議，或程式庫版本太舊。

+++

## 是否有任何特定型別的[!DNL Target]活動很可能造成區域性資料點閱？ {#section_69837442A9B84366BEFDA4588B31E574}

+++回答
重新導向產品建議會立即將使用者帶往另一個頁面，這表示在第一頁不會觸發 [!DNL Analytics] 呼叫。

+++

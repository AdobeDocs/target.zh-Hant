---
description: 有關使用 Adobe 客戶服務在 Adobe Target 中實作 CNAME (規範名稱) 支援的資訊。
keywords: 客戶服務; CNAME; 憑證程式; 規範名稱; Cookie; 憑證；amc；adobe管理憑證
seo-description: 有關使用 Adobe 客戶服務在 Adobe Target 中實作 CNAME (規範名稱) 支援的資訊。
seo-title: CNAME 與 Adobe Target
solution: Target
title: CNAME 與 Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: b7a80326b0b89f6fe3bac70ccc6941be09d14ac1

---


# CNAME 與 Adobe Target {#cname-and-adobe-target}

Information about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Target]. 為了最妥善處理廣告封鎖問題或ITP相關Cookie原則，會使用CNAME來呼叫客戶擁有的網域，而不是Adobe擁有的網域。

Perform the following steps to request CNAME support in [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. 建立CNAME記錄(請參閱下面的指示)。

   在收到票證時，FPSSL專員應該提供您一組CNAME記錄。這些記錄必須在您公司的DNS伺服器上設定，Adobe才能代表您購買憑證。

   CNAME類似下列範例：

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. 當這些CNAME就位時，Adobe將會與Digicert搭配使用，在Adobe的生產伺服器上購買並安裝憑證。

1. 完成前述工作後，您必須更新至at. js `serverDomain` 中的新CNAME。

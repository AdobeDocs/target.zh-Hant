---
keywords: client care;cname;certificate program;cookies;certificate;amc;adobe受管理證書
description: 有關使用 Adobe 客戶服務在 Adobe Target 中實作 CNAME (規範名稱) 支援的資訊。
title: CNAME 與 Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# CNAME 與 Adobe Target {#cname-and-adobe-target}

Information about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Target]. 為了最好地處理廣告封鎖問題或ITP相關Cookie政策，會使用CNAME，以便對客戶所擁有的網域進行呼叫，而非對Adobe所擁有的網域進行呼叫。

Perform the following steps to request CNAME support in [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. 建立CNAME記錄（請參閱下方說明）。

   收到票證後，FPSSL專員應提供您一對CNAME記錄。 您必須先在貴公司的DNS伺服器上設定這些記錄，Adobe才能代表您購買憑證。

   CNAMES將類似下列範例：

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. 當這些CNAMES就緒時，Adobe將與DigiCert合作，在Adobe的生產伺服器上購買並安裝憑證。

1. 完成上述工作後，您必須在 at.js 中將 `serverDomain` 更新為新 CNAME。

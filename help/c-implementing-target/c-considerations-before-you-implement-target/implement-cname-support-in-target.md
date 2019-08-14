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
source-git-commit: d21838bdf17327b394f6e3106ea5ce4bc72605e6

---


# CNAME 與 Adobe Target{#cname-and-adobe-target}

有關使用 Adobe 客戶服務在 Adobe Target 中實作 CNAME (規範名稱) 支援的資訊。為了最妥善處理廣告封鎖問題，使用CNAME來呼叫客戶擁有的網域，而不是Adobe擁有的網域。

執行下列步驟以在 Target 中要求 CNAME 支援:

1. 開啟[要求 Adobe Target CNAME 支援呼叫的客戶服務票證](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。
1. 註冊 [Adobe Managed Certificate (AMC) Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html)，並遵循[!DNL Adobe Analytics]*第一方 Cookie* 指南中提供的實作步驟。[!DNL Target] 使用 [!DNL Analytics] CNAME支援使用的方法。

   AMC 程式有助於消除客戶實作第一方 Cookie 時需花費的心力與混淆。註冊此程式後，Adobe 會購買並發行憑證，以安裝在安全的伺服器上。

   >[!NOTE]
   >
   >註冊 AMC 程式之前，必須先設定 CNAME。

1. 完成前述工作後，您必須更新至at. js `serverDomain` 中的新CNAME。

## 訓練影片：第一方Cookie及使用Adobe Managed Certificates

This video is a recording of [Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7), an initiative led by the Adobe Customer Care team. Adobe Managed Certificate Program contribute started at10：21.

[Adobe Analytics：第一方Cookie及使用Adobe Managed Certificates](https://helpx.adobe.com/customer-care-office-hours/analytics/first-party-cookies-adobe-managed-certificates.html)

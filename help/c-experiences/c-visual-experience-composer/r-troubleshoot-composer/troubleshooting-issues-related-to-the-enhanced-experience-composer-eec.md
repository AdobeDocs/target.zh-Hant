---
keywords: Targeting;eec;visual experience composer;troubleshoot enhanced experience composer;troubleshooting
description: 顯示在某些情況下，有時候會發生在增強體驗撰寫器 (EEC) 中的問題。
title: 疑難排解增強體驗撰寫器的相關問題
feature: vec
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 71%

---


# 疑難排解增強體驗撰寫器的相關問題{#troubleshooting-issues-related-to-the-enhanced-experience-composer}

顯示在某些情況下，有時候會發生在增強體驗撰寫器 (EEC) 中的問題。

## EEC 不會載入無法在公用 IP 上存取的內部 QA URL。(僅限 EEC) {#section_D29E96911D5C401889B5EACE267F13CF}

這可透過允許列出下列IP位址來解決。 這些 IP 位址用於 Adobe 的伺服器，用於增強體驗撰寫器 Proxy。只有針對活動編輯才需要這些資訊。您網站的訪客不需要這些允許列出的IP位址

請您的IT團隊允許列出下列IP位址：

| 地區 | IP 位址 | 主機名稱 |
|--- |--- |--- |
| 美國 | 52.55.99.45 | `us1-proxy.adobemc.com` |
| 歐洲、中東和非洲 (EMEA) | 52.51.238.221 | `emea1-proxy.adobemc.com` |
| 亞太 (APAC) | 52.193.67.35 | `apac1-proxy.adobemc.com` |

您可能會在 Target 中看見下列錯誤訊息:

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can allowlist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

下列是您可能會看見此錯誤訊息的原因和修正此情況的補救方式:

* **問題:** 您的網站網域 (ISP) 正在封鎖增強體驗撰寫器。

   **補救方法：** 允許列出上述IP位址。

* **問題：** 允許列出IP位址，但您的網站不支援TLS 1.2版。Target目前使用預設的1.2組態。在Target 18.4.1之前（2018年4月25日），預設組態支援TLS 1.0。如需詳細資訊，請參 [閱TLS（傳輸層安全性）加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)。

   **解決方案:** 請參閱下列問題: 增強可視化體驗撰寫器不會在我使用 TLS 1.2 的網站上安全頁面中載入。

## EEC 不會在我使用 TLS 1.0 的網站上安全頁面中載入。(僅限 EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

您可能會看見以上的「增強可視化體驗撰寫器不會在我的網站上安全頁面中載入」中所述的錯誤訊息。if the above IP addresses are allowlisted but your website does not support TLS version 1.2. Target currently uses the default configuration of 1.2. Prior to the Target 18.4.1 (April 25, 2018), the default configuration supported TLS 1.0. For more information, see [TLS (Transport Layer Security) Encryption Changes](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

若要使用 Firefox 檢查您的網站的 TLS 版本 (其他瀏覽器有類似的步驟):

1. 在 Firefox 中開啟受影響的網站。
1. 在瀏覽器的位址列按一下&#x200B;**[!UICONTROL 「顯示網站資訊」]**&#x200B;圖示。

   ![](assets/firefox_more_info.png)

1. 按一下&#x200B;**[!UICONTROL 「顯示連線詳細資料」]**>**[!UICONTROL 「詳細資訊」]**。

   ![](assets/firefox_more_info_2.png)

1. 在技術詳細資料下檢查 TLS 版本資訊:

   ![](assets/firefox_more_info_3.png)

1. 如果發現網站顯示 TLS 1.0，請參閱 [TLS (傳輸層安全性) 加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)，獲得 Target 的 TLS 支援政策相關資訊。若要補救目前狀況 (2018 年 9 月 12 日前有效)，請聯絡[客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以取得您的 TLS 版本和網域的組態。

## 載入已啟用 Proxy 的網站時，我看到逾時或「拒絕存取」錯誤。(僅限 EEC) {#section_60CBB9022DC449F593606C0E6252302D}

確定您的環境中未封鎖 Proxy IP。

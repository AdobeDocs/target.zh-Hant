---
keywords: 鎖定目標; EEC; 可視化體驗撰寫器; 疑難排解增強體驗撰寫器; 疑難排解
description: 瞭解如何排除在特定條件下Adobe [!DNL Target] Enhanced Experience Composer(EEC)中有時會出現的問題。
title: 如何疑難排解與增強的Experience Composer相關的問題？
feature: 可視化體驗撰寫器 (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: b14c9bb4bc0363c77de084c7ae7110e73c5f2f13
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 48%

---

# 疑難排解與[!UICONTROL Enhanced Experience Composer]相關的問題

在某些情況下，在[!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer](EEC)中有時會出現顯示問題。

## EEC 不會載入無法在公用 IP 上存取的內部 QA URL。 {#section_D29E96911D5C401889B5EACE267F13CF}

這可透過允許列出下列IP位址來解決。 這些IP地址用於Adobe的伺服器，用於EEC代理。 只有針對活動編輯才需要這些資訊。您網站的訪客不需要列出這些IP位址。

請您的IT團隊允許列出下列IP位址：

* 52.55.99.45
* 52.51.238.221
* 52.193.67.35

您可能會在[!DNL Target]中看到下列錯誤訊息：

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

下列是您可能會看見此錯誤訊息的原因和修正此情況的補救方式:

* **問題：** 您的網站網域(ISP)封鎖了「增強的 [!UICONTROL 體驗撰寫器」]。

   **Remedy:** 允許列出上述IP位址。

* **問題：** 允許列出IP位址，但您的網站不支援TLS 1.2版。 [!DNL Target] 當前使用預設配置1.2。在 [!DNL Target] 18.4.1之前（2018年4月25日），預設組態支援TLS 1.0。如需詳細資訊，請參 [閱TLS（傳輸層安全性）加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)。

   **解決方案:**[!UICONTROL  請參閱下列問題: 增強可視化體驗撰寫器不會在我使用 TLS 1.2 的網站上安全頁面中載入。]

## EEC 不會在我使用 TLS 1.0 的網站上安全頁面中載入。(僅限 EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

您可能會在「The [!UICONTROL Enhanced Visual Experience Composer] won&#39;t load on my site」（網站上的安全頁面不會載入）中看到上述錯誤訊息。 如果上述IP位址已允許列出，但您的網站不支援TLS 1.2版。[!DNL Target]目前使用預設組態1.2。在[!DNL Target] 18.4.1（2018年4月25日）之前，預設組態支援TLS 1.0。如需詳細資訊，請參閱[TLS（傳輸層安全性）加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)。

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

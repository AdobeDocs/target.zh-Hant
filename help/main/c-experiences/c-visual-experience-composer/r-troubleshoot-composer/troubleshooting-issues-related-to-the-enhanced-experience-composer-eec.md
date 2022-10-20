---
keywords: 鎖定目標; EEC; 可視化體驗撰寫器; 疑難排解增強體驗撰寫器; 疑難排解
description: 了解如何疑難排解Adobe中有時發生的問題 [!DNL Target] 增強體驗撰寫器(EEC)。
title: 如何疑難排解增強體驗撰寫器的相關問題？
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 5408c0ae5318250fa1f035f8cb8211a16600cf24
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 36%

---

# 排解[!UICONTROL 增強體驗撰寫器的相關問題]

顯示有時發生在 [!DNL Adobe Target] [!UICONTROL 增強體驗撰寫器] (EEC)。

## EEC 不會載入無法在公用 IP 上存取的內部 QA URL。 {#section_D29E96911D5C401889B5EACE267F13CF}

若允許列出下列IP位址，即可解決此問題。 這些IP位址是用於Adobe用於EEC代理的伺服器。 只有針對活動編輯才需要這些資訊。您網站的訪客不需要列出的這些IP位址。

請您的IT團隊允許列出下列IP位址：

* 34.253.100.20
* 34.248.100.23
* 52.49.228.246
* 54.205.42.123
* 107.22.177.39
* 52.201.5.105
* 52.193.211.177
* 18.180.24.249
* 52.194.154.154

您可能會在 [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error映像](assets/EEC_error.png)

下列是您可能會看見此錯誤訊息的原因和修正此情況的補救方式:

* **問題：** 您的網站網域(ISP)封鎖 [!UICONTROL 增強體驗撰寫器].

   **補救：** 允許列出上述IP位址。

* **問題：** 允許列出IP位址，但您的網站不支援TLS 1.2版。 [!DNL Target] 目前使用1.2的預設設定。 [!DNL Target] 18.4.1（2018年4月25日），預設設定支援TLS 1.0。如需詳細資訊，請參閱 [TLS（傳輸層安全性）加密變更](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank}。

   **解決方案:**[!UICONTROL  請參閱下列問題: 增強可視化體驗撰寫器不會在我使用 TLS 1.2 的網站上安全頁面中載入。]

## EEC 不會在我使用 TLS 1.0 的網站上安全頁面中載入。(僅限 EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

您可能會看到上述的錯誤訊息，如 [!UICONTROL 增強可視化體驗撰寫器] 不會載入到我網站上的安全頁面上。」 若已允許上述IP位址，但您的網站不支援TLS 1.2版。 [!DNL Target] 目前使用1.2的預設設定。 [!DNL Target] 18.4.1（2018年4月25日），預設設定支援TLS 1.0。如需詳細資訊，請參閱 [TLS（傳輸層安全性）加密變更](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank}。

若要使用 Firefox 檢查您的網站的 TLS 版本 (其他瀏覽器有類似的步驟):

1. 在 Firefox 中開啟受影響的網站。
1. 在瀏覽器的位址列按一下&#x200B;**[!UICONTROL 「顯示網站資訊」]**&#x200B;圖示。

   ![firefox_more_info影像](assets/firefox_more_info.png)

1. 按一下&#x200B;**[!UICONTROL 「顯示連線詳細資料」]**>**[!UICONTROL 「詳細資訊」]**。

   ![firefox_more_info_2影像](assets/firefox_more_info_2.png)

1. 在技術詳細資料下檢查 TLS 版本資訊:

   ![firefox_more_info_3影像](assets/firefox_more_info_3.png)

1. 若您發現您的網站顯示TLS 1.0，請參閱 [TLS（傳輸層安全性）加密變更](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank}，以取得Target的TLS支援原則的相關資訊。 若要補救目前狀況（2018年9月12日前有效）{target=_blank}，請洽詢 [客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 以使用您的TLS版本和網域進行設定。

## 載入已啟用 Proxy 的網站時，我看到逾時或「拒絕存取」錯誤。(僅限 EEC) {#section_60CBB9022DC449F593606C0E6252302D}

確定您的環境中未封鎖 Proxy IP。

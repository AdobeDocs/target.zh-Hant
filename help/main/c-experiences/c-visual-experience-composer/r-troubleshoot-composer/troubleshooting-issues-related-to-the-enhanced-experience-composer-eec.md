---
keywords: 鎖定目標; EEC; 可視化體驗撰寫器; 疑難排解增強體驗撰寫器; 疑難排解
description: 瞭解如何疑難排解Adobe中有時發生的問題 [!DNL Target] 特定條件下的增強體驗撰寫器(EEC)。
title: 如何疑難排解增強體驗撰寫器的相關問題？
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: f948e6bd66a42939834b598821d68b93c82fa6af
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 38%

---

# 排解[!UICONTROL 增強體驗撰寫器的相關問題]

顯示問題有時發生在 [!DNL Adobe Target] [!UICONTROL 增強體驗撰寫器] (EEC)在一定條件下。

## EEC 不會載入無法在公用 IP 上存取的內部 QA URL。 {#section_D29E96911D5C401889B5EACE267F13CF}

將下列IP位址列入允許清單即可解決此問題。 這些IP位址用於Adobe用於EEC Proxy的伺服器。 只有針對活動編輯才需要這些資訊。您網站的訪客不需要將這些IP位址加入允許清單。

要求您的IT團隊將下列IP位址加入允許清單：

* 52.18.97.86
* 52.209.31.20
* 52.214.41.220
* 54.144.66.225
* 54.82.53.36
* 34.206.104.26
* 3.115.90.128
* 18.178.137.67
* 3.112.77.52

您可能會在中看到下列錯誤訊息 [!DNL Target]：

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error圖片](assets/EEC_error.png)

下列是您可能會看見此錯誤訊息的原因和修正此情況的補救方式:

* **問題：** 您的網站網域(ISP)封鎖 [!UICONTROL 增強體驗撰寫器].

  **補救措施：** 將上述IP位址列入允許清單。

* **問題：** 這些IP位址已加入允許清單，但您的網站不支援TLS 1.2版。 [!DNL Target] 目前使用1.2的預設設定。在之前 [!DNL Target] 18.4.1 （2018年4月25日），預設設定支援TLS 1.0。如需詳細資訊，請參閱 [TLS （傳輸層安全性）加密變更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

  **解決方案:**[!UICONTROL  請參閱下列問題: 增強可視化體驗撰寫器不會在我使用 TLS 1.2 的網站上安全頁面中載入。]

## EEC 不會在我使用 TLS 1.0 的網站上安全頁面中載入。(僅限 EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

您可能會看到上述錯誤訊息，請參閱 [!UICONTROL 增強型視覺化體驗撰寫器] 不會在我的網站的安全頁面中載入。」 如果上述IP位址已加入允許清單，但您的網站不支援TLS 1.2版。 [!DNL Target] 目前使用1.2的預設設定。在之前 [!DNL Target] 18.4.1 （2018年4月25日），預設設定支援TLS 1.0。如需詳細資訊，請參閱 [TLS （傳輸層安全性）加密變更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

若要使用 Firefox 檢查您的網站的 TLS 版本 (其他瀏覽器有類似的步驟):

1. 在 Firefox 中開啟受影響的網站。
1. 在瀏覽器的位址列按一下&#x200B;**[!UICONTROL 「顯示網站資訊」]**&#x200B;圖示。

   ![firefox_more_info圖片](assets/firefox_more_info.png)

1. 按一下&#x200B;**[!UICONTROL 「顯示連線詳細資料」]**>**[!UICONTROL 「詳細資訊」]**。

   ![firefox_more_info_2圖片](assets/firefox_more_info_2.png)

1. 在技術詳細資料下檢查 TLS 版本資訊:

   ![firefox_more_info_3圖片](assets/firefox_more_info_3.png)

1. 如果您發現您的網站顯示TLS 1.0，請參閱 [TLS （傳輸層安全性）加密變更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} for information about Target's TLS support policy. To remedy the situation for now (valid until September 12, 2018){target=_blank}，請聯絡 [客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 以設定您的TLS版本和網域。

## 載入已啟用 Proxy 的網站時，我看到逾時或「拒絕存取」錯誤。(僅限 EEC) {#section_60CBB9022DC449F593606C0E6252302D}

確定您的環境中未封鎖 Proxy IP。

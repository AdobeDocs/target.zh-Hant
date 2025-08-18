---
keywords: 鎖定目標; EEC; 可視化體驗撰寫器; 疑難排解增強體驗撰寫器; 疑難排解
description: 瞭解如何疑難排解 [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC)在某些情況下有時發生的問題。
title: 如何疑難排解[!UICONTROL Enhanced Experience Composer]的相關問題？
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: ef5df0ae37ca1d07c0e51c06ed78739b2d2983fc
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 22%

---

# 疑難排解[!UICONTROL Enhanced Experience Composer]的相關問題

在某些情況下，[!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC)有時會發生顯示問題。

## EEC不會載入無法在公用IP上存取的內部QA URL。 {#section_D29E96911D5C401889B5EACE267F13CF}


+++詳細資料
此問題可透過將下列IP位址列入允許清單來解決。 這些IP位址是用於用於EEC Proxy的[!DNL Adobe]伺服器。 這些IP位址僅供活動編輯所需。 您網站的訪客不需要將這些IP位址加入允許清單。

要求您的IT團隊將下列IP位址加入允許清單：

### 美國(va7)

40.70.154.136/29
52.254.106.240/28
52.254.106.160/28
52.254.107.16/28
20.186.185.181
20.22.83.112
20.186.185.227
52.254.106.192/28
52.254.106.0/28
52.254.107.128/28
52.254.107.80/28
52.254.106.176/28
52.254.107.32/28
52.254.105.192/28
52.254.107.64/28
52.254.106.208/28
52.254.107.0/28
52.254.106.224/28
20.14.241.153
20.186.185.239
4.152.211.251
52.254.107.144/28
52.254.106.144/28

### EMEA (nld2)

51.138.17.16/28
51.138.17.48/28
51.138.16.128/28
51.138.17.32/28
51.138.16.240/28
51.138.17.112/28
51.138.16.160/28
51.138.16.208/28
51.138.17.80/28
51.138.17.0/28
51.138.17.96/28
51.138.16.144/28
20.31.145.248
20.126.189.248
51.138.16.224/28
51.138.16.192/28
51.138.12.94
51.138.12.11
51.138.16.176/28
51.138.12.100
51.138.17.64/28
51.138.12.160/28

### APAC (aus)

20.43.104.160/28
20.227.35.177
20.40.188.227
20.43.104.112/28
20.43.104.128/28
20.43.104.144/28
20.40.188.166
20.53.206.128
20.43.104.80/28
20.43.104.16/28
20.43.105.48/28
20.43.104.96/28
20.43.104.48/28
20.40.188.194
20.43.104.32/28
20.40.191.224/28
20.43.105.16/28
20.40.191.96/28
20.43.104.176/28
20.40.191.240/28
20.43.104.64/28
20.43.105.32/28
20.43.104.192/28
20.43.105.0/28
20.43.104.0/28

### 舊版IP位址

下列舊版IP位址應繼續列入允許清單，直到另行通知為止。

34.254.77.200
54.73.207.147
54.229.152.123
3.224.194.242
54.90.51.39
34.228.136.112
54.150.116.11
18.178.142.8
54.199.107.77
99.80.139.221
54.78.56.224
54.247.179.246
54.80.219.243
34.201.235.54
54.196.224.236
35.75.212.45
52.199.184.130
18.180.161.176

您可能會在[!DNL Target]中看到下列錯誤訊息：

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error影像](assets/EEC_error.png)

下列是您可能會看見此錯誤訊息的原因和修正此情況的補救方式:

* **問題：**&#x200B;您的網站網域(ISP)封鎖[!UICONTROL Enhanced Experience Composer]。

  **補救措施：**&#x200B;將上述IP位址列入允許清單。

* **問題：** IP位址已加入允許清單，但您的網站不支援TLS 1.2版。[!DNL Target]目前使用預設設定1.2。在[!DNL Target] 18.4.1 （2018年4月25日）之前，預設設定支援TLS 1.0。如需詳細資訊，請參閱[TLS （傳輸層安全性）加密變更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=zh-Hant){target=_blank}。

  **解決方案：**&#x200B;請參閱下列問題（[!UICONTROL Enhanced Visual Experience Composer]將不會在我的網站上使用TLS 1.2的安全頁面上載入）。

+++

## EEC 不會在我使用 TLS 1.0 的網站上安全頁面中載入。(僅限 EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

+++詳細資料
您可能會看見上述「我的網站的安全頁面不會載入[!UICONTROL Enhanced Visual Experience Composer]」中所述的錯誤訊息。 如果上述IP位址已加入允許清單，但您的網站不支援TLS 1.2版。[!DNL Target]目前使用預設設定1.2。在[!DNL Target] 18.4.1 （2018年4月25日）之前，預設設定支援TLS 1.0。如需詳細資訊，請參閱[TLS （傳輸層安全性）加密變更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=zh-Hant){target=_blank}。

若要使用 Firefox 檢查您的網站的 TLS 版本 (其他瀏覽器有類似的步驟):

1. 在 Firefox 中開啟受影響的網站。
1. 按一下瀏覽器位址列上的&#x200B;**[!UICONTROL Show Site Information]**&#x200B;圖示。

   ![firefox_more_info影像](assets/firefox_more_info.png)

1. 按一下&#x200B;**[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**。

   ![firefox_more_info_2圖片](assets/firefox_more_info_2.png)

1. 在技術詳細資料下檢查 TLS 版本資訊:

   ![firefox_more_info_3圖片](assets/firefox_more_info_3.png)

1. 如果您發現您的網站顯示TLS 1.0，請參閱[TLS （傳輸層安全性）加密變更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=zh-Hant){target=_blank}，以取得Target的TLS支援原則相關資訊。 若要補救目前狀況（2018年9月12日前有效）{target=_blank}，請聯絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以取得您的TLS版本和網域的組態。

+++

## 載入已啟用 Proxy 的網站時，我看到逾時或「拒絕存取」錯誤。(僅限 EEC) {#section_60CBB9022DC449F593606C0E6252302D}

+++詳細資料
確定您的環境中未封鎖 Proxy IP。

+++

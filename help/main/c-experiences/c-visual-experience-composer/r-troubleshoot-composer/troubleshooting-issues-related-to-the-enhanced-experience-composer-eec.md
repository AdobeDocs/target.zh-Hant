---
keywords: 鎖定目標; EEC; 可視化體驗撰寫器; 疑難排解增強體驗撰寫器; 疑難排解
description: 瞭解如何疑難排解[!DNL Adobe Target] [!UICONTROL 增強體驗撰寫器] (EEC)在某些情況下有時會發生的問題。
title: 如何疑難排解[!UICONTROL 增強體驗撰寫器]的相關問題？
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
TQID: 'https://experienceleague.adobe.com/Yan2cKWjs-u9JHQzT-PiRAFdxUJa1JSHS-fT68yxIjg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 5%
---
# 疑難排解[!UICONTROL 增強體驗撰寫器]的相關問題 {#eec-issues}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何解決僅影響&#x200B;**[!UICONTROL 增強體驗撰寫器]** (EEC)的問題，例如因為EEC Proxy的IP位址被封鎖而無法載入的頁面。

>[!ENDSHADEBOX]

顯示在某些情況下，有時候會在[!DNL Adobe Target] **[!UICONTROL 增強體驗撰寫器]** (EEC)中發生問題。 以下專案說明僅影響EEC的問題以及如何解決這些問題。

## 將EEC Proxy的IP位址列入允許清單 {#eec-ip-addresses}

EEC不會載入無法在公用IP位址上存取的內部QA URL。 將用於EEC Proxy的[!DNL Adobe]伺服器IP位址列入允許清單可解決此問題。 這些IP位址只有在編輯活動時才需要，網站的訪客不需要將它們加入允許清單。 要求IT團隊將下列IP位址列入允許清單。

### 美國(va7)

```
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
```

### EMEA (nld2)

```
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
```

### APAC (aus)

```
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
```

### 舊版IP位址

下列舊版IP位址應繼續列入允許清單，直到另行通知為止。

```
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
```

+++ EEC會顯示錯誤訊息，指出網站網域封鎖它

下列錯誤訊息可在[!DNL Target]中顯示：

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can allowlist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in Configure > Page Delivery menu.`

![體驗撰寫器，錯誤訊息為網站網域(ISP)封鎖Enhanced Experience Composer，建議將IP位址加入允許清單，或在[設定頁面傳送]功能表中關閉撰寫器](assets/EEC_error.png)

此錯誤訊息有兩個可能的原因：

* 網站網域(ISP)會封鎖EEC。 若要解決此問題，請將[中列出的IP位址加入允許清單，將EEC Proxy](#eec-ip-addresses)的IP位址加入允許清單。
* 這些IP位址已加入允許清單，但網站不支援TLS 1.2。 若要解決此問題，請參閱下列專案。

+++

+++ EEC沒有在使用TLS 1.0的網站安全頁面上載入

當IP位址已加入允許清單，但網站不支援TLS 1.2時，會顯示上一項中說明的錯誤訊息。 [!DNL Target]目前使用1.2版作為預設設定。 在[!DNL Target] 18.4.1 （2018年4月25日）之前，預設設定支援TLS 1.0。 如需詳細資訊，請參閱 [TLS (傳輸層安全性) 加密變更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=zh-Hant){target=_blank}。

若要在Firefox中檢查網站的TLS版本（其他瀏覽器有類似的步驟）：

1. 在 Firefox 中開啟受影響的網站。
1. 按一下瀏覽器位址列上的&#x200B;**[!UICONTROL 顯示網站資訊]**&#x200B;圖示。

   ![Firefox位址列，在URL](assets/firefox_more_info.png)左側反白顯示[顯示網站資訊]圖示

1. 按一下&#x200B;**[!UICONTROL 「顯示連線詳細資料」]**>**[!UICONTROL 「詳細資訊」]**。

   ![Firefox網站資訊面板，在「安全連線」旁邊反白顯示「顯示連線詳細資料」箭頭](assets/firefox_more_info_2.png)

1. 檢查&#x200B;**[!UICONTROL 技術詳細資料]**&#x200B;下的TLS版本資訊。

   ![Firefox頁面資訊視窗，安全性索引標籤，技術詳細資訊下方會醒目提示TLS版本](assets/firefox_more_info_3.png)

1. 如果網站顯示TLS 1.0，請參閱[TLS （傳輸層安全性）加密變更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=zh-Hant){target=_blank}，以取得[!DNL Target]的TLS支援原則相關資訊。 若要補救目前狀況（2018年9月12日前有效），請聯絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以取得TLS版本和網域的組態。

+++

+++ 載入已啟用Proxy的網站時，會顯示逾時或「拒絕存取」錯誤

請確定環境中未封鎖Proxy IP位址。 這些位址列在[允許列出EEC Proxy](#eec-ip-addresses)的IP位址。

+++

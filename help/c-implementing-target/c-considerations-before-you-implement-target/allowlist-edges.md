---
keywords: 實施；實施；白名單；白名單；allowlist;allowlist;edge;edge
description: 檢視主機清單，協助您列出Adobe Target邊緣（地理位置分散的服務節點，可確保使用者的最佳回應時間）。
title: 如何允許列出目標邊緣節點？
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: 806c52e69cce636a56eb067759612f80829418f9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 7%

---


# 允許列出目標邊緣節點

幫助您列出[!DNL Adobe Target]邊的資訊和最新主機清單。

邊緣是地理上分散的服務架構，可確保最佳回應時間給要求內容的使用者，不論使用者位於何處。 每個邊緣節點都具備回應使用者內容要求及追蹤該要求之分析資料所需的所有資訊。 用戶請求被路由到最近的邊緣節點。 如需詳細資訊，請參閱&#x200B;*Adobe[!DNL Target]如何運作*&#x200B;中的[邊緣網路](/help/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934)。

如果需要，可以允許列出[!DNL Target]邊節點。

## 目標邊緣的網路地址轉換(NAT)IP地址

[!DNL Target]邊的出口IP地址清單。 如果您打算讓Target觸及您的服務，請允許列出這些IP。

| 邊緣位置 | 出口IP地址 |
| --- | --- |
| Edge31(Mumbai) | 13.126.131.246<br>13.234.229.8 |
| Edge32（東京） | 3.115.154.28<br>3.115.227.146 |
| Edge34（美國東海岸） | 34.232.149.249<br>52.21.139.93 |
| Edge35（美國西海岸） | 52.10.11.139<br>44.231.171.161 |
| Edge36（雪梨） | 13.237.227.20<br>13.210.93.142 |
| Edge37（愛爾蘭） | 54.72.21.68<br>52.208.139.19 |
| Edge38（新加坡） | 18.141.132.96<br>54.179.187.167 |

## 目標邊緣IP位址

[!DNL Target]邊的IP地址清單。 如果您要對Target邊緣進行API呼叫，可以列出這些IP。

| 邊緣位置 | 網域 | IP 位址 |
| --- | --- | --- |
|  | `CLIENTCODE.tt.omtrdc.net`<br>(其中CLIENTCODE是您的 [!DNL Target] 用戶端ID) |  |
| Edge31(Mumbai) | `mboxedge31.tt.omtrdc.net` | 15.207.157.131<br>15.206.8.201 |
| Edge32（東京） | `mboxedge32.tt.omtrdc.net` | 54.199.66.101<br>54.64.93.37 |
| Edge34（美國東海岸） | `mboxedge34.tt.omtrdc.net` | 3.225.56.36<br>3.230.207.249<br>34.198.55.51<br>52.3.14.12<br>52.21.222.93<br>52.55.235.132<br>52.70.52.52<br>54.165.204.89 |
| Edge35（美國西海岸） | `mboxedge35.tt.omtrdc.net` | 52.10.244.20<br>52.36.232.38<br>52.88.209.29<br>54.214.180.56<br>35.162.74.35<br>34.214.12.211<br>52.42.35.202<br>54.148.71.13 |
| Edge36（雪梨） | `mboxedge36.tt.omtrdc.net` | 13.238.34.185<br>3.24.250.17<br>3.104.234.91<br>13.211.248.241 |
| Edge37（愛爾蘭） | `mboxedge37.tt.omtrdc.net` | 52.212.193.208<br>52.19.133.54<br>52.51.251.137<br>34.252.156.174<br>52.213.168.74<br>34.252.166.160<br>52.18.150.20<br>18.203.205.32 |
| Edge38（新加坡） | `mboxedge38.tt.omtrdc.net` | 52.221.145.65<br>52.220.44.99<br>13.250.75.226<br>54.151.139.123 |






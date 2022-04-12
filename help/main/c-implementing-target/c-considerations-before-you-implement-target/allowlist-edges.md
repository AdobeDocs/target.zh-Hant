---
keywords: 實現；實現；白名單；白名單；允許清單；邊緣；實現；白名單；白名單；允許清單；允許清單；邊緣
description: 查看主機清單以幫助您允許清單Adobe [!DNL Target] 邊（地理位置分佈的服務節點，確保最佳響應時間）。
title: 如何允許清單 [!DNL Target] 邊緣節點？
feature: Privacy & Security
role: Developer
exl-id: 2d8399b9-eec8-40b0-8b35-2812f83ff4dc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# 允許清單 [!DNL Target] 邊緣節點

資訊和最新主機清單，以幫助您允許列出 [!DNL Adobe Target] 邊。

邊緣是地理上分佈的服務體系結構，它確保請求內容的最終用戶的最佳響應時間，而不管他們位於何處。 每個邊緣節點都具有響應用戶內容請求和跟蹤該請求的分析資料所需的所有資訊。 用戶請求被路由到最近的邊緣節點。 有關詳細資訊，請參見 [邊緣網路](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) 在 *Adobe [!DNL Target] 作品*。

您可以允許清單 [!DNL Target] 邊節點（如果需要）。

## 網路地址轉換(NAT)IP地址 [!DNL Target] 邊

出口IP地址清單 [!DNL Target] 邊。 如果您計畫讓目標與您的服務聯繫，則允許列出這些IP。

| 邊位置 | 輸出IP地址 |
| --- | --- |
| Edge31（孟買） | 13.126.131.246<br>13.234.229.8 |
| Edge32（東京） | 3.115.154.28<br>3.115.227.146 |
| Edge34（美國東海岸） | 34.232.149.249<br>52.21.139.93 |
| Edge35（美國西海岸） | 52.10.11.139<br>44.231.171.161 |
| Edge36（雪梨） | 13.237.227.20<br>13.210.93.142 |
| Edge37（愛爾蘭） | 54.72.21.68<br>52.208.139.19 |
| Edge38（新加坡） | 18.141.132.96<br>54.179.187.167 |

## 目標邊緣IP地址

IP地址清單 [!DNL Target] 邊。 如果要對目標邊緣進行API調用，則允許列出這些IP。

| 邊位置 | 網域 | IP 位址 |
| --- | --- | --- |
|  | `CLIENTCODE.tt.omtrdc.net`<br>(其中CLIENTCODE是您 [!DNL Target] 客戶端ID) |  |
| Edge31（孟買） | `mboxedge31.tt.omtrdc.net` | 15.207.157.131<br>15.206.8.201 |
| Edge32（東京） | `mboxedge32.tt.omtrdc.net` | 54.199.66.101<br>54.64.93.37 |
| Edge34（美國東海岸） | `mboxedge34.tt.omtrdc.net` | 3.225.56.36<br>3.230.207.249<br>34.198.55.51<br>52.3.14.12<br>52.21.222.93<br>52.55.235.132<br>52.70.52.52<br>54.165.204.89 |
| Edge35（美國西海岸） | `mboxedge35.tt.omtrdc.net` | 52.10.244.20<br>52.36.232.38<br>52.88.209.29<br>54.214.180.56<br>35.162.74.35<br>34.214.12.211<br>52.42.35.202<br>54.148.71.13 |
| Edge36（雪梨） | `mboxedge36.tt.omtrdc.net` | 13.238.34.185<br>3.24.250.17<br>3.104.234.91<br>13.211.248.241 |
| Edge37（愛爾蘭） | `mboxedge37.tt.omtrdc.net` | 52.212.193.208<br>52.19.133.54<br>52.51.251.137<br>34.252.156.174<br>52.213.168.74<br>34.252.166.160<br>52.18.150.20<br>18.203.205.32 |
| Edge38（新加坡） | `mboxedge38.tt.omtrdc.net` | 52.221.145.65<br>52.220.44.99<br>13.250.75.226<br>54.151.139.123 |
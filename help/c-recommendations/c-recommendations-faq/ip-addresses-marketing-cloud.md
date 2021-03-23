---
keywords: IP位址；IP位址；白名單；allowlist;firewall;recs;feed;servers;adobe marketing cloud;recommendations
description: 檢視TargetRecommendations饋送處理伺服器中使用的IP位址清單，以協助您設定防火牆，以允許源自Adobe伺服器的IP位址。
title: Recommendations饋送處理伺服器使用哪些IP位址？
feature: Recommendations
translation-type: tm+mt
source-git-commit: 55b246f5f0d660e6c4f71352c5b638347d55ac28
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 13%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations 摘要處理伺服器使用的 IP 位址

[!DNL Adobe Target] [!DNL Recommendations]饋送處理伺服器中使用的IP位址清單，可協助您設定防火牆，以允許源自Adobe伺服器的IP位址。

[!DNL Target] [!UICONTROL 建] 議活動在存取客戶的FTP伺服器時使用下列IP位址：

| CIDR 符號 |
|---|
| 44.241.237.28/32 |
| 44.232.167.82/32 |
| 52.41.252.205/32 |

[!DNL Target]  RecommendationsAPI使用下列IP位址：

| CIDR 符號 |
|---|
| 44.241.237.28/32 |
| 44.232.167.82/32 |
| 52.41.252.205/32 |

>[!NOTE]
>
>這些IP位址上次更新日期為2021年3月16日。 以前，訪問FTP伺服器的伺服器位於192.243.242.0/24 IP地址CIDR塊中。 托管RecommendationsAPI的伺服器位於192.243.224.0/20 IP地址CIDR塊中。


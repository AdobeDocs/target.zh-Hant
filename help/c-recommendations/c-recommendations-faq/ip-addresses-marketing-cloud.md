---
keywords: IP 位址;IP 位址;合格清單;允許清單;防火牆;recs;摘要;伺服器;adobe marketing cloud;推薦
description: 檢視 [!DNL Target] Recommendations饋送處理伺服器中使用的IP位址清單，協助您設定防火牆，以允許源自Adobe伺服器的IP位址。
title: Recommendations 摘要處理伺服器使用哪些 IP 位址？
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 24%

---

# Recommendations 摘要處理伺服器使用的 ![PREMIUM](/help/assets/premium.png) IP 位址

[!DNL Adobe Target] [!DNL Recommendations]饋送處理伺服器中使用的IP位址清單，可協助您設定防火牆，以允許源自Adobe伺服器的IP位址。

[!DNL Target] [!UICONTROL 在訪] 問客戶的FTP伺服器時，建議活動使用以下AWS主機：

| 位置 | 主機 |
| --- | --- |
| 俄勒岡州 | `44.241.237.28` |
| 俄勒岡州 | `44.232.167.82` |
| 俄勒岡州 | `52.41.252.205` |

[!DNL Target]  RecommendationsAPI也使用相同的AWS主機。

>[!NOTE]
>
>這些IP位址上次更新日期為2021年3月16日。 以前，訪問FTP伺服器的伺服器位於192.243.242.0/24 IP地址CIDR塊中。 托管RecommendationsAPI的伺服器位於192.243.224.0/20 IP地址CIDR塊中。

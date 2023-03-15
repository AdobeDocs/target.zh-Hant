---
keywords: IP 位址;IP 位址;合格清單;允許清單;防火牆;recs;摘要;伺服器;adobe marketing cloud;recommendations
description: 檢視用於 [!DNL Target] Recommendations 摘要處理伺服器的 IP 位址清單，協助您將防火牆設定為允許來自 Adobe 伺服器的 IP 位址。
title: Recommendations 摘要處理伺服器使用哪些 IP 位址？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 100%

---

# Recommendations 摘要處理伺服器使用的 IP 位址

[!DNL Adobe Target] [!DNL Recommendations] 摘要處理伺服器中使用的 IP 位址清單，可協助您將防火牆設定為允許來自 Adobe 伺服器的 IP 位址。

[!DNL Target] [!UICONTROL Recommendations] 活動在存取客戶的 FTP 伺服器時會使用以下 AWS 主機：

| 位置 | 主機 |
| --- | --- |
| 美國奧勒岡 | `44.241.237.28` |
| 美國奧勒岡 | `44.232.167.82` |
| 美國奧勒岡 | `52.41.252.205` |

[!DNL Target] [!UICONTROL Recommendations] API 也會使用相同的 AWS 主機。

>[!NOTE]
>
>這些 IP 位址的上次更新日期為 2021 年 3 月 16 日。 先前，存取 FTP 伺服器的伺服器位在 192.243.242.0/24 IP 位址 CIDR 區塊中。 代管 Recommendations API 的伺服器位在 192.243.224.0/20 IP 位址 CIDR 區塊中。

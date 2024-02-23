---
keywords: IP 位址;IP 位址;合格清單;允許清單;防火牆;recs;摘要;伺服器;adobe marketing cloud;recommendations
description: 檢視用於 [!DNL Target] Recommendations 摘要處理伺服器的 IP 位址清單，協助您將防火牆設定為允許來自 Adobe 伺服器的 IP 位址。
title: Recommendations 摘要處理伺服器使用哪些 IP 位址？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: 558de92e672c276474bc76fad19e5461ae7d4c88
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 49%

---

# 使用的IP位址 [!DNL Recommendations] 摘要處理伺服器

使用的IP位址清單 [!DNL Adobe Target] [!DNL Recommendations] 摘要處理伺服器可協助您將防火牆設定為允許來自的IP位址 [!DNL Adobe] 伺服器。

>[!IMPORTANT]
>
>2023年2月23日： [!DNL Target] 群組目前正在更新要下載的NAT閘道位址 [!DNL Recommendations] 摘要。 如果您實施IP允許清單，請確定您允許清單下列新的AWS主機。 現有主機已排程在未來停止服務。 所有九部主機現在都已運作。

[!DNL Target] [!UICONTROL Recommendations] 活動在存取客戶的 FTP 伺服器時會使用以下 AWS 主機：

**新主機**：

| 位置 | 主機 |
| --- | --- |
| 美國奧勒岡 | `52.40.124.129` |
| 美國奧勒岡 | `54.148.219.69` |
| 美國奧勒岡 | `54.189.208.212` |
| 美國奧勒岡 | `44.230.236.35` |
| 美國奧勒岡 | `54.190.78.243` |
| 美國奧勒岡 | `52.41.73.133` |

**現有主機**：

| 位置 | 主機 |
| --- | --- |
| 美國奧勒岡 | `44.241.237.28` |
| 美國奧勒岡 | `44.232.167.82` |
| 美國奧勒岡 | `52.41.252.205` |

[!DNL Target] [!UICONTROL Recommendations] API 也會使用相同的 AWS 主機。

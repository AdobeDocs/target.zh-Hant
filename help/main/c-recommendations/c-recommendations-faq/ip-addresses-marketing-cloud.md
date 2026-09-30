---
keywords: IP 位址;IP 位址;合格清單;允許清單;防火牆;recs;摘要;伺服器;adobe marketing cloud;推薦
description: 檢視用於[!DNL Target] Recommendations摘要處理伺服器的IP位址清單，協助您將防火牆設定為允許源自Adobe伺服器的IP位址。
title: 推薦摘要處理伺服器使用哪些 IP 位址？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
TQID: 'https://experienceleague.adobe.com/-EhfjK6jTuHX33utQig-XYhf-nzkWlxb58VRmK9fLWo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 19%
---
# [!DNL Recommendations]個摘要處理伺服器使用的IP位址

[!DNL Adobe Target] [!DNL Recommendations]摘要處理伺服器中使用的IP位址清單，可協助您將防火牆設定為允許來自[!DNL Adobe]伺服器的IP位址。

>[!IMPORTANT]
>
>[!DNL Target]團隊目前正在更新NAT閘道位址，以便下載[!DNL Recommendations]摘要。 如果您實施IP允許清單，請確定您允許清單下列新的AWS主機。 現有主機預計於2024年6月30日停止服務。 為確保順利轉換，請將所有九個地址加入允許清單。 移除現有位址並不緊迫。

存取客戶的FTP伺服器時，[!DNL Target]個[!UICONTROL Recommendations]活動會使用下列AWS主機：

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

[!DNL Target] [!UICONTROL 建議] API也使用相同的AWS主機。

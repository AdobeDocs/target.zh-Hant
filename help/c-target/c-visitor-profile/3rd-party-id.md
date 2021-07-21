---
keywords: mbox;mbox3rdPartyId;設定檔同步中;設定檔同步;PCID
description: 了解如何使用mbox3rdPartyId（即您組織的訪客ID），例如會籍ID或您組織的忠誠計畫。
title: 如何對mbox3rdPartyId使用即時設定檔同步？
feature: 對象
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: c19163020cdcb41a17ea6b65b5b500fadc9c7512
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 61%

---

# mbox3rdPartyId 的即時設定檔同步

[!DNL Adobe Target]中的mbox3rdPartyId為公司的訪客ID，例如公司忠誠計畫的會員ID。

當訪客登入某個公司的網站時，該公司通常會建立 ID，此 ID 會連結至該訪客的帳戶、常客卡、會員編號或適用於該公司的其他識別碼。

當訪客存取已啟用 [!DNL Target] 的頁面時，該訪客會獲派 [!DNL Target] PCID。如果訪客隨後登入，且實作將 mbox3rdPartyId 傳給 [!DNL Target]，[!DNL Target] 即會將該訪客的 mbox3rdPartyId 連結至 [!DNL Target] PCID。

每隔 3 到 5 分鐘，系統就會將更新同步至資料庫。當訪客登出時，合併的資料會取代與mbox3rdPartyId相關聯的先前資料，並建立該訪客動作的完整記錄。 如果兩個 ID 中存在相同的屬性，例如 PCID 具有 category=hats，而 mbox3rdPartyId 具有 category=skis，或者，訪客在登入前看到體驗 A，但 mbox3rdPartyId 中儲存體驗 B，則 mbox3rdPartyId 中儲存的屬性會覆寫 PCID 中的屬性。如果訪客在登入前位於某個活動或體驗中，但 mbox3rdPartyId 中儲存另一個活動和體驗，則在登入後，該訪客會安排到 mbox3rdPartyId 活動和體驗中。

| PCID (未登入) | mbox3rdPartyId (已登入) | 已合併且儲存至 mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活動 1、體驗 A | 活動 1、體驗 B | 活動 1、體驗 B |
| 活動 1 |  | 活動 1 |

訪客登出時，仍維持合併的描述檔。

>[!NOTE]
>
>如果您想要區分已驗證（登入）使用者與非已驗證使用者，請使用[!DNL Adobe Experience Cloud Identity Service](ECID)，而非mbox3rdPartyID。 使用者與mbox3rdPartyID建立關聯後，即使登出後，仍會維持與使用者關聯。

>[!NOTE]
>
>[!DNL Adobe Analytics] 在ID(EDID)變更( [!DNL Adobe Experience Cloud] 例如訪客變更裝置)的情況下，系統不會追蹤目標，即使 [!DNL Target] 可能已根據mbox3rdPartyId合併設定檔且仍有活動資訊，也是如此。若為已識別具有相同EDID的訪客（使用相同裝置存取頁面的訪客）,[!DNL Analytics for Target](A4T)應可如運期般運作。

## 考量事項 {#considerations}

如果您的頁面包含多個mbox且只有部分使用3rdPartyID,[!DNL Target]沒有適用於每個訪客請求的個別訪客設定檔/內容。 3rdPartyID 內容的優先順序高於 PCID 內容。一個 mbox 只要傳送 3rdPartyId，即可讓其內容的優先順序高於 PCID。

例如，假設訪客在登入前存取了頁面並看到體驗。 全域 mbox 不會使用 3rdPartyID。登入後，訪客看到三個具有子項 mbox 的體驗之一，其中某些使用 3rdPartyID。訪客造訪網站上的各個頁面，然後使用返回按鈕回到登入前所存取的主要頁面，且看到某個不同的體驗。在此案例中，全域 mbox 並未傳送 3rdPartyID，但一或多個子項 mbox 已這麼做。3rdPartyID 的優先順序高於 PCID。

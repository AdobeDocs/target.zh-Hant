---
keywords: mbox;mbox3rdPartyId;設定檔同步中;設定檔同步;PCID
description: 瞭解如何使用mbox3rdPartyId，即您組織的訪客ID，例如會籍ID或您組織的忠誠度方案。
title: 我要如何使用mbox3rdPartyId的即時描述檔同步？
feature: Audiences
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 76%

---


# mbox3rdPartyId 的即時設定檔同步{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyId 為公司的訪客 ID，例如公司忠誠計劃的會員 ID。

當訪客登入某個公司的網站時，該公司通常會建立 ID，此 ID 會連結至該訪客的帳戶、常客卡、會員編號或適用於該公司的其他識別碼。

當訪客存取已啟用 [!DNL Target] 的頁面時，該訪客會獲派 [!DNL Target] PCID。如果訪客隨後登入，且實作將 mbox3rdPartyId 傳給 [!DNL Target]，[!DNL Target] 即會將該訪客的 mbox3rdPartyId 連結至 [!DNL Target] PCID。

每隔 3 到 5 分鐘，系統就會將更新同步至資料庫。當訪客登出時，合併的資料會取代與 mbox3rdPartyId 關聯的舊資料，並為該訪客的活動建立更完整的記錄。如果兩個 ID 中存在相同的屬性，例如 PCID 具有 category=hats，而 mbox3rdPartyId 具有 category=skis，或者，訪客在登入前看到體驗 A，但 mbox3rdPartyId 中儲存體驗 B，則 mbox3rdPartyId 中儲存的屬性會覆寫 PCID 中的屬性。如果訪客在登入前位於某個活動或體驗中，但 mbox3rdPartyId 中儲存另一個活動和體驗，則在登入後，該訪客會安排到 mbox3rdPartyId 活動和體驗中。

| PCID (未登入) | mbox3rdPartyId (已登入) | 已合併且儲存至 mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活動 1、體驗 A | 活動 1、體驗 B | 活動 1、體驗 B |
| 活動 1 |  | 活動 1 |

訪客登出時，仍維持合併的描述檔。

>[!NOTE]
>
>如果您想要區分已驗證（登入）的使用者與非驗證的使用者，請使用Adobe Experience Cloud Identity Service(ECID)，而非mbox3rdPartyID。 在使用者與mbox3rdPartyID建立關聯後，即使在登出後，它仍會與使用者建立關聯。

>[!NOTE]
>
>[!DNL Adobe Analytics] 當 [!DNL Adobe Experience Cloud] ID(EDID)變更（例如訪客變更裝置）時，即使描述檔可能會根據mbox3rdPartyId進行合併，但 [!DNL Target] 仍有活動資訊，也不會追蹤目標。對於使用相同EDID（使用相同裝置存取頁面的訪客）識別的訪客，[!DNL Analytics for Target](A4T)應如預期般運作。

## 考量事項 {#considerations}

如果頁面包含多個 mbox 且只有一些使用 3rdPartyID，Target 不會有適用於各個訪客要求的個別訪客設定檔/內容。3rdPartyID 內容的優先順序高於 PCID 內容。一個 mbox 只要傳送 3rdPartyId，即可讓其內容的優先順序高於 PCID。

例如，假設訪客在登入前存取頁面且看到某個體驗。全域 mbox 不會使用 3rdPartyID。登入後，訪客看到三個具有子項 mbox 的體驗之一，其中某些使用 3rdPartyID。訪客造訪網站上的各個頁面，然後使用返回按鈕回到登入前所存取的主要頁面，且看到某個不同的體驗。在此案例中，全域 mbox 並未傳送 3rdPartyID，但一或多個子項 mbox 已這麼做。3rdPartyID 的優先順序高於 PCID。

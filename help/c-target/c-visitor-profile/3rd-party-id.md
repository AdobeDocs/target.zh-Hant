---
description: mbox3rdPartyID 為公司的訪客 ID，例如公司忠誠計劃的會員 ID。
keywords: mbox;mbox3rdPartyID;設定檔同步中;設定檔同步
seo-description: mbox3rdPartyID 為公司的訪客 ID，例如公司忠誠計劃的會員 ID。
seo-title: mbox3rdPartyID 的即時設定檔同步
solution: Target
title: mbox3rdPartyID 的即時設定檔同步
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 17f0612559bae335d261ebc7654bc5d7fe3c0d12

---


# mbox3rdPartyID 的即時設定檔同步{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyID 為公司的訪客 ID，例如公司忠誠計劃的會員 ID。

當訪客登入某個公司的網站時，該公司通常會建立 ID，此 ID 會連結至該訪客的帳戶、常客卡、會員編號或適用於該公司的其他識別碼。

當訪客存取已啟用 Target 的頁面時，該訪客會獲派 Target PCID。如果訪客隨後登入，且實作將 mbox3rdPartyID 傳給 Target，Target 即會將該訪客的 mbox3rdPartyID 與 Target PCID 結合。

每隔 3 到 5 分鐘，系統就會將更新同步至資料庫。當訪客登出時，合併的資料會取代與 mbox3rdPartyID 關聯的舊資料，並為該訪客的活動建立更完整的記錄。如果兩個 ID 中存在相同的屬性，例如 PCID 具有 category=hats，而 mbox3rdPartyID 具有 category=skis，或者，訪客在登入前看到體驗 A，但 mbox3rdPartyID 中儲存體驗 B，則 mbox3rdPartyID 中儲存的屬性會覆寫 PCID 中的屬性。如果訪客在登入前位於某個活動或體驗中，但 mbox3rdPartyID 中儲存另一個活動和體驗，則在登入後，該訪客會安排到 mbox3rdPartyID 活動和體驗中。

| PCID (未登入) | mbox3rdPartyID (登入) | 合併且儲存至 mbox3rdPartyID |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活動 1、體驗 A | 活動 1、體驗 B | 活動 1、體驗 B |
| 活動 1 |  | 活動 1 |

訪客登出時，仍維持合併的描述檔。

>[!NOTE]
>
>[!DNL Adobe Analytics] 無法在 [!DNL Adobe Experience Cloud] ID(MID)變更的情況下追蹤目標(例如，訪客變更裝置)，即使 [!DNL Target] 設定檔可能根據mbox3rdPartyId合併，仍具有活動資訊。對於以相同MID識別的訪客(存取相同裝置的頁面)， [!DNL Analytics for Target] (A4T)應如預期般運作。

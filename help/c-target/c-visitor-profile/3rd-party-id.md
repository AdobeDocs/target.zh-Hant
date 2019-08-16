---
description: mbox3rdPartyID 為公司的訪客 ID，例如公司忠誠計劃的會員 ID。
keywords: mbox;mbox3rdPartyID;設定檔同步中;設定檔同步；PCID
seo-description: '即時設定檔的相關資訊 '
seo-title: Adobe Target中mbox3 rdPartyId的即時描述檔同步
solution: Target
title: mbox3rdPartyID 的即時設定檔同步
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 647776170531230a0d0f0aa3d97565fbb75bc963

---


# mbox3rdPartyID 的即時設定檔同步{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyID 為公司的訪客 ID，例如公司忠誠計劃的會員 ID。

當訪客登入某個公司的網站時，該公司通常會建立 ID，此 ID 會連結至該訪客的帳戶、常客卡、會員編號或適用於該公司的其他識別碼。

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyID to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyID with the [!DNL Target] PCID.

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
>在 [!DNL Adobe Experience Cloud] ID (MID) 變更 (例如訪客變更裝置) 的情況下，系統不會追蹤 [!DNL Adobe Analytics] 目標，即使可能已根據 mbox3rdPartyID 合併 [!DNL Target] 設定檔且仍有活動資訊，也是如此。若為已識別具有相同 MID 的訪客 (使用同一部裝置存取頁面的訪客)，[!DNL Analytics for Target] (A4T) 應該會如運期般運作。

## 考量事項 {#considerations}

如果您的頁面包含數個mbox，而只有部分mbox使用3rdPartyId，則Target對每個訪客請求沒有個別的訪客資料/上下文。3rdPartyId上下文優先於PCID上下文。一個mbox可以傳遞3rdPartyId讓其上下文優先於PCID。

例如，假設訪客在登入之前存取頁面並查看體驗。全域mbox不會使用3rdPartyId。登入後，訪客會看到其中一個具有子mbox的體驗，其中有些會使用3rdPartyId。訪客瀏覽網站上的各頁面，然後使用「上一步」按鈕返回存取前存取的主頁面，並查看不同的體驗。在此情況下，全域mbox未通過3rdPartyId，但一個或多個子mbox已執行。3rdPartyId優先於PCID。

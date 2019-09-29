---
description: mbox3rdPartyId是您公司的訪客ID，例如您公司忠誠度方案的會籍ID。
keywords: mbox;mbox3rdPartyId；描述檔同步；描述檔同步；PCID
seo-description: '即時描述檔的相關資訊 '
seo-title: 在Adobe target中即時同步mbox3rdPartyId的描述檔
solution: Target
title: mbox3rdPartyId的即時描述檔同步
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: f54dba622e449fb8dac44cb37ff711419f8eda4b

---


# Real-time profile syncing for mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyId是您公司的訪客ID，例如您公司忠誠度方案的會籍ID。

當訪客登入某個公司的網站時，該公司通常會建立 ID，此 ID 會連結至該訪客的帳戶、常客卡、會員編號或適用於該公司的其他識別碼。

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyId to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyId with the [!DNL Target] PCID.

每隔 3 到 5 分鐘，系統就會將更新同步至資料庫。當訪客登出時，合併的資料會取代與mbox3rdPartyId關聯的先前資料，以建立該訪客動作的更完整記錄。 如果兩個ID中都有相同的屬性——例如，PCID有category=hats，而mbox3rdPartyId有category=skis，或如果訪客在登入前看到體驗A，但體驗B儲存在mbox3rdPartyId中——儲存在mbox3rdPartyId中的屬性會覆寫PCID中的屬性。 如果訪客在登入前曾經處於某個活動或體驗中，但mbox3rdPartyId中儲存了不同的活動和體驗，則在登入後該訪客會被放入mbox3rdPartyId活動和體驗。

| PCID (未登入) | mbox3rdPartyId（登入） | 合併並儲存至mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活動 1、體驗 A | 活動 1、體驗 B | 活動 1、體驗 B |
| 活動 1 |  | 活動 1 |

訪客登出時，仍維持合併的描述檔。

>[!NOTE]
>
>[!DNL Adobe Analytics] 當 [!DNL Adobe Experience Cloud][!DNL Target] ID(MID)變更（例如訪客變更裝置）時，即使描述檔可能會根據mbox3rdPartyId合併，但仍有活動資訊，也不會追蹤目標。 若為已識別具有相同 MID 的訪客 (使用同一部裝置存取頁面的訪客)，[!DNL Analytics for Target] (A4T) 應該會如運期般運作。

## 考量事項 {#considerations}

如果您的頁面包含數個mbox，且只有部分使用3rdPartyID，則Target對於每個訪客請求沒有個別的訪客資料／內容。 第3rdPartyID上下文優先於PCID上下文。 只要有一個mbox傳遞第3rdPartyId，其內容就足以優先於PCID。

例如，假設訪客在登入前存取頁面，並看到體驗。 全域mbox不使用3rdPartyID。 登入後，訪客會看到子mbox的3種體驗之一，其中有些使用3rdPartyID。 訪客瀏覽了網站上的不同頁面，然後使用「上一步」按鈕返回登入前存取的首頁面，並看到不同的體驗。 在此案例中，全域mbox未通過3rdPartyID，但有一或多個子mbox已通過。 第三方ID優先於PCID。

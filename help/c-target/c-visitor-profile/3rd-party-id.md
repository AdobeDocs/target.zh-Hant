---
description: mbox3rdPartyId是貴公司的訪客ID，例如貴公司忠誠度計劃的會籍ID。
keywords: mbox；mbox3rdPartyId；描述檔同步；描述檔同步；PCID
seo-description: '即時設定檔的相關資訊 '
seo-title: Adobe Target中mbox3 rdPartyId的即時描述檔同步
solution: Target
title: mbox3 rdPartyId的即時描述檔同步
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: f54dba622e449fb8dac44cb37ff711419f8eda4b

---


# Real-time profile syncing for mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyId是貴公司的訪客ID，例如貴公司忠誠度計劃的會籍ID。

當訪客登入某個公司的網站時，該公司通常會建立 ID，此 ID 會連結至該訪客的帳戶、常客卡、會員編號或適用於該公司的其他識別碼。

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyId to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyId with the [!DNL Target] PCID.

每隔 3 到 5 分鐘，系統就會將更新同步至資料庫。當訪客登出時，合併資料會取代與mbox3rdPartyId關聯的先前資料，為該訪客的動作建立更完整的記錄。如果兩個ID中的相同屬性存在—例如，PCID有category= hats和mbox3rdPartyId has category= skis，或者如果訪客在登入之前看見體驗A，但體驗B儲存在mbox3rdPartyId中—儲存於mbox3rdPartyId中的屬性會覆寫PCID的屬性。如果訪客在登入之前是處於某個活動或體驗中，但在登入mbox3rdPartyId後，會將不同的活動和體驗儲存在mbox3rdPartyId活動和體驗中。

| PCID (未登入) | mbox3rdPartyId(登入) | 合併並儲存至mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活動 1、體驗 A | 活動 1、體驗 B | 活動 1、體驗 B |
| 活動 1 |  | 活動 1 |

訪客登出時，仍維持合併的描述檔。

>[!NOTE]
>
>[!DNL Adobe Analytics] 無法在 [!DNL Adobe Experience Cloud] ID(MID)變更的情況下追蹤目標(例如，訪客變更裝置)，即使 [!DNL Target] 設定檔可能根據mbox3rdPartyId合併，仍具有活動資訊。若為已識別具有相同 MID 的訪客 (使用同一部裝置存取頁面的訪客)，[!DNL Analytics for Target] (A4T) 應該會如運期般運作。

## 考量事項 {#considerations}

如果您的頁面包含數個mbox，而只有部分mbox使用3rdPartyId，則Target對每個訪客請求沒有個別的訪客資料/上下文。3rdPartyId上下文優先於PCID上下文。一個mbox可以傳遞3rdPartyId讓其上下文優先於PCID。

例如，假設訪客在登入之前存取頁面並查看體驗。全域mbox不會使用3rdPartyId。登入後，訪客會看到其中一個具有子mbox的體驗，其中有些會使用3rdPartyId。訪客瀏覽網站上的各頁面，然後使用「上一步」按鈕返回存取前存取的主頁面，並查看不同的體驗。在此情況下，全域mbox未通過3rdPartyId，但一個或多個子mbox已執行。3rdPartyId優先於PCID。

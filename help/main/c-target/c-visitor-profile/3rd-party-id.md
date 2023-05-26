---
keywords: mbox;mbox3rdPartyId;設定檔同步中;設定檔同步;PCID
description: 瞭解如何使用mbox3rdPartyId，這是您組織的訪客ID，例如會籍ID或您組織的忠誠度計畫。
title: 如何對mbox3rdPartyId使用即時設定檔同步？
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 21%

---

# mbox3rdPartyId 的即時設定檔同步

此 `mbox3rdPartyId` 在 [!DNL Adobe Target] 是您公司的訪客ID，例如您公司的忠誠度計畫的會員ID。

當訪客登入某個公司的網站時，該公司通常會建立 ID，此 ID 會連結至該訪客的帳戶、常客卡、會員編號或適用於該公司的其他識別碼。

當訪客存取已啟用 [!DNL Target] 的頁面時，該訪客會獲派 [!DNL Target] PCID。如果訪客隨後登入，且實作通過 `mbox3rdPartyId` 至 [!DNL Target]， [!DNL Target] 連結該訪客的 `mbox3rdPartyId` 使用 [!DNL Target] PCID。

每5-10分鐘會和設定檔存放區同步更新。 當訪客的工作階段結束時，合併的資料會取代與相關的先前資料 `mbox3rdPartyId`，建立該訪客動作的完整記錄。 如果兩個ID中存在相同的屬性 — 例如，PCID具有category=hats和 `mbox3rdPartyId` 具有category=skis，或如果訪客在登入前看到體驗A，但體驗B儲存在 `mbox3rdPartyId` — 儲存在 `mbox3rdPartyId` 覆寫PCID中的屬性。 如果訪客在登入前位於某個活動或體驗中，但不同的活動和體驗會儲存在 `mbox3rdPartyId`，登入後，該訪客會獲分配至 `mbox3rdPartyId` 活動和體驗。

| PCID (未登入) | mbox3rdPartyId (已登入) | 已合併且儲存至 mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活動 1、體驗 A | 活動 1、體驗 B | 活動 1、體驗 B |
| 活動 1 |  | 活動 1 |

訪客登出時，仍維持合併的描述檔。

>[!NOTE]
>
>如果您想要區分已驗證（登入）使用者與非驗證使用者，請使用 [!DNL Adobe Experience Cloud Identity Service] (ECID)而非mbox3rdPartyID。 使用者與mbox3rdPartyID建立關聯後，即使登出後，仍會維持與使用者建立關聯。

>[!NOTE]
>
>[!DNL Adobe Analytics] 在以下情況下，不會追蹤目標 [!DNL Adobe Experience Cloud] ID (ECID)會變更（例如訪客變更裝置），即使 [!DNL Target] 設定檔可能會根據mbox3rdPartyId合併，並且仍有活動資訊。 對於以相同ECID識別的訪客（使用相同裝置存取頁面的訪客）， [!DNL Analytics for Target] (A4T)應該會如預期般運作。

## 考量事項 {#considerations}

* 如果您的頁面包含多個mbox且只有部分使用 `3rdPartyID`， [!DNL Target] 沒有適用於每個訪客請求的個別訪客設定檔/內容。 此 `3rdPartyID` 前後關聯優先於PCID前後關聯。 只要一個mbox就能通過 `3rdPartyId` 使其內容優先於PCID。

   例如，假設訪客在登入前存取頁面且看到某個體驗。 全域 mbox 不會使用 `3rdPartyID`. 登入後，訪客看到三個具有子項 mbox 的體驗之一，其中某些使用 `3rdPartyID`. 訪客造訪網站上的各個頁面，然後使用返回按鈕回到登入前所存取的主要頁面，且看到某個不同的體驗。在此案例中，全域mbox未通過 `3rdPartyID`，但有一或多個子mbox有。 `3rdPartyID` 優先順序高於PCID。

* 您可以將訪客的客戶ID傳送至 [!DNL Target] 使用兩種方法：

   1. 使用 `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` 是您使用時的引數名稱 `targetPageParams` 或 `targetPageParamsAll`
      * `thirdPartyId` 是您直接在傳送API裝載中設定的引數名稱。
      * 您只能在此引數中傳送一個值。
   1. 使用 `setCustomerId`/`customerIds` ECID服務的函式。

      * `setCustomerId` 是當頁面上有VisitorAPI.js可用時，您可在使用者端（瀏覽器）實作中使用的函式。
      * `customerIds` 是您直接在傳送API裝載中設定引數時使用的引數名稱，通常會在伺服器端或IOT （物聯網）實施上完成。
      * 取消讚 `mbox3rdPartyId`/`thirdPartyId`，您可以在此方法中以清單形式傳送多個ID，但這是因為 [!DNL Target] 每個TnT ID僅支援單一客戶ID，會使用清單中具有已知別名（在客戶屬性UI中設定的別名）的第一個ID。

   您可以使用 `mbox3rdPartyId`/`thirdPartyId` 如果 [!DNL Target] 是您唯一的 [!DNL Adobe Experience Cloud] 解決方案，而您不想使用客戶屬性。 對於所有其他情況，我們建議您使用 `setCustomerId`/`customerIds` 用於傳送客戶ID。

   >[!IMPORTANT]
   >
   > 對單一訪客交替使用上述兩種方法，可能會導致未驗證和已驗證的設定檔合併不正確 [!DNL Target] 設定檔。
   >
   >Adobe不建議您同時使用兩者 `mbox3rdPartyId`/`thirdPartyId` 和 `setCustomerID`/`customerIds` 一起。
   >
   >如果您必須交替使用這兩種方法，請確定使用的清單中的第一個ID `setCustomerID`/`customerIds` 的使用者為 `thirdPartyId`/`mbox3rdPartyId` 反之亦然。


---
keywords: mbox;mbox3rdPartyId;設定檔同步中;設定檔同步;PCID
description: 了解如何使用mbox3rdPartyId（即您組織的訪客ID），例如會籍ID或您組織的忠誠計畫。
title: 如何對mbox3rdPartyId使用即時設定檔同步？
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 47772ebbdec10f78ec120d2e4437eccad969b338
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 24%

---

# mbox3rdPartyId 的即時設定檔同步

此 `mbox3rdPartyId` in [!DNL Adobe Target] 是您公司的訪客ID，例如公司忠誠計畫的會員ID。

當訪客登入某個公司的網站時，該公司通常會建立 ID，此 ID 會連結至該訪客的帳戶、常客卡、會員編號或適用於該公司的其他識別碼。

當訪客存取已啟用 [!DNL Target] 的頁面時，該訪客會獲派 [!DNL Target] PCID。如果訪客隨後登入，且實作通過 `mbox3rdPartyId` to [!DNL Target], [!DNL Target] 連結該訪客的 `mbox3rdPartyId` 和 [!DNL Target] PCID。

每隔 3 到 5 分鐘，系統就會將更新同步至資料庫。當訪客登出時，合併的資料會取代與 `mbox3rdPartyId`，建立該訪客動作的完整記錄。 如果兩個ID中都存在相同的屬性，例如，PCID具有category=hats，且 `mbox3rdPartyId` 有category=skis，或如果訪客在登入前看到體驗A，但體驗B儲存在 `mbox3rdPartyId` — 儲存在 `mbox3rdPartyId` 覆寫PCID中的屬性。 如果訪客在登入前位於某個活動或體驗中，但中儲存的活動和體驗不同 `mbox3rdPartyId`，在登入後，該訪客會放入 `mbox3rdPartyId` 活動和體驗。

| PCID (未登入) | mbox3rdPartyId (已登入) | 已合併且儲存至 mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| 活動 1、體驗 A | 活動 1、體驗 B | 活動 1、體驗 B |
| 活動 1 |  | 活動 1 |

訪客登出時，仍維持合併的描述檔。

>[!NOTE]
>
>如果您想要區分已驗證（登入）使用者與非已驗證使用者，請使用 [!DNL Adobe Experience Cloud Identity Service] (ECID)，而非mbox3rdPartyID。 使用者與mbox3rdPartyID建立關聯後，即使登出後，仍會維持與使用者關聯。

>[!NOTE]
>
>[!DNL Adobe Analytics] 在 [!DNL Adobe Experience Cloud] ID(ECID)變更（例如訪客變更裝置），即使 [!DNL Target] 設定檔可能會根據mbox3rdPartyId合併，且仍有活動資訊。 若為已識別具有相同ECID的訪客（使用相同裝置存取頁面的訪客）, [!DNL Analytics for Target] (A4T)應可如預期般運作。

## 考量事項 {#considerations}

* 如果您的頁面包含數個mbox，且只有部分使用 `3rdPartyID`, [!DNL Target] 沒有適用於每個訪客請求的個別訪客設定檔/內容。 此 `3rdPartyID` 內容優先於PCID內容。 一個mbox就足以傳遞 `3rdPartyId` 讓其內容優先於PCID。

   例如，假設訪客在登入前存取了頁面並看到體驗。 全域 mbox 不會使用 `3rdPartyID`. 登入後，訪客看到三個具有子項 mbox 的體驗之一，其中某些使用 `3rdPartyID`. 訪客造訪網站上的各個頁面，然後使用返回按鈕回到登入前所存取的主要頁面，且看到某個不同的體驗。此情境中，全域mbox未傳遞 `3rdPartyID`，但有一或多個子項mbox確實如此。 `3rdPartyID` 優先於PCID。

* 您可以將訪客的客戶ID傳送至 [!DNL Target] 使用兩種方法：

   1. 使用 `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` 是參數名稱，當您使用 `targetPageParams` 或 `targetPageParamsAll`
      * `thirdPartyId` 是您在傳送API裝載中直接設定的參數名稱。
      * 您只能在此參數中傳送一個值。
   1. 使用 `setCustomerId`/`customerIds` ECID服務的函式。

      * `setCustomerId` 是函式，當頁面上有VisitorAPI.js時，您可在用戶端（瀏覽器）實作上使用。
      * `customerIds` 是您直接在「傳送API」裝載中設定參數名稱時使用的參數名稱，通常是在伺服器端或IOT（物聯網）實施上完成。
      * 不同於 `mbox3rdPartyId`/`thirdPartyId`，您可以在此方法中以清單的形式傳送多個ID，但 [!DNL Target] 每個TnT ID僅支援一個客戶ID，它使用清單中的第一個ID，具有已知別名（在客戶屬性UI中配置別名）。

   >[!IMPORTANT]
   >
   > 對單一訪客交替使用上述兩種方法，可能會導致未驗證和已驗證的設定檔合併不正確 [!DNL Target] 設定檔。
   >
   >Adobe不建議您同時使用 `mbox3rdPartyId`/`thirdPartyId` 和 `setCustomerID`/`customerIds` 一起。
   >
   >如果您必須交互使用這兩種方法，請確定所使用清單中的第一個ID `setCustomerID`/`customerIds` 是使用的 `thirdPartyId`/`mbox3rdPartyId` 反之亦然。


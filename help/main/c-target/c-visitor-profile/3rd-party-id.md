---
keywords: mbox;mbox3rdPartyId;設定檔同步中;設定檔同步;PCID
description: 瞭解如何使用mbox3rdPartyId（組織的訪問者ID），如成員資格ID或組織的忠誠計畫。
title: 如何使用mbox3rdPartyId的即時配置檔案同步？
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 21%

---

# mbox3rdPartyId 的即時設定檔同步

的 `mbox3rdPartyId` 在 [!DNL Adobe Target] 是您公司的訪問者ID，如您公司的忠誠計畫的成員身份ID。

當訪客登入某個公司的網站時，該公司通常會建立 ID，此 ID 會連結至該訪客的帳戶、常客卡、會員編號或適用於該公司的其他識別碼。

當訪客存取已啟用 [!DNL Target] 的頁面時，該訪客會獲派 [!DNL Target] PCID。如果訪問者隨後登錄，且實施通過 `mbox3rdPartyId` 至 [!DNL Target]。 [!DNL Target] 把訪客的 `mbox3rdPartyId` 和 [!DNL Target] PCID

更新每5-10分鐘與配置檔案儲存同步一次。 訪問者會話結束時，合併的資料將替換與 `mbox3rdPartyId`，建立該訪問者的完整操作記錄。 如果兩個ID中都存在相同的屬性，例如，PCID具有category=hats和 `mbox3rdPartyId` has category=skis，或如果訪問者在登錄前看到體驗A，但體驗B儲存在 `mbox3rdPartyId` — 儲存在 `mbox3rdPartyId` 覆蓋PCID中的屬性。 如果訪問者在登錄之前曾參與過一個活動或體驗，但是將不同的活動和體驗儲存在 `mbox3rdPartyId`，登錄後，該訪問者被安置在 `mbox3rdPartyId` 活動和經驗。

| PCID (未登入) | mbox3rdPartyId (已登入) | 已合併且儲存至 mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | 類別=滑雪板 |
|  | store=94103 | store=94103 |
| 活動 1、體驗 A | 活動 1、體驗 B | 活動 1、體驗 B |
| 活動 1 |  | 活動 1 |

訪客登出時，仍維持合併的描述檔。

>[!NOTE]
>
>如果要區分已驗證（已登錄）用戶與非已驗證用戶，請使用 [!DNL Adobe Experience Cloud Identity Service] (ECID)，而不是mbox3rdPartyID。 用戶與mbox3rdPartyID關聯後，即使在註銷後，它仍與用戶關聯。

>[!NOTE]
>
>[!DNL Adobe Analytics] 在目標 [!DNL Adobe Experience Cloud] ID(ECID)更改（例如，訪問者更改設備），即使 [!DNL Target] 配置檔案可能會基於mbox3rdPartyId合併，但仍然包含活動資訊。 對於使用相同ECID（使用相同設備訪問頁面的訪問者）, [!DNL Analytics for Target] (A4T)應按預期工作。

## 考量事項 {#considerations}

* 如果您的頁面包含多個框，並且僅使用 `3rdPartyID`。 [!DNL Target] 沒有每個訪問者請求的單獨訪問者配置檔案/上下文。 的 `3rdPartyID` 上下文優先於PCID上下文。 只要一個盒子就能通過 `3rdPartyId` 其上下文優先於PCID。

   例如，假設訪問者在登錄前訪問頁面並看到體驗。 全域 mbox 不會使用 `3rdPartyID`. 登入後，訪客看到三個具有子項 mbox 的體驗之一，其中某些使用 `3rdPartyID`. 訪客造訪網站上的各個頁面，然後使用返回按鈕回到登入前所存取的主要頁面，且看到某個不同的體驗。在此情況下，全局框未通過 `3rdPartyID`但有一個或多個孩子盒子。 `3rdPartyID` 優先於PCID。

* 您可以將訪問者的客戶ID發送到 [!DNL Target] 採用兩種方法：

   1. 使用 `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` 是使用時的參數名稱 `targetPageParams` 或 `targetPageParamsAll`
      * `thirdPartyId` 是您直接在傳遞API負載中設定的參數名。
      * 在此參數中只能發送一個值。
   1. 使用 `setCustomerId`/`customerIds` ECID服務的函式。

      * `setCustomerId` 是當VisitorAPI.js在頁面上可用時，可以在客戶端（瀏覽器）實現中使用的函式。
      * `customerIds` 是直接在Delivery API負載中設定它時使用的參數名稱，通常在伺服器端或IOT（物聯網）實現中完成。
      * 不像 `mbox3rdPartyId`/`thirdPartyId`，您可以在此方法中將多個ID作為清單發送，但是 [!DNL Target] 每個TnT Id只支援單個客戶ID，它使用清單中第一個ID和已知別名（在「客戶屬性UI」中配置的別名）。

   您可以使用 `mbox3rdPartyId`/`thirdPartyId` 如果 [!DNL Target] 你唯一 [!DNL Adobe Experience Cloud] 解決方案，您不想使用「客戶屬性」。 對於所有其他情況，我們建議您 `setCustomerId`/`customerIds` 發送客戶ID。

   >[!IMPORTANT]
   >
   > 對單個訪問者可交替使用上述兩種方法可能會導致未經驗證和經過身份驗證的配置檔案合併不正確 [!DNL Target] 配置檔案。
   >
   >Adobe不建議您同時使用 `mbox3rdPartyId`/`thirdPartyId` 和 `setCustomerID`/`customerIds` 一起。
   >
   >如果必須可替換地使用這兩種方法，請確保清單中使用的第一個ID `setCustomerID`/`customerIds` 是使用 `thirdPartyId`/`mbox3rdPartyId` 反之亦然。


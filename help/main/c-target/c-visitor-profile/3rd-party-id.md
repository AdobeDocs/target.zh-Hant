---
keywords: mbox;mbox3rdPartyId;輪廓同步中;輪廓同步;PCID
description: 瞭解如何使用mbox3rdPartyId，這是您組織的訪客ID，例如會籍ID或您組織的忠誠度計畫。
title: 如何對mbox3rdPartyId使用即時設定檔同步？
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 18%

---

# mbox3rdPartyId 的即時輪廓同步

`mbox3rdPartyId`中的[!DNL Adobe Target]是您公司的訪客ID，例如您公司的忠誠度計畫的會員ID。

當訪客登入某個公司的網站時，該公司通常會建立 ID，此 ID 會連結至該訪客的帳戶、常客卡、會員編號或適用於該公司的其他識別碼。

當訪客存取已啟用 [!DNL Target] 的頁面時，該訪客會獲派 [!DNL Target] PCID。如果訪客隨後登入，且實作將`mbox3rdPartyId`傳給[!DNL Target]，[!DNL Target]會將該訪客的`mbox3rdPartyId`與[!DNL Target] PCID連線。

每5-10分鐘會和設定檔存放區同步更新。 當訪客的工作階段結束時，合併的資料會取代與`mbox3rdPartyId`關聯的舊資料，以建立該訪客動作的完整記錄。 如果兩個ID中存在相同的屬性，例如PCID具有category=hats，而`mbox3rdPartyId`具有category=skis，或者，如果訪客在登入前看到體驗A，但體驗B儲存在`mbox3rdPartyId`中，則儲存在`mbox3rdPartyId`中的屬性會覆寫來自PCID的屬性。 如果訪客在登入前位於某個活動或體驗中，但另一個活動和體驗儲存在`mbox3rdPartyId`中，則登入後，該訪客會放入`mbox3rdPartyId`活動和體驗中。

| PCID (未登入) | mbox3rdPartyId (已登入) | 已合併且儲存至 mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|   | store=94103 | store=94103 |
| 活動 1、體驗 A | 活動 1、體驗 B | 活動 1、體驗 B |
| 活動 1 |  | 活動 1 |

訪客登出時，仍維持合併的描述檔。

>[!NOTE]
>
>若要區分已驗證（登入）使用者與未驗證使用者，請使用[!DNL Adobe Experience Cloud Identity Service] (ECID)而非mbox3rdPartyID。 使用者與mbox3rdPartyID建立關聯後，即使登出後，仍會維持與使用者建立關聯。

>[!NOTE]
>
>在[!DNL Adobe Analytics] ID (ECID)變更（例如訪客變更裝置）的情況下，系統不會追蹤[!DNL Adobe Experience Cloud]目標，即使可能已根據mbox3rdPartyId合併[!DNL Target]設定檔且仍有活動資訊，也是如此。 若為已識別具有相同ECID的訪客（使用相同裝置存取頁面的訪客），[!DNL Analytics for Target] (A4T)應該會如運期般運作。

## 考量事項 {#considerations}

* 如果您的頁面包含多個mbox且只有一些使用`3rdPartyID`，則[!DNL Target]不會針對每個訪客要求個別提供訪客設定檔/內容。 `3rdPartyID`內容優先於PCID內容。 一個mbox只要傳遞`3rdPartyId`，其內容就會優先於PCID。

  例如，假設訪客在登入前存取頁面且看到某個體驗。 全域mbox未使用`3rdPartyID`。 登入後，訪客看到三個具有子項mbox的體驗之一，其中某些使用`3rdPartyID`。 訪客造訪網站上的各個頁面，然後使用返回按鈕回到登入前所存取的主要頁面，且看到某個不同的體驗。在此案例中，全域mbox未傳遞`3rdPartyID`，但有一或多個子mbox傳遞。 `3rdPartyID`優先順序高於PCID。

* 您可以使用兩種方法將訪客的客戶ID傳送至[!DNL Target]：

   1. 使用`mbox3rdPartyId`/`thirdPartyId`。

      * 當您使用`mbox3rdPartyId`或`targetPageParams`時，`targetPageParamsAll`是引數名稱
      * `thirdPartyId`是您直接在傳送API裝載中設定的引數名稱。
      * 您只能在此引數中傳送一個值。

   1. 使用ECID服務的`setCustomerId`/`customerIds`函式。

      * `setCustomerId`是您可以在使用者端（瀏覽器）實施上使用的函式，當頁面上有VisitorAPI.js可用時。
      * `customerIds`是您直接在傳送API裝載中設定引數時使用的引數名稱，通常是在伺服器端或IOT （物聯網）實作上完成。
      * 與`mbox3rdPartyId`/`thirdPartyId`不同，您可以在此方法中以清單形式傳送多個ID，但由於[!DNL Target]僅支援每個TnT ID的單一客戶ID，因此會使用具有已知別名（在客戶屬性UI中設定的別名）的清單中的第一個ID。

  如果`mbox3rdPartyId`是您唯一的`thirdPartyId`解決方案，而且您不想使用客戶屬性，則可以使用[!DNL Target]/[!DNL Adobe Experience Cloud]。 對於所有其他情況，我們建議您使用`setCustomerId`/`customerIds`來傳送客戶ID。

  >[!IMPORTANT]
  >
  > 對單一訪客可交換使用上述兩種方法，可能會導致未驗證和已驗證的[!DNL Target]設定檔合併出現錯誤的設定檔合併。
  >
  >Adobe不建議您同時使用`mbox3rdPartyId`/`thirdPartyId`和`setCustomerID`/`customerIds`。
  >
  >如果您必須交替使用這兩種方法，請確定`setCustomerID`/`customerIds`使用的清單中的第一個ID是`thirdPartyId`/`mbox3rdPartyId`使用的專案，反之亦然。


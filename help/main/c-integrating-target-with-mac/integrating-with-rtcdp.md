---
keywords: Real-time Customer Data Platform;rtcdp；個人化；aep對象；adobe experience platform對象；設定檔屬性
description: 了解如何使用 [!DNL Target]/[!DNL Real-Time Customer Data Platform] (RTCDP) 整合服務，以提供更豐富的客戶資料和更有影響力的個人化功能。
title: 我如何整合  [!DNL Target] 和 [!DNL Real-Time Customer Data Platform]？
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 08422323607f7238a7cf9bac5b863032ce734662
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 49%

---

# 整合 [!DNL Real-Time Customer Data Platform]

內建 [!DNL Adobe Experience Platform], [!DNL Real-Time Customer Data Platform] (RTCDP)可協助公司匯集來自多個企業來源的已知和匿名資料。 RTCDP可讓您建立客戶設定檔，以便即時提供跨所有通道和裝置的個人化客戶體驗。

有關RTCDP的詳細資訊，請參見 [Real-time Customer Data Platform概述](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant){target=_blank}.

## 重要功能

重要功能包含：

* 直接 [!DNL Target] 整合Real-Time CDP/[!DNL Adobe Experience Platform] 在邊上(移除 [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge 目標卡]以及控管和政策執行
* Real-time CDP 區段和共用設定檔屬性

## 實作案例

下列小節顯示使用不同實施方法時可用的個人化使用案例類型（下次工作階段或同頁）:

### at.js 實施

| 解決方案 | 啟用使用案例 |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) 和 [!DNL Target]</li><li>[!DNL RTCDP] (Premium 或 Ultimate) 和 [!DNL Target]</li><li>[!DNL RTCDP] (任何 SKU)、[!DNL AAM] 和 [!DNL Target]</li></ul> | 下一個工作階段的個人化 |

### [!DNL Adobe Experience Platform Web SDK]或 [!DNL Experience Platform Server-Side API] 實作

| 解決方案 | 啟用使用案例 |
| --- | --- |
| <ul><li>[!DNL RTCDP] (任何 SKU) 和 [!DNL Target]</li></ul> | <ul><li>下一個工作階段的個人化</li><li>透過 Edge 進行同一頁面的個人化</li><li>共用區段時強制執行控管</li></ul> |
| <ul><li>[!DNL RTCDP] (任何 SKU)、[!DNL AAM] 和 [!DNL Target]</li></ul> | <ul><li>下一個工作階段的個人化</li><ul><li>[!DNL AAM] 區段</li><li>透過 [!DNL AAM] 進行第三方區段</li></ul><li>透過 Edge 進行同一頁面的個人化</li><ul><li>[!DNL RTCDP] 區段</li><li>共用區段時強制執行控管</li></ul> |

### 混合 [!UICONTROL at.js] 和 [!DNL Platform Web SDK] 實作

| 解決方案 | 啟用使用案例 |
| --- | --- |
| <ul><li>[!DNL RTCDP] (任何 SKU) 和 [!DNL Target]</li></ul> | <ul><li>下一個工作階段的個人化</li><ul><li>針對所有頁面和 [!UICONTROL at.js]</li></ul><li>同一頁面的個人化</li><ul><li>針對所有頁面和 [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] (任何 SKU)、[!DNL AAM] 和 [!DNL Target]</li></ul> | <ul><li>下一個工作階段的個人化</li><ul><li>針對所有頁面和 [!UICONTROL at.js]</li><li>[!DNL AAM] 區段</li><li>透過 [!DNL AAM] 進行第三方區段</li></ul> |

## 區段評估時間

下表顯示在不同實施場況發生事件的區段評估時間：

| 藍本 | Edge 區段 (毫秒評估) | 串流區段 (分鐘評估) | 批次區段評估 |
| --- | --- | --- | --- |
| 來自 [!DNL Adobe Experience Platform] SDK 的事件/資料 | 是 | 是 | 不適用 |
| 來自 [!UICONTROL at.js]的事件 | 無 | 是 | 不適用 |
| 來自 [!DNL Target Mobile] SDK 的事件 | 無 | 是 | 不適用 |
| 來自批次的事件 | 無 | 無 | 是 |
| 來自離線資料的事件 (串流) | 無 | 是 | 是 |

## 使用來自 [!DNL Adobe Experience Platform] 的對象 {#aep}

使用在 [!DNL Adobe Experience Platform] 中建立的[對象](/help/main/c-target/c-audiences/audiences.md)可提供更豐富的客戶資料，進而帶來更具影響力的個人化。 此 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant){target=_blank} (RTCDP)，建置於 [!DNL Adobe Experience Platform]，可協助公司匯集來自多個企業來源的已知和匿名資料。 此流程允許您建立客戶設定檔，並且可將這些設定檔用來即時提供跨所有管道和裝置的個人化客戶體驗。

通過連接 [!DNL Target] 到 [!DNL Real-Time Customer Data Platform]，客戶可讓其網頁個人化更加豐富。 此整合可讓您解除鎖定先前可能無法存取的新區段 [!DNL Target] 以在客戶網站造訪的第一頁上啟用即時毫秒個人化。 使用在 [!DNL Adobe Experience Platform] 中建立的對象和設定檔屬性，可讓您擴展更強個人化的可用資料點。

此整合可解鎖Real-Time CDP的重要使用案例：

* 同一頁面 / 下次點擊的個人化
* 第一次/不明使用者的個人化

## 共用Real-Time CDP設定檔屬性，與 [!DNL Target] {#rtcdp-profile-attributes}

Real-Time CDP設定檔屬性可與共用 [!DNL Target] 用於HTML選件和 [JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Real-Time CDP設定檔屬性功能限制和考量事項

>[!NOTE]
>
>Real-Time CDP設定檔屬性功能可在測試版取得，以取得HTML選件和 [JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md).

考慮以下事項：

* 指定選件內的屬性必須來自相同 [!UICONTROL Experience Platform] 沙箱。 (換句話說，選件不能包含來自不同 [!UICONTROL Experience Platform] 沙箱。)
* 指定選件中的屬性可能來自不同來源；即 [!DNL Target] 設定檔與 [!UICONTROL Experience Platform] 設定檔。 (換句話說，您可以結合屬性(無論屬性來自何種 [!DNL Target] 或 [!UICONTROL Experience Platform] 設定檔)。
* 定義選件時，您可以為 [!UICONTROL Real-Time CDP設定檔屬性]，則屬性沒有明確值。 例如，如果同意書或控管政策封鎖個人化服務內使用的屬性，則可以改用預設值。

### JSON範例使用案例

身為線上行銷人員，您希望AEP/統一設定檔與共用屬性值 [!DNL Target] 提供即時個人化。 使用 [!UICONTROL Real-Time CDP設定檔屬性]，則可顯示 [!UICONTROL Experience Platform] 屬性 [!DNL Target] 使用代號取代的選件。 例如，您可以根據客戶最喜歡使用的顏色 `${aep.profile.favoriteColor}`，或者他們使用代幣的忠誠度等級和忠誠度點值 `${aep.loyalty.tier}` 和 `${aep.loyalty.points}` 來進行個人化。

建立JSON選件以與共用AEP/統一設定檔屬性的方式 [!DNL Target]:

1. 同時 [建立JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)，從 **[!UICONTROL 選擇源]** 清單，選擇 **[!UICONTROL Adobe Experience Platform]**.
1. 從 **[!UICONTROL 選取設定檔沙箱名稱]** 清單中，選取所需的沙箱。
1. 從 **[!UICONTROL 選取設定檔屬性]** 清單中，選擇所需的屬性。
1. （選用）從 **[!UICONTROL 插入預設值]** 清單中，選擇所需值。
1. 按一下&#x200B;**[!UICONTROL 「新增」]**。

下圖顯示兩個設定檔屬性： `loyalty.tier` 和 `loyalty.points` 已新增至JSON選件。

![offer-json-aep-shared-attribute 圖像](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## 了解更多資訊的連結

如需詳細資訊，請參閱下列主題:

* [目標發行說明](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=zh-Hant#destinations){target=_blank} (在 *Adobe Experience Platform 發行說明*&#x200B;中)
* [為同一頁和下一頁個人化設定個人化目標](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} (在&#x200B;*目標概觀*&#x200B;指南中)。
* [Adobe Target 連接](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} (在&#x200B;*目標概觀*&#x200B;指南中)
* [映射屬性](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=en#map-attributes){target=_blank} 在 *目的地概觀* 指南。

## 影片和部落格文章

以下影片和部落格文章提供有關使用 Target 和 RTCDP 加強個人化的更多資訊：

### 影片：使用Real-Time CDP和 [!DNL Adobe Target]{#RTCDP}

了解如何使用 [!DNL Real-Time Customer Data Platform]和 [!DNL Adobe Target] 對下一次點擊進行個人化。 [!DNL Real-Time CDP] 中的 [!DNL Adobe Target] 目標可讓您將 [!DNL Adobe Target] 中的 [!DNL Experience Platform] 區段用於具有控管和隱私權支援的同一頁個人化和下一頁個人化。

如需詳細資訊，請參閱 [使用Real-Time CDP和Adobe Target進行下次點擊個人化](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html?lang=zh-Hant){target=_blank} 在 *平台Tutorials* 指南。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### [!DNL Adobe Target] 部落格和影片：同頁增強的個人化

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

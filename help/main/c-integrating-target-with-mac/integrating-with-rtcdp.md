---
keywords: Real-time Customer Data Platform;rtcdp；個人化；aep對象；adobe experience platform對象；設定檔屬性
description: 了解如何使用 [!DNL Target]/[!DNL Real-time Customer Data Platform] (RTCDP) 整合服務，以提供更豐富的客戶資料和更有影響力的個人化功能。
title: 我如何整合  [!DNL Target] 和 [!DNL Real-time Customer Data Platform]？
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: b31fc335c2066f74ec9aebe835a2c47822a49e5a
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 9%

---

# 整合 [!DNL Real-time Customer Data Platform]

內建 [!DNL Adobe Experience Platform], [!DNL Real-time Customer Data Platform] (RTCDP)可協助公司匯集來自多個企業來源的已知和匿名資料。 RTCDP可讓您建立客戶設定檔，以便即時提供跨所有通道和裝置的個人化客戶體驗。

有關RTCDP的詳細資訊，請參見 [Real-time Customer Data Platform概述](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant){target=_blank}.

## 使用對象來自 [!DNL Adobe Experience Platform] {#aep}

使用 [對象](/help/main/c-target/c-audiences/audiences.md) 建立於 [!DNL Adobe Experience Platform] 提供更豐富的客戶資料，進而實現更具影響力的個人化。 此 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant){target=_blank} (RTCDP)，建置於 [!DNL Adobe Experience Platform]，可協助公司匯集來自多個企業來源的已知和匿名資料。 此程式可讓您建立客戶設定檔，以用於即時提供跨所有管道和裝置的個人化客戶體驗。

通過連接 [!DNL Target] 到 [!DNL Real-time Customer Data Platform]，客戶可讓其網頁個人化更加豐富。 此整合可讓您解除鎖定先前可能無法存取的新區段 [!DNL Target] 以在客戶網站造訪的第一頁上啟用即時毫秒個人化。 使用中建立的對象和設定檔屬性 [!DNL Adobe Experience Platform] 可讓您展開可用的資料點，以便更豐富的個人化。

此整合可解鎖Real-time CDP的主要使用案例：

* 同頁/下次點擊個人化
* 首次/未知使用者個人化

### 主要功能

主要功能包括：

* 直接 [!DNL Target] 與Real-time CDP/整合[!DNL Adobe Experience Platform] 在邊上(移除 [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations卡] 與治理和政策執行
* Real-time CDP Segments和共用配置檔案屬性

### Personalization 使用案例

下列小節顯示使用不同實施方法時可用的個人化使用案例類型（下次工作階段或同頁）:

#### at.js 實施

| 解決方案 | 啟用使用案例 |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM)和 [!DNL Target]</li><li>[!DNL RTCDP] （Premium或Ultimate）和 [!DNL Target]</li><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]，和 [!DNL Target]</li></ul> | 下一工作階段個人化 |

#### Adobe Experience Platform Web SDK或Experience Platform伺服器端API實作

| 解決方案 | 啟用使用案例 |
| --- | --- |
| <ul><li>[!DNL RTCDP] （任何SKU）和 [!DNL Target]</li></ul> | <ul><li>下一工作階段個人化</li><li>透過Edge提供同頁個人化</li><li>共用區段時強制執行控管</li></ul> |
| <ul><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]，和 [!DNL Target]</li></ul> | <ul><li>下一工作階段個人化</li><ul><li>[!DNL AAM] 區段</li><li>透過 [!DNL AAM]</li></ul><li>透過Edge提供同頁個人化</li><ul><li>[!DNL RTCDP] 區段</li><li>共用區段時強制執行控管</li></ul> |

#### 混合 [!UICONTROL at.js] 和 [!DNL Platform Web SDK] 實施

| 解決方案 | 啟用使用案例 |
| --- | --- |
| <ul><li>[!DNL RTCDP] （任何SKU）和 [!DNL Target]</li></ul> | <ul><li>下一工作階段個人化</li><ul><li>對於具有 [!UICONTROL at.js]</li></ul><li>同頁個人化</li><ul><li>對於具有 [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]，和 [!DNL Target]</li></ul> | <ul><li>下一工作階段個人化</li><ul><li>對於具有 [!UICONTROL at.js]</li><li>[!DNL AAM] 區段</li><li>透過 [!DNL AAM]</li></ul> |

### 區段評估時間

下表顯示來自不同實施案例之事件的區段評估時間：

| 藍本 | 邊緣段（毫秒評估） | 串流區段（分鐘評估） | 批次區段評估 |
| --- | --- | --- | --- |
| 事件/資料來源 [!DNL Adobe Experience Platform] SDK | 是 | 是 | 不適用 |
| 來自 [!UICONTROL at.js] | 無 | 是 | 不適用 |
| 來自 [!DNL Target Mobile] SDK | 無 | 是 | 不適用 |
| 批次上傳的事件 | 無 | 無 | 是 |
| 來自離線資料（資料流）的事件 | 無 | 是 | 是 |

### 連結至更多資訊

如需詳細資訊，請參閱下列主題:

* [目的地發行說明](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} 在 *Adobe Experience Platform發行說明*
* [為同一頁面和下一頁個人化設定個人化目的地](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} 在 *目的地概觀* 指南。
* [自訂個人化連線](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} 在 *目的地概觀* 指南
* [Adobe Target連線](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} 在 *目的地概觀* 指南
* [針對相同頁面和下一頁個人化使用案例設定個人化目的地](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} 在 *目的地概觀* 指南

## 與共用Real-time CDP Profile Attributes [!DNL Target] {#rtcdp-profile-attributes}

可與共用即時CDP配置檔案屬性 [!DNL Target] 用於HTML選件和 [JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Real-time CDP Profile Attributes功能限制和考量事項

>[!NOTE]
>
>Beta中提供Real-time CDP Profile Attributes功能，供HTML選件和 [JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md).

考慮以下事項:

* 指定選件內的屬性必須來自相同的Experience Platform沙箱。 (換言之，選件不能包含來自不同Experience Platform沙箱的屬性。)
* 指定選件中的屬性可能來自不同來源；即 [!DNL Target] 設定檔和Experience Platform設定檔。 (換句話說，您可以結合屬性(無論屬性來自何種 [!DNL Target] 或從Experience Platform設定檔)。
* 定義選件時，如果屬性沒有明確值，您可以為即時CDP設定檔屬性指派預設值。 例如，如果同意或控管原則封鎖了個人化服務中使用的屬性，則可改用預設值。
* 共用時，人工智慧/機器學習個人化模型中會使用即時CDP設定檔屬性，用於 [!UICONTROL 自動鎖定目標] 和 [!UICONTROL Automated Personalization] 活動。

### 範例使用案例

身為線上行銷人員，您希望AEP/統一設定檔與共用屬性值 [!DNL Target] 提供即時個人化。 使用即時CDP設定檔屬性，即可在 [!DNL Target] 使用代號取代的選件。 例如，您可以使用 `${aep.profile.favoriteColor}`，或使用代號的忠誠度層級和忠誠度點數值 `${aep.loyalty.tier}` 和 `${aep.loyalty.points}`.

建立JSON選件以與共用AEP/統一設定檔屬性的方式 [!DNL Target]:

1. 同時 [建立JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)，從 **[!UICONTROL 選擇源]** 清單，選擇 **[!UICONTROL Adobe Experience Platform]**.
1. 從 **[!UICONTROL 選取設定檔沙箱名稱]** 清單中，選取所需的沙箱。
1. 從 **[!UICONTROL 選取設定檔屬性]** 清單中，選擇所需的屬性。
1. （選用）從 **[!UICONTROL 插入預設值]** 清單中，選擇所需值。
1. 按一下&#x200B;**[!UICONTROL 「新增」]**。

   下圖顯示兩個設定檔屬性： `loyalty.tier` 和 `loyalty.points` 已新增至JSON選件。

   ![offer-json-aep-shared-attribute影像](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## 影片和部落格貼文

下列影片和部落格文章提供有關使用Target和RTCDP增強個人化的詳細資訊：

### 影片：使用即時CDP進行下次點擊的個人化，以及 [!DNL Adobe Target]{#RTCDP}

了解如何使用個人化下次點擊 [!DNL Real-time Customer Data Platform] 和 [!DNL Adobe Target]. 此 [!DNL Adobe Target] 目的地 [!DNL Real-time CDP] 可讓您使用 [!DNL Experience Platform] 區段 [!DNL Adobe Target] 提供控管和隱私權支援的相同頁面個人化和下一頁個人化。

如需詳細資訊，請參閱 [使用即時CDP和Adobe Target進行下一次點擊的個人化](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} 在 *平台Tutorials* 指南。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Adobe Target部落格和影片：同頁增強的個人化

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

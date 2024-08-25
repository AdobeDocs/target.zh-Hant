---
keywords: Real-Time Customer Data Platform;RTCDP;個人化;aep 客群;adobe experience platform 客群;設定檔屬性
description: 了解如何使用 [!DNL Target]/[!DNL Real-Time Customer Data Platform] (RTCDP) 整合服務，以提供更豐富的客戶資料和更有影響力的個人化功能。
title: 我如何整合  [!DNL Target] 和 [!DNL Real-Time Customer Data Platform]？
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 210e9de954dba813972b0da9a7db5b9383d3e303
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 85%

---

# 整合 [!DNL Real-Time Customer Data Platform]

[!DNL Real-Time Customer Data Platform] (RTCDP)，建置在 [!DNL Adobe Experience Platform] 上，可幫助公司整合來自多個企業來源的已知和匿名資料。RTCDP 可讓您建立客戶設定檔，並且可將這些設定檔用來即時提供跨所有管道和裝置的個人化客戶體驗。

若要了解更多關於 RTCDP，請參閱 [Real-Time Customer Data Platform 概覽](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant){target=_blank}。

## 重要功能

重要功能包含：

* 在 Edge 上，直接 [!DNL Target] 整合 Real-Time CDP/[!DNL Adobe Experience Platform] (消除對 [!DNL Audience Core services] - AAM 的相依性)
* [!UICONTROL Target Edge Destinations Card]具有治理和原則執行
* Real-time CDP 區段和共用設定檔屬性

## 實作案例

以下章節顯示在使用不同實作方法時會提供哪類型的個人化使用案例 (下一個工作階段或同一頁面)：

### at.js 實作

| 解決方案 | 啟用的使用案例 |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) 和 [!DNL Target]</li><li>[!DNL RTCDP] (Premium 或 Ultimate) 和 [!DNL Target]</li><li>[!DNL RTCDP] (任何 SKU)、[!DNL AAM] 和 [!DNL Target]</li></ul> | 下一個工作階段的個人化 |

### [!DNL Adobe Experience Platform Web SDK]或[!DNL Experience Platform Server-Side API]實作

| 解決方案 | 啟用的使用案例 |
| --- | --- |
| <ul><li>[!DNL RTCDP] (任何 SKU) 和 [!DNL Target]</li></ul> | <ul><li>下一個工作階段的個人化</li><li>透過 Edge 進行同一頁面的個人化</li><li>共用區段時強制執行控管</li></ul> |
| <ul><li>[!DNL RTCDP] (任何 SKU)、[!DNL AAM] 和 [!DNL Target]</li></ul> | <ul><li>下一個工作階段的個人化</li><ul><li>[!DNL AAM] 區段</li><li>透過 [!DNL AAM] 進行第三方區段</li></ul><li>透過 Edge 進行同一頁面的個人化</li><ul><li>[!DNL RTCDP] 區段</li><li>共用區段時強制執行控管</li></ul> |

### [!UICONTROL at.js]和[!DNL Platform Web SDK]實作的組合

| 解決方案 | 啟用的使用案例 |
| --- | --- |
| <ul><li>[!DNL RTCDP] (任何 SKU) 和 [!DNL Target]</li></ul> | <ul><li>下一個工作階段的個人化</li><ul><li>針對所有頁面和 [!UICONTROL at.js]</li></ul><li>同一頁面的個人化</li><ul><li>針對所有頁面和 [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] (任何 SKU)、[!DNL AAM] 和 [!DNL Target]</li></ul> | <ul><li>下一個工作階段的個人化</li><ul><li>針對所有頁面和 [!UICONTROL at.js]</li><li>[!DNL AAM] 區段</li><li>透過 [!DNL AAM] 進行第三方區段</li></ul> |

## 區段評估時間

下表顯示在不同實作案例發生事件的區段評估時間：

| 藍本 | Edge 區段 (毫秒評估) | 串流區段 (分鐘評估) | 批次區段評估 |
| --- | --- | --- | --- |
| 來自 [!DNL Adobe Experience Platform] SDK 的事件/資料 | 是 | 是 | 不適用 |
| 來自[!UICONTROL at.js]的事件 | 無 | 是 | 不適用 |
| 來自 [!DNL Target Mobile] SDK 的事件 | 無 | 是 | 不適用 |
| 來自批次的事件 | 無 | 無 | 是 |
| 來自離線資料的事件 (串流) | 無 | 是 | 是 |

## 使用來自 [!DNL Adobe Experience Platform] 的客群 {#aep}

使用在 [!DNL Adobe Experience Platform] 中建立的[客群](/help/main/c-target/c-audiences/audiences.md)可提供更豐富的客戶資料，進而帶來更具影響力的個人化。 [Real-Time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant){target=_blank} (RTCDP)，建置在 [!DNL Adobe Experience Platform] 上，可幫助公司整合來自多個企業來源的已知和匿名資料。此流程允許您建立客戶設定檔，並且可將這些設定檔用來即時提供跨所有管道和裝置的個人化客戶體驗。

透過將 [!DNL Target] 連接到 [!DNL Real-Time Customer Data Platform]，客戶可以強化他們的網頁個人化。此整合可讓您解鎖之前可能無法存取 [!DNL Target] 的新區段，進而在客戶瀏覽網頁的第一頁即可實現即時的毫秒個人化。使用在 [!DNL Adobe Experience Platform] 中建立的客群和設定檔屬性，可讓您擴展更強個人化的可用資料點。

這種整合方式可解鎖 Real-Time CDP 的關鍵使用案例：

* 同一頁面 / 下次點擊的個人化
* 第一次/不明使用者的個人化

## 與 [!DNL Target] 共用 Real-Time CDP 設定檔屬性 {#rtcdp-profile-attributes}

Real-Time CDP 設定檔屬性可與 [!DNL Target] 共用，用於 HTML 選件和 [JSON 選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)。

### Real-Time CDP 設定檔屬性功能限制和考量

考慮以下事項：

* 指定選件內的屬性必須來自相同的[!UICONTROL Experience Platform]沙箱。 （換句話說，選件不能包含不同[!UICONTROL Experience Platform]沙箱的屬性。）
* 指定選件內的屬性可能來自不同的來源，即[!DNL Target]設定檔和[!UICONTROL Experience Platform]設定檔。 （換言之，您可以合併來自[!DNL Target]或來自[!UICONTROL Experience Platform]設定檔的屬性。）
* 定義優惠方案時，您可以為[!UICONTROL Real-Time CDP Profile Attributes]指派預設值，以防屬性沒有明確值。 例如，如果同意書或控管政策封鎖個人化服務內使用的屬性，則可以改用預設值。

### JSON 使用案例範例

身為線上行銷人員，您希望 AEP/整合設定檔與以下人員共用屬性值[!DNL Target]以提供即時個人化。使用[!UICONTROL Real-Time CDP Profile Attributes]後，您就可以使用權杖取代來顯示[!DNL Target]選件中[!UICONTROL Experience Platform]屬性的值。 例如，您可以根據客戶最喜歡使用的顏色 `${aep.profile.favoriteColor}`，或者他們使用權杖的忠誠度等級和忠誠度點值 `${aep.loyalty.tier}` 和 `${aep.loyalty.points}` 來進行個人化。

若要建立 JSON 選件以與 [!DNL Target] 共用 AEP/Unified 設定檔屬性。

1. 在[建立JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md)時，從&#x200B;**[!UICONTROL Select a source]**&#x200B;清單中選取&#x200B;**[!UICONTROL Adobe Experience Platform]**。
1. 從&#x200B;**[!UICONTROL Select a profile sandbox name]**&#x200B;清單中，選取所需的沙箱。
1. 從&#x200B;**[!UICONTROL Select a profile attribute]**&#x200B;清單中，選取所需的屬性。
1. （選擇性）從&#x200B;**[!UICONTROL Insert a default value]**&#x200B;清單中選取所需的值。
1. 按一下 **[!UICONTROL Add]**。

下圖顯示了兩個設定檔屬性：`loyalty.tier` 和 `loyalty.points` 已新增到 JSON 選件中。

![offer-json-aep-shared-attribute 圖像](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## 了解更多資訊的連結

如需詳細資訊，請參閱下列主題:

* [目的地發行說明](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=zh-Hant#destinations){target=_blank} (在 *Adobe Experience Platform 發行說明*&#x200B;中)
* [為同一頁和下一頁個人化設定個人化目的地](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} (在&#x200B;*目的地概觀*&#x200B;指南中)。
* [Adobe Target 連接](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} (在&#x200B;*目的地概觀*&#x200B;指南中)
* [對應屬性](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=zh-Hant#map-attributes){target=_blank} (在&#x200B;*目的地概觀*&#x200B;指南中)。
* [對邊緣個人化目的地啟用客群](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-edge-personalization-destinations.html){target=_blank} (在&#x200B;*目的地概觀*&#x200B;指南中)。
* [透過  [!DNL Adobe Target]  和自訂個人化目的地進行同一頁和下一頁個人化](https://experienceleague.adobe.com/docs/experience-platform/destinations/destinations-faq.html?lang=en#same-next-page-personalization){target=_blank} (在&#x200B;*目的地概觀*&#x200B;指南中的「常見問題」下方)。

## 影片和部落格文章 {#videos-blogs}

以下影片和部落格文章提供有關使用 Target 和 RTCDP 加強個人化的更多資訊：

### 影片：使用 Real-Time CDP 和 [!DNL Adobe Target] 進行下一次點擊的個人化{#RTCDP}

了解如何使用 [!DNL Real-Time Customer Data Platform]和 [!DNL Adobe Target] 對下一次點擊進行個人化。 [!DNL Real-Time CDP] 中的 [!DNL Adobe Target] 目的地可讓您將 [!DNL Adobe Target] 中的 [!DNL Experience Platform] 區段用於具有控管和隱私權支援的同一頁個人化和下一頁個人化。

若要了解詳細資訊，請參閱[使用 Real-time CDP 和 Adobe Target 的下一次點擊個人化](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html?lang=zh-Hant){target=_blank} (在 *Platform 教學課程*&#x200B;指南中)。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### 影片：在 [!DNL Real-Time Customer Data Platform] 中設定 [!DNL Adobe Target] 目的地

了解如何在 [!DNL Real-Time Customer Data Platform] 中設定 [!DNL Adobe Target] 目的地，以開始從 [!DNL Real-Time CDP] 傳送區段和設定檔屬性到 [!DNL Target]。

>[!VIDEO](https://video.tv.adobe.com/v/3418799/?learn=on)

### 影片：啟動區段和設定檔屬性

了解如何從 [!DNL Adobe Real-Time Customer Data Platform] 將區段和設定檔屬性啟動到 [!DNL Adobe Target] 以在您的網站、行動應用程式和其他數位資產中顯示即時個人化內容。

>[!VIDEO](https://video.tv.adobe.com/v/3419036/?learn=on)

### 影片：在 [!DNL Target] 中使用 [!DNL Real-Time CDP] 區段

了解如何在 [!DNL Adobe Target] 中使用 [!DNL Real-Time Customer Data Platform] 區段，以在您的網站和行動應用程式上提供個人化體驗。

>[!VIDEO](https://video.tv.adobe.com/v/3419149/?learn=on)

### 影片：在 [!DNL Adobe Target] 中使用 [!DNL Real-Time CDP] 設定檔屬性

了解如何在 [!DNL Adobe Target] 中使用 [!DNL Adobe Real-Time Customer Data Platform] 設定檔屬性，以在您的網站和行動應用程式上提供個人化體驗。

>[!VIDEO](https://video.tv.adobe.com/v/3419318/?learn=on)

### [!DNL Adobe Target] 部落格和影片：同一頁面增強的個人化

[[!DNL Adobe] 宣佈使用 [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]的同頁增強型Personalization](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

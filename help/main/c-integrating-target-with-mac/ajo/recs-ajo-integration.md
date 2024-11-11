---
keywords: ajo；adobe journey optimizer；adobe journey optimizer target整合；建議；target建議；整合
description: 將 [!DNL Adobe Target Recommendations] 與 [!DNL Adobe Journey Optimizer]整合。
title: 如何在使用 [!DNL Adobe Journey Optimizer]的客戶歷程中使用 [!DNL Target Recommendations] ？
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
badgeBeta: label="Beta 版" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 有哪些 Beta 版功能。"
hide: true
hidefromtoc: true
exl-id: 81bbbd51-47fc-4e23-a1cb-7c18fea1c159
source-git-commit: b4f9e14f9dfa94f8648686e43e66eee7e0f7daa1
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 1%

---

# 整合[!DNL Adobe Target Recommendations]和[!DNL Adobe Journey Optimizer]

本文提供將[!DNL Adobe Target Recommendations]與[!DNL Adobe Journey Optimizer]整合的使用案例和指引，讓您提供連線、情境式和個人化的客戶體驗。

此整合可協助您提高轉換率，並瞭解包含個人化建議的電子郵件訊息的影響。

## 先決條件

若要使用[!DNL Target Recommendations]與[!DNL Adobe Journey Optimizer]整合，您需要下列專案：

* 使用[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}實作的[[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium)。

  [!DNL Target Standard]授權或使用at.js或其他[!DNL Target] SDK實作[!DNL Target]時，無法使用此功能。

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target=_blank}。

## 範例使用案例

這些使用案例只是將[!DNL Target Recommendations]與[!DNL Adobe Journey Optimizer]整合的幾個可能使用案例：

* **[!DNL Adobe Journey Optimizer]在購物車放棄後傳送個人化電子郵件**：此使用案例是以客戶造訪網站、將專案放入購物車，然後離開網站而未完成購買程式為基礎。

  例如，假設訪客造訪一家服裝公司的網站，在購物車中放置兩件冬季外套和一件運動衫。 訪客接著會分心，離開網站，或不確定購買情形，然後關閉瀏覽器或應用程式。

  在指定的期間（可能是幾個小時或一天）之後，[!DNL Journey Optimizer]中的自訂動作會呼叫[!DNL Target Recommendations]，以使用[購物車型建議](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)演演算法來決定捨棄的購物車的內容。 [!DNL Journey Optimizer]接著傳送個人化電子郵件給此訪客，以提醒購買程式尚未完成，同時附上影像和放棄專案的連結。

* **[!DNL Adobe Journey Optimizer]在網站造訪後會傳送大量電子郵件，以提醒訪客已檢視哪些專案**：此使用案例是根據訪客造訪網站、檢視各種專案，然後離開網站或應用程式，而不將專案放入購物車中的情形。

  在指定的時段後，[!DNL Journey Optimizer]中的自訂動作會呼叫[!DNL Target Recommendations]，使用每位訪客的[!DNL Adobe Experience Cloud Identifier] (EDID)、訪客的[!DNL Target]設定檔及[以使用者為基礎的](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)演演算法，來決定每位訪客檢視哪些專案。 [!DNL Adobe Journey Optimizer]接著傳送個人化電子郵件給合格對象中的每個成員，內含每個訪客已檢視專案的影像和連結，以便讓訪客回訪並購買。

  在此案例中，[!UICONTROL Experience Cloud Visitor ID] (ECID)和每個訪客的[!DNL Target]設定檔內容是用來根據最近檢視的演演算法產生建議。

  例如，假設一位訪客造訪零售網站並檢視數個手錶。 此訪客的[!DNL Target]設定檔已更新為檢視的監看清單。 使用ECID和訪客的[!DNL Target]設定檔，[!DNL Target]會將建議傳送至[!DNL Journey Optimizer]。 [!DNL Journey Optimizer]接著會傳送電子郵件，內含該訪客使用最近檢視的演演算法所檢視之監視專案的影像和連結。 另一位訪客收到個人化電子郵件，其中包含該訪客已檢視專案的影像和連結。 每個訪客的每則電子郵件訊息都會個人化。

* **[!DNL Adobe Journey Optimizer]在網站造訪後傳送大量電子郵件給合格訪客，以建議熱門專案**：此使用案例是以造訪網站的訪客為基礎，但未檢視任何特定專案。 電子郵件會大量傳送給符合特定對象資格的所有訪客，例如：

  假設訪客沒有檢視任何特定手錶。 或許訪客只是按一下網站各處，然後檢視了類別頁面或部落格專案。 因此，[!DNL Target]設定檔沒有最近檢視專案的相關特定資訊。 在此情況下，[!DNL Target Recommendations]會使用[備份建議](/help/main/c-recommendations/c-algorithms/backup-recs.md)，讓[!DNL Journey Optimizer]可以傳送包含影像和網站熱門專案連結的電子郵件，以讓訪客回訪，並可能進行購買。

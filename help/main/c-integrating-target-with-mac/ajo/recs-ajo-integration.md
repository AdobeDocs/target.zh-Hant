---
keywords: ajo；adobe journey optimizer；adobe journey optimizer target整合；建議；target建議；整合
description: 整合 [!DNL Adobe Target Recommendations] 替換為 [!DNL Adobe Journey Optimizer].
title: 如何使用 [!DNL Target Recommendations] 在客戶歷程中，使用 [!DNL Adobe Journey Optimizer]？
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
badgeBeta: label="Beta 版" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 有哪些 Beta 版功能。"
hide: true
hidefromtoc: true
source-git-commit: ce74c85380333476b97f47fab4d2659a3c9c86e1
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 1%

---

# 整合 [!DNL Adobe Target Recommendations] 和 [!DNL Adobe Journey Optimizer]

本文說明使用案例和資訊，協助您設定以下兩者的整合： [!DNL Adobe Target Recommendations] 和 [!DNL Adobe Journey Optimizer] 協助您為客戶提供連結、情境式和個人化的體驗。

此整合可協助您提高轉換率，並瞭解包含個人化建議的電子郵件訊息的影響。

## 必備條件

若要使用 [!DNL Target Recommendations] 和 [!DNL Adobe Journey Optimizer] 整合，您需要下列專案：

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) 使用實施 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

  此功能不適用於 [!DNL Target Standard] 授權或實施時 [!DNL Target] 使用at.js或其他 [!DNL Target] SDK。

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## 範例使用案例

以下只是整合的幾個可能使用案例 [!DNL Target Recommendations] 替換為 [!DNL Adobe Journey Optimizer]：

* **[!DNL Adobe Journey Optimizer]在放棄購物車後傳送個人化電子郵件**：此使用案例是根據客戶造訪網站，將專案放入購物車，然後離開網站而未完成購買程式。

  例如，假設訪客造訪一家服裝公司的網站，在購物車中放置兩件冬季外套和一件運動衫。 訪客接著會分心，離開網站，或不確定購買情形，然後關閉瀏覽器或應用程式。

  在指定的時間段（可能是幾個小時或一天）之後，中的自訂動作 [!DNL Adobe Journey Optimizer] 呼叫 [!DNL Target Recommendations] 以使用判斷捨棄的購物車的內容 [購物車型建議](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) 演演算法。 [!DNL Adobe Journey Optimizer] 然後傳送個人化電子郵件給此訪客，提醒其購買程式尚未完成，並提供影像和放棄專案的連結。

* **[!DNL Adobe Journey Optimizer]會在網站造訪後傳送大量電子郵件，提醒訪客已檢視哪些專案**：此使用案例是根據訪客造訪網站、檢視各種專案，然後離開網站或應用程式而不將專案放入購物車中的情形。

  經過指定期間後，中的自訂動作 [!DNL Adobe Journey Optimizer] 呼叫 [!DNL Target Recommendations] 使用每位訪客的 [!DNL Adobe Experience Cloud Identifier] (EDID)，訪客的 [!DNL Target] 設定檔和 [基於使用者](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) 演演算法。 [!DNL Adobe Journey Optimizer] 然後傳送個人化電子郵件給合格受眾的每個成員，內含每個訪客已檢視專案的影像和連結，以讓訪客回訪並購買。

  在此案例中， [!UICONTROL Experience Cloud訪客ID] (ECID)以及每位訪客的 [!DNL Target] 設定檔是用來根據最近檢視的演演算法產生建議。

  例如，假設一位訪客造訪零售網站並檢視數個手錶。 此訪客的 [!DNL Target] 設定檔會以已檢視的監看清單更新。 使用ECID和訪客的 [!DNL Target] 設定檔， [!DNL Target] 傳送建議至 [!DNL Adobe Journey Optimizer]. [!DNL Adobe Journey Optimizer] 然後傳送電子郵件，內含該訪客使用最近檢視的演演算法所檢視之監視專案的影像和連結。 另一位訪客收到個人化電子郵件，其中包含該訪客已檢視專案的影像和連結。 每個訪客的每則電子郵件訊息都會個人化。

* **[!DNL Adobe Journey Optimizer]在網站造訪後傳送大量電子郵件給合格訪客，以建議熱門專案**：此使用案例是根據訪客造訪網站但未檢視任何特定專案。 電子郵件會大量傳送給所有符合特定對象資格的對象，例如：

  假設訪客沒有檢視任何特定手錶。 或許訪客只是按一下網站各處，然後檢視了類別頁面或部落格專案。 因此， [!DNL Target] 設定檔沒有最近檢視專案的相關特定資訊。 在此情況下， [!DNL Target Recommendations] 使用 [備份建議](/help/main/c-recommendations/c-algorithms/backup-recs.md) 因此 [!DNL Adobe Journey Optimizer] 可以傳送內含影像和網站熱門專案連結的電子郵件，以吸引訪客回訪並可能進行購買。



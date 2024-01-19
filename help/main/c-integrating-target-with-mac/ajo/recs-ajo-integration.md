---
keywords: ajo；adobe journey optimizer；adobe journey optimizer target整合；建議；target建議；整合
description: 使用 [!DNL Adobe Target Recommendations] 替換為 [!DNL Adobe Journey Optimizer].
title: 如何使用 [!DNL Target Recommendations] 在客戶歷程中，使用 [!DNL Adobe Journey Optimizer]？
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
badgeBeta: label="Beta 版" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip=" [!DNL Adobe Target] 有哪些 Beta 版功能。"
hide: true
hidefromtoc: true
source-git-commit: bb6c83ff393656a634e1e8ddcb02b14dc8d4c8d2
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 3%

---

# [!DNL Adobe Target Recommendations] 和 [!DNL Adobe Journey Optimizer] 整合

本文說明使用案例和資訊，協助您設定以下兩者的整合： [!DNL Adobe Target Recommendation] 和 [!DNL Adobe Journey Optimizer] 協助您為客戶提供連結、情境式和個人化的體驗。

## 必備條件

若要使用 [!DNL Target Recommendations] 和 [!DNL Adobe Journey Optimizer] 整合，您需要下列專案：

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) 使用實施 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

  此功能不適用於 [!DNL Target Standard] 授權或實施時 [!DNL Target] 使用at.js或其他 [!DNL Target] SDK。

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## 範例使用案例

以下是整合的兩個可能使用案例 [!DNL Target Recommendations] 替換為 [!DNL Adobe Journey Optimizer]：

* **[!DNL Customer Journey Optimizer]在放棄購物車後傳送個人化電子郵件**：此使用案例是根據客戶造訪網站，將專案放入購物車，然後離開網站而未完成購買程式。

  例如，假設訪客造訪一家服裝公司的網站，在購物車中放置兩件冬季外套和一件運動衫。 訪客接著會分心，離開網站，或不確定購買情形，然後關閉瀏覽器或應用程式。

  經過指定的時段（可能是幾個小時或一天）後，中的自訂動作 [!DNL Adobe Journey Optimizer] 呼叫 [!DNL Target Recommendations] 以判斷捨棄的購物車的內容。 [!DNL Adobe Journey Optimizer] 然後傳送個人化電子郵件給此訪客，提醒其購買程式尚未完成，並提供影像和放棄專案的連結。

* **[!DNL Customer Journey Optimizer]使用使用者設定檔在網站造訪後傳送電子郵件**：此使用案例是根據客戶造訪網站、檢視各種專案，然後離開網站而不將專案放入購物車中的情形。

  經過指定時間後，中的自訂動作 [!DNL Adobe Journey Optimizer] 呼叫 [!DNL Target Recommendations] 以判斷此訪客使用訪客的 [!DNL Adobe Experience Cloud Identifier] (EDID)。 [!DNL Adobe Journey Optimizer] 然後傳送個人化電子郵件給此訪客，提醒其購買程式尚未完成，並提供影像和放棄專案的連結。


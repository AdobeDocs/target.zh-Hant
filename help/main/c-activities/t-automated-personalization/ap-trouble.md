---
keywords: Automated Personalization；ap；疑難排解；疑難排解；模型；提升度
description: 探索您在Adobe Target中使用[!UICONTROL Automated Personalization] (AP)活動時可能遇到的挑戰，以及建議的解決方案。
title: 如何疑難排解[!UICONTROL Automated Personalization]活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
TQID: 'https://experienceleague.adobe.com/1Qevyq-TiutN1dEZnfC1DDmUgXoHIxtBl-3RMPq-m-0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 7%
---
# 疑難排解[!UICONTROL Automated Personalization] {#ap-troubleshooting}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;尋找&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動常見問題的解決方案。

>[!ENDSHADEBOX]

活動並非總是如預期般進行。 使用以下清單來識別[!UICONTROL Automated Personalization] (AP)活動中常見問題的原因，並套用建議的解決方案。

## 模型與提升度 {#models-and-lift}

+++ 我的[!UICONTROL Automated Personalization]活動花費太長的時間建立模型

數個活動設定選擇會影響模型需要建置的時間，包括您的&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中的體驗數量、流向您網站的流量，以及您選取的成功量度。

**解決方案：**&#x200B;檢閱您的活動設定，並檢查您是否可以進行變更以改善模型建立的速度。

* 如果您的成功量度是設為 RPV，您可以變更為轉換嗎？ 轉換活動傾向需要較少流量來建置模型。 如果將成功量度從RPV變更為轉換，則不會遺失活動資料。
* 您的成功量度是否遠低於您的活動體驗的銷售漏斗？ 較低的活動轉換率會增加要建立的模型流量需求，因為轉換數是最低要求。
* 是否有您可以從活動中排除的一些選件或體驗？ 減少活動中的體驗數量會加快建立模型的時間。
* 是否有更高流量的頁面可讓此活動更成功？ 活動位置的流量和轉換次數越多，建立的模型就越快。

+++

+++ 我的[!UICONTROL Automated Personalization]活動未產生提升度

**[!UICONTROL Automated Personalization]**&#x200B;活動需要數個因素才能產生提升度：

* 選件差異必須足以影響訪客。
* 選件必須位於對最佳化目標有所影響的位置。
* 測試中必須有足夠的流量和統計「能力」，才能偵測提升度。
* 個人化演算法必須正常運作。

**解決方案：**&#x200B;動作的最佳措施是先使用簡易、非個人化的A/B測試，確定組成活動體驗的內容和位置對整體回應率真的有產生影響。 提前計算樣本大小以確保有足夠的能力來檢視合理的提升度，然後在固定期間內執行A/B測試而不停止它或進行任何變更。 如果A/B測試結果顯示一或多個體驗在統計上顯著提升，個人化活動可能會成功。 即使體驗的整體回應率沒有差異，Personalization仍可運作。 通常，問題源自選件或位置對最佳化目標的影響不足以偵測到具有統計顯著性的情況。

+++

## 活動設定與報告 {#setup-and-reporting}

+++ 我的[!UICONTROL Automated Personalization]活動URL在不正確的頁面上顯示選件內容

**原因：**&#x200B;在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;中，URL和範本測試規則新增至[!DNL Target]要求專案條件約束（例如target-global-mbox），只會評估一次。 訪客符合活動資格後，系統不會重新評估[!DNL Target]請求層級鎖定目標規則，而會將鎖定目標對象新增至位置鎖定目標規則。

**解決方案：**&#x200B;新增必要的範本規則作為活動的輸入對象。 對象評估會在每個要求時進行（呼叫）。

+++

+++ 相依於轉換量度的任何量度永遠不會轉換

這是預期中的正常行為。

在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中，轉換量度（無論是最佳化目標或貼文目標）一旦轉換，訪客就會從體驗中釋放，活動就會重新啟動。

例如，活動具有轉換量度(C1)和相依於C1的其他量度(A1)。 當訪客首次進入活動且未轉換C1或A1時，A1不會轉換，因為成功量度相依性。 如果訪客轉換C1然後轉換A1，A1仍不會轉換，因為訪客在C1轉換時就會釋放。

+++

+++ 我的體驗URL未如預期運作

**解決方案：**&#x200B;使用以下動作：

* 如果您在新索引標籤中看不到預覽（由於瀏覽器快取），請嘗試重新整理兩或三次。 您也可以複製連結，並在新瀏覽器或新工作階段中開啟。
* 如果您變更任何內容，請重新產生Experience URL連結，並與您的隊友共用新的連結。

+++

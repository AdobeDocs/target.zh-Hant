---
kewords: Automated Personalization;ap;troublshoot;troubleshooting;model;lift
description: 探索您在使用時可能面臨的潛在挑戰 [!UICONTROL Automated Personalization] (AP) Adobe Target中的活動，以及建議的解決方案。
title: 如何疑難排解 [!UICONTROL Automated Personalization] 活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
source-git-commit: 2cb2c2b68f6487d1af41ecc7e73750afa1ad85f9
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 31%

---

# 疑難排解 [!UICONTROL Automated Personalization]

有時活動不會如預期般進行。以下是使用時可能會面臨的一些潛在挑戰 [!UICONTROL Automated Personalization] (AP)，以及一些建議的解決方案。

## 我的 [!UICONTROL Automated Personalization] 活動花費太長的時間建立模型。 {#section_20028B204DBB4D77A324BA193434AEE2}

+++查看詳細資料

有幾項活動設定變更可以縮短建立模型的預期時間，包括您的中的體驗數量 [!UICONTROL Automated Personalization] 活動、您網站的流量，以及您選取的成功量度。

**解決方案：** 檢閱活動設定，並檢視您是否有任何願意進行的變更來改善模型建立的速度。

* 如果您的成功量度是設為 RPV，您可以變更為轉換嗎？ 轉換活動傾向需要較少流量來建置模型。如果將成功量度從RPV變更為轉換，則不會遺失活動資料。
* 您的成功量度是否遠低於您的活動體驗的銷售漏斗？ 較低的活動轉換率將增加建置模型所需的流量，因為需要最低的轉換數量。
* 是否有您可以從活動中排除的一些選件或體驗? 減少活動中的體驗數量會加快建立模型的時間。
* 是否有更高流量的頁面可讓此活動更成功？ 活動位置的流量和轉換次數越多，建立的模型就越快。

+++

## 我的 [!UICONTROL Automated Personalization] 活動未產生提升度。 {#section_8900BC8968474438B8092F7A94C0C6CF}

+++查看詳細資料

有幾個因素需要進行 [!UICONTROL Automated Personalization] 產生提升度的活動：

* 選件差異必須足以影響訪客。
* 選件必須位於對最佳化目標有所影響的位置。
* 測試中必須有足夠的流量和統計「能力」，才能偵測提升度。
* 個人化演算法必須正常運作。

**解決方案:** 動作的最佳措施是先使用簡易、非個人化的 A/B 測試確定組成活動體驗的內容和位置對整體回應率真的有產生影響。請務必提前計算樣本大小。 提前計算樣本大小有助於確保有足夠的力量來看到合理的提升度。 接著，您可以持續固定時間執行A/B測試，而不需停止或進行任何變更。 如果A/B測試結果顯示一或多個體驗在統計上顯著提升，則個人化活動可能會成功。 即使體驗的整體回應率沒有差異，個人化仍可運作。 通常，問題源自選件或位置對最佳化目標的影響不足以偵測到具有統計顯著性的情況。

+++

## 我的 [!UICONTROL Automated Personalization] 活動URL在不正確的頁面上顯示選件內容。 {#section_82A224406DBF4107B05204BEFBBE458C}

+++查看詳細資料

在 [!UICONTROL Automated Personalization]，則URL和範本測試規則會新增至 [!DNL Target] 要求專案限制（例如target-global-mbox），只會評估一次。 使用者符合活動資格後，不會重新評估Target請求層級的鎖定目標規則。 不過，鎖定目標對象會新增至位置鎖定目標規則。

**解決方案：** 新增必要的範本規則作為活動的輸入對象。 在每個要求/呼叫時都會進行對象評估。

+++

## 相依於轉換量度的任何量度永遠不會轉換。 {#section_076D1F44298C4E4A849AC52F5A33214D}

+++查看詳細資料

這是預期中的情形。

在 [!UICONTROL Automated Personalization] 活動，轉換量度（無論是最佳化目標或事後目標）轉換後，訪客會從體驗中釋放，而活動會重新啟動。

例如，有一個活動具有轉換量度 (C1) 和另一個量度 (A1)。A1相依於C1。 當訪客第一次進入活動，而轉換 A1 和 C1 的條件未轉換，由於成功量度相依性，此時不會轉換量度 A1。如果訪客轉換C1然後轉換A1，A1仍不會轉換，因為轉換C1時，訪客會釋放。

+++

## 我的體驗 URL 未如預期運作。 {#section_7B08DA1F30AA483E9406336DAF361BA4}

+++查看詳細資料

* 如果您在新索引標籤中看不到預覽（由於瀏覽器快取），請嘗試重新整理兩或三次。 您也可以複製連結，並在新瀏覽器或新工作階段中開啟。
* 如果您已變更任何內容，請重新產生體驗 URL 連結，並您的團隊成員分享新連結。

+++

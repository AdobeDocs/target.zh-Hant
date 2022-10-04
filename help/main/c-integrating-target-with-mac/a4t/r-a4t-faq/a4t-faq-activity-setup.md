---
keywords: faq;常見問題集;analytics for target;a4T;活動設定
description: 尋找使用Analytics進行活動設定時的相關問題解答 [!DNL Target] (A4T)。 A4T可讓您對 [!DNL Target] 活動。
title: 我可以在哪裡找到關於A4T活動設定的常見問題集？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 20%

---

# 活動設定 - A4T 常見問題集

此主題包含經常詢問關於活動設定和使用 [!DNL Analytics] 作為的報表來源 [!DNL Target] (A4T)。

## Analytics 作為報表來源 (A4T) 時支援哪些活動類型? {#section_5E4F58CD25A5424E869E6FE0803968EF}

如需完整清單，請參閱 [Adobe Analytics 作為 Adobe Target (A4T) 的報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)中的「支援的活動類型」。

## 在設定目標量度時，為何無法存取進階設定？

針對使用 [!DNL Analytics] 作為報表來源(A4T)，目標量度會使用[!UICONTROL 增加計數並讓使用者留在活動中]&quot;和&quot;[!UICONTROL 在每次曝光時]」設定。 這些設定包括 *not* 可設定。

如需詳細資訊，請參閱「設定目標量度時，為何無法存取進階設定選項？」 in [量度定義 — A4T常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## 我剛才建立了活動。為何沒看到任何資料進入? {#section_9F8092BE4225442896F926540292F221}

建立活動時， [!DNL Target] 將分類檔案傳送至 [!DNL Analytics]. 雖然 [!DNL Analytics] 擷取和處理資料時，除非更新分類檔案，否則不會在報表中顯示。 此程式最多需要24小時。 如果 48 小時之後沒看到資料，請[聯絡客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。或者，如果您知道您啟動活動，則可以事前幾天建立活動，並在儲存活動時傳送分類。 於是，啟動後資料即會立即出現在報表中。請注意，在中處理資料需要45到90分鐘 [!DNL Analytics].

## 建立活動時，為何無法選取Analytics作為報表來源？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

您可以變更 [!UICONTROL 報表設定] 選項 [!UICONTROL 管理].

1. 在 [!DNL Target]，按一下 **[!UICONTROL 管理]**.
1. 在&#x200B;**[!UICONTROL 「用於報表的 Experience Cloud 解決方案」]**&#x200B;下拉式清單中，按一下&#x200B;**[!UICONTROL 「為每個活動選取」]**。

![根據活動選擇影像](assets/select-per-activity.png)

**[!UICONTROL 「目標與設定」]**&#x200B;畫面中會啟用&#x200B;**[!UICONTROL 「報表來源」下拉式清單，以供您建立和編輯活動。]**

一律使用 [!DNL Analytics] 作為報表來源，請選取 **[!UICONTROL Adobe Analytics]** 從 [!UICONTROL 管理].

## 在使用A4T的自動鎖定目標活動中，訪客是否可以在不同造訪中的鎖定目標體驗和控制體驗之間切換？

假設訪客的visitorId不會在兩次瀏覽之間變更，則下列情況成立。

如果流量分配百分比在活動中間調整，訪客可能會在鎖定目標和控制體驗之間移動。

如果百分比未在活動中間調整，則一律會將最初看到控制的訪客傳送至控制。 傳送至目標體驗的訪客一律會傳送至目標體驗。

* 在流量的目標「貯體」中後，如果機器學習模型判斷不同體驗與新造訪相關，則可將訪客傳送至與造訪不同的體驗。
* 將訪客指派給流量的控制「貯體」後，將一律會看見相同的體驗，因為體驗指派是以訪客visitorId的確定性偽隨機雜湊為基礎。


## 我可以使用二項式嗎 [!DNL Analytics] 量度，並將區段套用為 [!UICONTROL 自動分配] 活動？ {#binomial}

您無法使用 [!DNL Analytics] 量度，並將區段套用為 [!UICONTROL 自動分配] 活動。 作為因應措施，您可以定義達到相同目標的自訂事件，並將其用作最佳化目標量度。
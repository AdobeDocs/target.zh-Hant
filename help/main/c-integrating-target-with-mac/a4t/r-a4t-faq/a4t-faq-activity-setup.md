---
keywords: faq;常見問題集;analytics for target;a4T;活動設定
description: 為以下專案使用Analytics時尋找有關活動設定的問題解答： [!DNL Target] (A4T)。 A4T可讓您將Analytics報表用於 [!DNL Target] 活動。
title: 我可以在哪裡找到有關A4T活動設定的常見問題集？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 52dd26acfce77da0eea14be572708c069ba5e9ba
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 14%

---

# 活動設定 - A4T 常見問題集

此主題包含經常詢問關於活動設定和使用問題的回答 [!DNL Analytics] 做為的報表來源 [!DNL Target] (A4T)。

## Analytics 作為報表來源 (A4T) 時支援哪些活動類型? {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++如需完整清單，請參閱以下的「支援的活動型別」： [Adobe Analytics作為Adobe Target (A4T)的報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

+++

## 設定目標量度時，為何無法存取進階設定？

+++使用回答活動 [!DNL Analytics] 作為報表來源(A4T)，目標量度使用「[!UICONTROL 增加計數以及讓使用者留在活動中]「和」[!UICONTROL 在每次曝光時]「設定。 這些設定為 *非* 可設定。

如需詳細資訊，請參閱「設定目標量度時，為何無法存取進階設定選項？」 在 [量度定義 — A4T常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## 我剛才建立了活動。為何沒看到任何資料進入? {#section_9F8092BE4225442896F926540292F221}


+++回答建立活動時， [!DNL Target] 傳送分類檔案至 [!DNL Analytics]. 雖然 [!DNL Analytics] 擷取及處理資料時，在更新分類檔案之前，不會顯示在報表中。 此程式可能需要24到72小時的時間才能完成。 如果72小時之後沒看到資料， [連絡Client Care](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). 或者，如果您知道您啟動了一個活動，您可以提前幾天建立該活動，並在儲存活動時傳送分類。 於是，啟動後資料即會立即出現在報表中。請注意，在中處理資料需要45到90分鐘 [!DNL Analytics].

+++

## 建立活動時，為何無法選取Analytics作為報表來源？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++回答您可以變更您的 [!UICONTROL 報表設定] 中的選項 [!UICONTROL 管理].

1. 在 [!DNL Target]，按一下 **[!UICONTROL 管理]**.
1. 在&#x200B;**[!UICONTROL 「用於報表的 Experience Cloud 解決方案」]**&#x200B;下拉式清單中，按一下&#x200B;**[!UICONTROL 「為每個活動選取」]**。

![為每個活動選取影像](assets/select-per-activity.png)

**[!UICONTROL 「目標與設定」]**&#x200B;畫面中會啟用&#x200B;**[!UICONTROL 「報表來源」下拉式清單，以供您建立和編輯活動。]**

永遠使用 [!DNL Analytics] 作為報表來源，選取「 」 **[!UICONTROL Adobe Analytics]** 從的下拉式清單 [!UICONTROL 管理].

+++

## 在使用A4T的自動鎖定目標活動中，訪客可以在不同造訪中的目標體驗和控制體驗之間切換嗎？

+++回答假設訪客的visitorId在兩次造訪之間未變更，則符合下列條件。

如果流量分配百分比在活動期間調整，訪客可能會在目標鎖定和控制體驗之間移動。

如果百分比未在活動期間調整，最初看到控制的訪客一律會傳送至控制。 傳送至目標體驗的訪客一律會傳送至目標體驗。

* 如果機器學習模型判斷不同的體驗與新造訪相關，則訪客在進入鎖定目標的流量「貯體」後，可以經由造訪傳送至不同的體驗。
* 在指派給流量的控制「貯體」後，訪客將一律會看到相同的體驗，因為體驗指派是以訪客visitorId的確定性偽隨機雜湊為基礎。

+++

## 我可以使用二項式嗎 [!DNL Analytics] 量度，並將區段套用為中的最佳化目標 [!UICONTROL 自動分配] 活動？ {#binomial}

+++回答您無法使用 [!DNL Analytics] 量度，並將區段套用為中的最佳化目標 [!UICONTROL 自動分配] 活動。 暫行解決方法是定義達成相同目標的自訂事件，並將其作為最佳化目標量度。

+++
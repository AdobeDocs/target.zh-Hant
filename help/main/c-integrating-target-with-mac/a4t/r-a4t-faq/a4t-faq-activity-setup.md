---
keywords: faq;常見問題集;analytics for target;a4T;活動設定
description: 尋找使用Analytics for [!DNL Target] (A4T)時活動設定的相關問題解答。 A4T可讓您對 [!DNL Target] 個活動使用Analytics報告。
title: 我可以在哪裡找到有關A4T活動設定的常見問題集？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 6%

---

# 活動設定 - A4T 常見問題集

此主題包含經常詢問關於活動設定和使用[!DNL Analytics]做為[!DNL Target] (A4T)報表來源問題的回答。

## 哪些活動型別支援[!DNL Analytics]做為報表來源(A4T)？ {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++回答
如需完整清單，請參閱[Adobe Analytics as a4T) ](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)中的「支援的活動型別」，作為Adobe Target的報表Source。

+++

## 使用A4T報表時，我可以在不同的工作區中，對兩個活動使用相同的活動名稱嗎？

+++回答

請勿對使用A4T報表之不同[工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)中的兩個活動使用相同的活動名稱。

雖然使用[!DNL Target]作為報表來源時支援此功能，但是使用[!UICONTROL Analytics for Target]作為報表來源時，不支援對兩個活動使用相同的活動名稱。

+++

## 設定目標量度時，為何無法存取進階設定？

+++回答
對於使用[!DNL Analytics]作為報表來源(A4T)的活動，目標量度使用&quot;[!UICONTROL Increment Count & Keep User in Activity]&quot;和&quot;[!UICONTROL On Every Impression]&quot;設定。 這些設定是&#x200B;*不可設定的*。

如需詳細資訊，請參閱「設定目標量度時，為何無法存取進階設定選項？」 在[量度定義中 — A4T常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)。

+++

## 我剛才建立了活動。為何沒看到任何資料進入? {#section_9F8092BE4225442896F926540292F221}


+++回答
建立活動時，[!DNL Target]會將分類檔案傳送至[!DNL Analytics]。 雖然[!DNL Analytics]正在擷取及處理資料，但只有在更新分類檔案後，才會顯示在報表中。 此程式可能需要24到72小時的時間才能完成。 如果您在72小時之後沒有看到資料，請[連絡客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。 或者，如果您知道您啟動了一個活動，您可以提前幾天建立該活動，並在儲存活動時傳送分類。 於是，啟動後資料即會立即出現在報表中。請注意，在[!DNL Analytics]內處理資料需要45到90分鐘。

+++

## 建立活動時，為何無法選取Analytics作為報表來源？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++回答
您可以在[!UICONTROL Administration]中變更您的[!UICONTROL Reporting Settings]選項。

1. 在[!DNL Target]中，按一下&#x200B;**[!UICONTROL Administration]**。
1. 在&#x200B;**[!UICONTROL Experience Cloud solution used for reporting]**&#x200B;下拉式清單中，按一下&#x200B;**[!UICONTROL Select per Activity]**。

![為每個活動選取影像](assets/select-per-activity.png)

已在&#x200B;**[!UICONTROL Goal & Settings]**&#x200B;畫面中啟用&#x200B;**[!UICONTROL Reporting Source]**&#x200B;下拉式清單，以用於建立和編輯活動。

若要一律使用[!DNL Analytics]作為報表來源，請在[!UICONTROL Administration]中從下拉式清單選取&#x200B;**[!UICONTROL Adobe Analytics]**。

+++

## 在使用A4T的自動鎖定目標活動中，訪客可以在不同造訪中的目標體驗和控制體驗之間切換嗎？

+++回答
假設訪客的visitorId在兩次造訪之間未變更，則情況如下。

如果流量分配百分比在活動期間調整，訪客可能會在目標鎖定和控制體驗之間移動。

如果百分比未在活動期間調整，最初看到控制的訪客一律會傳送至控制。 傳送至目標體驗的訪客一律會傳送至目標體驗。

* 如果機器學習模型判斷不同的體驗與新造訪相關，則訪客在進入鎖定目標的流量「貯體」後，可以經由造訪傳送至不同的體驗。
* 在指派給流量的控制「貯體」後，訪客將一律會看到相同的體驗，因為體驗指派是以訪客visitorId的確定性偽隨機雜湊為基礎。

+++

## 我可以在[!UICONTROL Auto-Allocate]活動中，將二項式[!DNL Analytics]量度搭配作為最佳化目標的區段一起使用嗎？ {#binomial}

+++回答
您無法將[!DNL Analytics]量度與已套用為[!UICONTROL Auto-Allocate]活動中最佳化目標的區段搭配使用。 暫行解決方法是定義達成相同目標的自訂事件，並將其作為最佳化目標量度。

+++
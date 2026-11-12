---
keywords: 活動url；url；不同的url
description: 探索如何在A/B、體驗鎖定目標或多變數測試活動中設定[!UICONTROL 活動URL]，以定義測試頁面並確保精確的測試設計。
title: A/B、體驗鎖定目標或多變數測試活動中的活動URL為何？
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
reason: republish
TQID: 'https://experienceleague.adobe.com/arQWsSfBKYtrayq9AI8ejU1T-Uor-oL5j2Sp2JKKXZE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 25%
---
# 活動 URL {#ab-activity-url}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何指定A/B、體驗鎖定目標(XT)或多變數測試(MVT)活動的活動URL、如何顯示不同的頁面，以及如何為更多頁面或區段新增規則。

>[!ENDSHADEBOX]

[!UICONTROL 活動URL]決定活動中使用的頁面。 這是在[!UICONTROL 視覺化體驗撰寫器] (VEC)或[!UICONTROL 表單式體驗撰寫器]中開啟的頁面（當活動設計於[!DNL Adobe Target]中時）。

## 指定活動URL {#specify-url}

在建立活動期間出現提示時，請指定活動 URL。 輸入完整的URL （包括`https://`），然後按一下&#x200B;**[!UICONTROL 「建立」]**。

>[!NOTE]
>
>[!DNL Target]不會區分URL通訊協定（[!DNL https]和[!DNL http]）。 因此，[!DNL `http://www.adobe.com`]和[!DNL `https://www.adobe.com`]都相符。

如果您指定的網站URL不包括[!DNL Target] [at.js JavaScript資料庫或 [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}，則無法選取頁面元素。

## 顯示其他頁面 {#different-page}

依預設，VEC或[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)會開啟[視覺化體驗撰寫器設定](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的頁面。 您可以在活動建立期間指定不同的頁面。

若要在VEC開啟之後顯示不同的頁面：

1. 在&#x200B;**[!UICONTROL 體驗]**&#x200B;頁面上，按一下頁面頂端的&#x200B;**[!UICONTROL 設定]**，然後選取&#x200B;**[!UICONTROL 頁面傳送]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;欄位中指定URL。

1. 完成後，按一下&#x200B;**[!UICONTROL 「儲存」]**。

根據預設，VEC 不允許對包含 JavaScript 的元素進行變更，例如旋轉橫幅。 如果您想要能夠使用VEC更改這些元素，可以關閉&#x200B;**[!UICONTROL 使用JavaScript]**&#x200B;呈現。

>[!NOTE]
>
>如果您在對一或多個體驗的頁面進行變更之後變更 URL，則體驗會使用新頁面進行重設，而您所進行的變更會遺失。

## 為更多頁面或區段新增規則 {#add-rules}

若要新增更多頁面或區段至活動，請在&#x200B;**[!UICONTROL 頁面傳送]**&#x200B;設定中按一下&#x200B;**[!UICONTROL 新增規則]**，然後在完成時按一下&#x200B;**[!UICONTROL 儲存]**。

其他規則可以根據以下任何項目:

* URL
* 網域
* 路徑
* 雜湊 (#) 片段
* 查詢
* mbox 參數
* 自訂

其他規則可以用AND或OR聯結到活動URL。 您新增的所有規則會使用「與」彼此進行評估。

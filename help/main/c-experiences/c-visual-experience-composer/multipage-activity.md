---
keywords: 多頁面; 歷程測試; 多頁面活動
description: 瞭解如何在Adobe [!DNL Target]中建立多頁活動，可讓您使用每個頁面專屬的設計，在多個頁面上建立劇本。
title: 如何建立多頁活動？
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
TQID: 'https://experienceleague.adobe.com/ZFqgbNp-sLF-ahG-uXKvWY0XPcxO0oZScGkpNX8hDHY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
    internal-label: Mobile experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 13%
---
# 多頁活動 {#multipage-activity}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何使用多頁活動來建立多個頁面的劇本，每個頁面都有專屬的設計。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的多頁活動會在多個頁面上建立劇本，每個頁面都有專屬的設計。

例如，可以測試購買量超過特定金額的免費送貨優惠。 優惠方案可出現在登入頁面、類別頁面和某些產品頁面上，且大小不同，位置也不同。 顯著的優惠方案可顯示在首頁上，然後以其他相關頁面上的較小優惠方案來強化。

多頁活動也可以為案頭和非回應式行動網站定義不同的版面配置。 如果網站有獨立的行動網站，例如[!DNL m.mysite.com]而非[!DNL `www.mysite.com`]，請建立多頁活動，新增[!DNL m.mysite.com]做為獨立的頁面，然後套用行動編輯，對相同體驗中的案頭版和行動版進行適當的變更。 若為回應式行動網站，請使用[行動體驗編](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)。

>[!NOTE]
>
>多頁面活動是針對同一產品建議在多個頁面上有不同外觀的活動而設計。 如果產品建議在所有頁面上皆呈現相同外觀，使用[範本測試](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages)會更有效率。

您可以為多頁測試中的每個頁面指定範本規則。 例如，將範本規則套用至多頁測試的類別頁面，即可在首頁和所有類別頁面中執行多頁測試。 請參閱[在類似頁面上包含相同體驗](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages)。

## 將頁面新增至活動 {#add-pages}

新增至活動的每個頁面都可以有自己的優惠方案設計。

1. 按一下&#x200B;**[!UICONTROL 設定]**&#x200B;圖示（ ![設定圖示](/help/main/assets/icons/Setting.svg) ）。

1. 按一下&#x200B;**[!UICONTROL 「新增其他頁面」]**。

   畫面左側會顯示&#x200B;**[!UICONTROL 頁面]**&#x200B;窗格。

   ![設定圖示](assets/vec_edit_4.png)

1. 指定頁面並設定預設頁面。

   按一下&#x200B;**[!UICONTROL 新增頁面]** （![新增圖示](/help/main/assets/icons/Add.svg)）以新增其他頁面，指定頁面名稱和URL，然後按一下&#x200B;**[!UICONTROL 儲存]**。

1. 使用[!UICONTROL 視覺化體驗撰寫器]來設計選件在每個頁面上的外觀。

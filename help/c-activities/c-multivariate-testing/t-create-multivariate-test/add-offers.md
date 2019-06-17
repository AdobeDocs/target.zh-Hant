---
description: 使用Adobe Target中的Visual Experience Composer(CMS)建立您要包含在多變數測試(MVT)中的選件。
seo-description: 使用Adobe Target中的Visual Experience Composer(CMS)建立您要包含在多變數測試(MVT)中的選件。
seo-title: 使用Adobe Target在多變數測試(MVT)中建立組合
title: 建立組合
uuid: 2ee47bf5-f8b3-41e2-b9a5-0ff4ab175373
translation-type: tm+mt
source-git-commit: 0730d5f8f6aa2b72c2069c81d6e5a0183489e91c

---


# 建立組合{#create-combinations}

使用Adobe Target中的Visual Experience Composer(CMS)建立您要包含在多變數測試(MVT)中的選件。

如需使用CMS建立和編輯選件的詳細資訊，請參閱 [Visual Experience Composer選項](/help/c-experiences/c-visual-experience-composer/viztarget-options.md)。

>[!NOTE]
>
>在頁面上選取物件時，除了原先選取的元素，您可以按一下 **[!UICONTROL 「展開選取範圍」]** 以選取父元素。選取任何上層元素時，系統會自動選取該元素的所有下層。您可以展開選取範圍多次。
>
>您也可以使用 [DOM路徑](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) 來瀏覽元素。

## 影像選件 {#section_A48333211DB149ED926AE467D0032914}

在一個位置內測試多個影像選件，以判斷最成功的影像。

1. 按一下頁面上的影像，然後選取 **[!UICONTROL 「變更影像」]**。

   ![變更影像選項](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changeimage.png)

1. 選取要納入測試中的所有影像，然後按一下 **[!UICONTROL 「新增」]**。

   ![選取用於新增影像的「內容」對話方塊](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/addimage.png)

每個影像會變成該位置中的個別體驗。

## HTML 選件 {#section_DF016101AFA9412C9B99862C23DE77B1}

在一個位置內測試多個文字/HTML 選件，以判斷最成功的選件。

1. 按一下頁面上的 HTML 選件，然後按一下 **[!UICONTROL 「變更文字/HTML」]**。

   ![變更文字/HTML](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changehtml.png)

1. 按一下 **[!UICONTROL 「新增文字/HTML 選件」]**，將選件命名，然後輸入或貼上文字/HTML 選件的程式碼。

   ![編輯選件](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   對於您要包含的任何其他文字/HTML 選件，重複這樣做。

1. 按一下 **[!UICONTROL 「儲存」]**。

每個文字/HTML 選件會變成該位置中的個別體驗。

## 最佳實務 {#section_2E98C23D2F1A460FA732A31799CE6291}

* 請勿在測試中包含太多不必要的位置。您在測試中包含的每個體驗，將會明顯增加達到滿意結果所需的流量和時間。例如，假設您的頁面元素各有三個選件，總共有九種可能的組合 (3x3)。在三個元素中，有兩個包含三個可能的選件，有一個有兩個選件，總共有 18 種選項 (3x3x2)。每增加一個元素和選件，數字便會顯著增加。
* 建立多變數測試時，若您認可之後必須使用離線報表進行分析的警告，您現在可以從測試排除超過 10% 的體驗。
* 利用預覽功能來避免不需要的內容組合。例如，您可能有兩個影像在相同件商品或服務上提供不同的折扣。在相同個頁面上同時顯示這些影像不合邏輯，很可能造成混淆。
* 使用流量估算程式來確定您的測試是針對頁面所接收的流量而設計。確定流量估算程式對您的測試組態指示綠燈，使得您可以取得所需的結果。
* 您必須至少測試三個元素。如果少於這個數目，請執行一系列的A/B 測試。
* 建議您每個元素的替代項目之間必須有大幅差異。
* 雖非必要，但每個元素最好有相同的替代項數量。


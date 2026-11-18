---
keywords: mvt；多變數測試；選件；組合
description: 瞭解如何在Adobe [!DNL Target]中使用[!UICONTROL 視覺化體驗撰寫器] (VEC)來建立您要包含在[!UICONTROL 多變數測試] (MVT)中的選件。
title: 如何在[!UICONTROL 多變數測試] (MVT)中建立組合？
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
TQID: 'https://experienceleague.adobe.com/3vxuP07ZViE1etmmvBdYVHIOrtZqRZfL3nE5RMHo9rU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 29%
---
# 建立組合 {#create-combinations}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何建立構成&#x200B;**[!UICONTROL 多變數測試]**&#x200B;組合的影像和HTML選件。

>[!ENDSHADEBOX]

在&#x200B;**[!UICONTROL 多變數測試]** (MVT)中，每個位置都包含數個選件，而各個位置上的每個選件組合都是一個體驗。 在[!DNL Adobe Target]中使用&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)來建立您要包含在測試中的選件。

如需有關如何使用 VEC 建立及編輯產品建議的詳細資訊，請參閱[可視化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

>[!NOTE]
>
>在頁面上選取物件時，除了原先選取的元素，您可以按一下&#x200B;**[!UICONTROL 展開選取範圍]**&#x200B;以選取父元素。 選取任何上層元素時，系統會自動選取該元素的所有下層。 您可以展開選取範圍多次。
>
>您也可以使用 [DOM 路徑](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)來導覽元素。

## 影像產品建議 {#image-offers}

在一個位置內測試多個影像選件，以判斷最成功的影像。

1. 按一下頁面上的影像，然後選取&#x200B;**[!UICONTROL 變更影像選件]**。

   ![變更影像選件功能表](../assets/multivariate-1.png)

1. 從&#x200B;**[!UICONTROL 影像選件]**&#x200B;對話方塊中，選取要包含在測試中的所有影像，然後按一下&#x200B;**[!UICONTROL 新增]**。

   ![變更影像選件功能表](../assets/multivariate-3.png)

每個影像會變成該位置中的個別體驗。

## HTML優惠方案 {#html-offers}

在一個位置內測試多個 HTML 產品建議，以判斷最成功的產品建議。

1. 按一下頁面上的HTML選件，然後按一下&#x200B;**[!UICONTROL 變更HTML選件]**。

   ![變更HTML選件功能表](../assets/multivariate-2.png)

1. 選擇您的HTML選件，然後按一下&#x200B;**[!UICONTROL 建立選件]**、**[!UICONTROL HTML選件]**。

   ![變更HTML選件功能表](../assets/multivariate-4.png)

1. 為選件命名，輸入或貼上HTML選件的程式碼，然後按一下[建立]。****

   重複此步驟，加入您要加入的任何其他HTML選件。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

每個 HTML 產品建議會變成該位置中的個別體驗。

有關啟動測試前要包含多少組合以及如何檢閱這些組合的建議，請參閱[多變數測試最佳作法](/help/main/c-activities/c-multivariate-testing/best-practices.md#create)。

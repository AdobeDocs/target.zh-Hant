---
keywords: 鎖定目標; 體驗; 新增體驗; 體驗新增
description: 瞭解如何在 [!DNL Adobe Target]中使用[!UICONTROL Visual Experience Composer] (VEC)。
title: 如何在A [!DNL Target] A/B活動中新增體驗？
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: 6fa1b428e7955bae976649c42d3eb9b2ddc2c79f
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 43%

---

# 新增體驗

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)提供視覺化介面，用於新增及編輯您頁面上的體驗。

如需關於體驗的其他詳細資料，請參閱[體驗](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)。

1. 從VEC的&#x200B;**[!UICONTROL Experiences]**&#x200B;頁面，按一下&#x200B;**[!UICONTROL Add Experience]**。

   ![新增體驗選項](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/add-experience.png)

   >[!NOTE]
   >
   >如果您要將體驗鎖定到某個對象，則必須先選取對象，才可以新增體驗。系統會出現訊息以提醒您選擇對象。

1. 選取您要變更的元素，並進行所需的變更。

   當您將滑鼠停留在頁面上的元素上時，這些元素會反白顯示。 任何強調顯示的元素可使用VEC進行更改。

   如果您在使用[!DNL Target Classic] （先前為[!DNL Test&Target]）的頁面上建立[!DNL Target]要求，該[!DNL Target]要求會顯示為顯示要求名稱的元素，且可如同任何其他元素般加以修改。

   如需可以在顯示頁面上執行元素以變更體驗的動作清單，請參閱[可視化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

   >[!NOTE]
   >
   >如果您從主要頁面以外的來源 (例如在 `akamai.net` 上託管並在 `example.com` 上傳送的影像) 傳送影像，該影像不會顯示在流程圖中所顯示頁面的縮圖中。

1. 當您完成體驗設計時，請按一下「**[!UICONTROL Save]**」。

## 重新命名體驗

1. 在[!UICONTROL A/B Test]或[!UICONTROL Experience Targeting] (XT)活動中的體驗上按一下&#x200B;**[!UICONTROL Rename Experience]**&#x200B;圖示，將體驗命名為新的名稱。

   ![重新命名體驗](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/rename-experience.png)

2. 指定新名稱。

   為體驗命名或重新命名時，不得使用下列字元：

   | 字元 | 說明 |
   |--- |--- |
   | / | 正斜線 |
   | ? | 問號 |
   | # | 數字符號 |
   | : | 冒號 |
   | = | 等號 |
   | + | 加號 |
   | - | 減號 |
   | @ | 「@」符號 |

## 重新導向至 URL

1. 按一下[!UICONTROL A/B Test]或[!UICONTROL Experience Targeting] (XT)活動之體驗上的&#x200B;**[!UICONTROL More]**&#x200B;圖示（垂直省略符號）圖示，然後按一下&#x200B;**[!UICONTROL Redirect to URL]**。

   如需詳細資訊，請參閱[重新導向至 URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)。

   **注意**: 為體驗命名或重新命名時，不得使用下列字元:

   | 字元 | 說明 |
   |--- |--- |
   | / | 正斜線 |
   | ? | 問號 |
   | # | 數字符號 |
   | : | 冒號 |
   | = | 等號 |
   | + | 加號 |
   | - | 減號 |
   | @ | 「@」符號 |

1. 指定您要重新導向體驗的URL。

1. （條件式）勾選&#x200B;**[!UICONTROL Include Current Query Parameters]**&#x200B;核取方塊。

## 複製體驗

您可以複製[!UICONTROL A/B Test]中的體驗，不必從頭再次建立體驗，即可進行微幅變更。

1. 在&#x200B;**[!UICONTROL Experiences]**&#x200B;頁面（三步驟引導式工作流程的第一步），按一下垂直的省略符號圖示> **[!UICONTROL Duplicate]**。

   ![重複體驗選項](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/duplicate-experience.png)

## 刪除體驗

1. 在&#x200B;**[!UICONTROL Experiences]**&#x200B;頁面（三步驟引導式工作流程的第一步），按一下垂直的省略符號圖示> **[!UICONTROL Duplicate]**。

   ![刪除體驗選項](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/delete-experience.png)

## 訓練影片：使用[!UICONTROL Visual Experience Composer]

以下影片提供有關使用[!UICONTROL Visual Experience Composer]選項的資訊。 (7:17)

* 變更頁面的內容
* 變更頁面的配置

>[!VIDEO](https://video.tv.adobe.com/v/17399)

---
description: 設計可定義建議出現在頁面上的方式。
keywords: 建議設計;建立設計;複製設計
seo-description: 設計可定義建議出現在頁面上的方式。
seo-title: 建立設計
solution: Target
title: 建立設計
title-outputclass: premium
topic: Premium
uuid: 812258e0-8d28-4ef3-b745-45ed694fcabe
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) 建立設計{#create-a-design}

設計可定義建議出現在頁面上的方式。

您可以使用預設的設計來建立 [!UICONTROL Recommendations] 設計，或建立自訂的設計。**[!UICONTROL 「Recommendations」&gt;「設計」]畫面會顯示預設設計卡片和您已建立的任何設計。**您不能編輯或刪除預設設計。

1. 在**[!UICONTROL 「Recommendations &gt; 設計」]**畫面上，將游標移至您要建立的設計的卡片。

   ![](assets/Card_CopyDesign.png)

1. 若要複製和編輯現有設計，請按一下**[!UICONTROL 「複製」]**圖示。

   或

   若要建立自訂設計，請在**[!UICONTROL 「Recommendations」&gt;「設計」]畫面上按一下****「建立設計」[!UICONTROL 。]**

   ![](assets/createDesign.png)

1. 新增**[!UICONTROL 內容名稱]**。

   使用預設設計時，設計名稱和「Copy」將出現在**[!UICONTROL 「內容名稱」]欄位中。**您可以編輯名稱。1.(可選) 按一下來選取要在設計卡片上顯示的影像。
1. 編輯設計**[!UICONTROL 程式碼]**。

   Recommendation 設計使用開放式原始碼 Velocity 設計語言。有關 Velocity 的資訊，請參閱 [](https://velocity.apache.org)https://velocity.apache.org。

   設計可以是 HTML 或非 HTML。根據預設，HTML 設計會以 <div> 標籤包住，以允許在 Web 環境中進行點擊追蹤。非 HTML 設計用於非 Web 環境，在其中無法進行點擊追蹤。

   >[!NOTE]
   >
   >可在設計中參照 (明確寫在程式碼中或透過迴圈) 的實體數上限是 99。

1. 按一下**[!UICONTROL 「儲存」]**。

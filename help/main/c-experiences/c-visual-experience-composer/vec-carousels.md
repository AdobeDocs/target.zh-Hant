---
keywords: 可視化體驗撰寫器; VEC; 輪播
description: 瞭解如何建立可以在Adobe [!DNL Target]視覺化體驗撰寫器(VEC)中編輯的輪播。
title: 如何在視覺化體驗撰寫器中建立輪播？
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
TQID: 'https://experienceleague.adobe.com/RN04MJgC49BI2-h2e-i-kgSRTejpLHzKACm-hOv2VCE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 2%
---
# 建立可在[!UICONTROL 視覺化體驗撰寫器]中運作的輪播 {#vec-carousels}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何建立可以在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)中編輯的輪播。

>[!ENDSHADEBOX]

可以在[!DNL Adobe Target] **[!UICONTROL 視覺化體驗撰寫器]** (VEC)中編輯使用以下結構建立的輪播。 此結構可讓每個幻燈片的選取器保持有效，因此[!DNL Target]一律會識別正確的幻燈片，即使顯示的幻燈片在VEC中的頁面載入數秒後有所變更。

1. 將幻燈片建立為靜態HTML預留位置，其中一個幻燈片為可見幻燈片，其他幻燈片則依類別隱藏。

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. 僅使用CSS設計外觀和風格。 請勿對此使用JavaScript。

   >[!NOTE]
   >
   >在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;中使用&#x200B;**[!UICONTROL 使用JavaScript]**&#x200B;呈現選項，以及自訂程式碼時，目前不支援該選項。

1. 只更新類別名稱來顯示下一張幻燈片：隱藏其他幻燈片，並使用計時器或動畫顯示下一張幻燈片。 切勿使用JavaScript更新DOM結構。

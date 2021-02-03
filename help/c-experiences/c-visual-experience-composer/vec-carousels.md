---
keywords: 可視化體驗撰寫器; VEC; 輪播
description: 本主題說明如何建立可在Adobe Target Visual Experience Composer(VEC)中編輯的轉盤。
title: 建立可在視覺體驗撰寫器中運作的轉盤
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 69%

---


# 建立可在可視化體驗撰寫器中運作的輪播

本主題說明如何建立可在[!DNL Adobe Target] [!UICONTROL  Visual Experience Composer](VEC)中編輯的轉盤。

使用下列步驟時，[!DNL Target] 一律知道已選取投影片會有正確投影片的「選取器」，即便在幾秒後它在可視化體驗撰寫器中已變更。

1. 建立靜態的 HTML 預留位置。

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. 新增 CSS 以設計外觀和風格。

   請勿對此使用 JavaScript。

   >[!NOTE]
   >
   >如果是在可視化體驗撰寫器中使用[!UICONTROL 使用 JavaScript 呈現]選項搭配自訂代碼，則目前不支援該選項。

1. 僅更新 classNames 以隱藏其他項目，並使用計時器/動畫顯示下一個。

   永遠不要使用 JavaScript 更新 DOM 結構。
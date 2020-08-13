---
keywords: Visual Experience Composer;VEC;carousel
description: 此主題顯示如何建立可以在可視化體驗撰寫器 (VEC) 中編輯的輪播。
title: 建立可在可視化體驗撰寫器中運作的輪播
feature: vec
subtopic: Multivariate Test
topic: Standard
uuid: 19538f6e-445c-49ca-9f0d-b49fc330b721
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 100%

---


# 建立可在可視化體驗撰寫器中運作的輪播{#creating-carousels-that-work-in-the-visual-experience-composer}

此主題顯示如何建立可以在可視化體驗撰寫器 (VEC) 中編輯的輪播。

使用下列步驟時，[!DNL Target] 一律知道已選取投影片會有正確投影片的「選取器」，即便在幾秒後它在可視化體驗撰寫器中已變更。

1. 建立靜態的 HTML 預留位置。

   ```
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
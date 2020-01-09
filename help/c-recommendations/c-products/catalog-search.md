---
keywords: catalog;search
description: Adobe Target 中的目錄搜尋可協助您在目錄中尋找產品或內容。
title: Adobe Target 中的目錄搜尋
uuid: e0876963-5905-4850-a615-953e435f26e9
translation-type: tm+mt
source-git-commit: 1a1e1a0f2ff802ee630c47ceeb3241c55eb2cb65

---


# ![PREMIUM](/help/assets/premium.png) 目錄搜尋{#catalog-search}

目錄搜尋可協助您在目錄中尋找產品或內容。

To access catalog search, click **[!UICONTROL Recommendations]**>**[!UICONTROL  Catalog Search]**.

您可以從選項功能表中 (按一下搜尋欄位的向下箭頭時出現) 選取搜尋選項，以精簡搜尋。

![](assets/searchproductsmenu.png)

搜尋選項包含下列項目:

* ALL
* 名稱
* 品牌
* 類別
* ID
* 訊息

**[!UICONTROL 全部]**會使用 OR 邏輯，涵蓋其他所有搜尋條件來搜尋。

在搜尋結果中，按一下&#x200B;**[!UICONTROL 環境]**篩選器，以指定您要顯示其中目錄的生產[主機群組環境](/help/administrating-target/hosts.md)。您也可以捲動瀏覽搜尋結果中的項目，以檢視縮圖和其他產品資訊。

「產品」旁顯示的數字代表在所指定環境中可用的總數之中，符合搜尋詞語的產品數量。

透過摘要檔案、API 或 mbox 更新收到更新時，目錄會自動重新整理。更新通常會在一小時內完成。如果正在進行更新，會顯示最新更新的開始時間。如果沒有任何正在進行的更新，會顯示最新更新的開始和結束時間。

## 根據進階搜尋建立集合或排除項目

您可以使用目錄搜尋頁面上的進階搜尋 ([!UICONTROL Recommendations] > [!UICONTROL 目錄搜尋] > [!UICONTROL 進階搜尋])，以建立[集合](/help/c-recommendations/c-products/collections.md)或[排除項目](/help/c-recommendations/c-products/exclusions.md)。

![另存為對話框](/help/c-recommendations/c-products/assets/save-as.png)

例如，使用 &quot;id > contains&quot; 建立搜尋之後，您就可以按一下[!UICONTROL 「另存新檔] > [!UICONTROL 集合或排除項目」]。

>[!IMPORTANT]
>
>「進階搜尋」功能不區分大小寫，不過傳送時傳回的產品會以區分大小寫的搜尋為依據。此不相符的情況可能導致混淆。使用「進階搜尋」功能來根據結果建立集合或排除項目時，務必注意大小寫。例如，如果您執行 &quot;Holiday&quot; 的搜尋，初始的搜尋清單結果會包含 &quot;Holiday&quot; 和 &quot;holiday&quot;。如果您之後建立一個目錄，目的要傳回包含 &quot;holiday&quot; 的產品，則只會傳回包含 &quot;holiday&quot; 的產品。不會傳回包含 &quot;Holiday&quot; 的產品。排除項目也是以類似的方式處理。

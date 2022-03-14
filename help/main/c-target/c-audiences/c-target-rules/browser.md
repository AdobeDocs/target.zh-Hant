---
keywords: 瀏覽器選項;類型;瀏覽器類型;瀏覽器語言;語言;版本;瀏覽器版本
description: 瞭解如何在 [!DNL Adobe Target] 目標用戶在訪問您的頁面時使用特定瀏覽器或特定瀏覽器選項。
title: 是否可以基於瀏覽器類型來定向訪問者？
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 76%

---

# 瀏覽器

您可以鎖定造訪您的頁面時使用特定瀏覽器或特定瀏覽器選項的使用者。

下列瀏覽器可鎖定作為目標:

* Chrome
* Firefox
* Safari
* Internet Explorer
* Microsoft Edge
* Opera
* iPad
* iPhone|

鎖定目標瀏覽器有兩種方法:

* **預先建立的對象:**&#x200B;如果您想鎖定使用特定瀏覽器來造訪網站的對象為目標，請使用預先建立的對象。例如，如果您提供 Chrome 擴充功能，則只需要鎖定 Chrome 使用者作為目標。

   1. 設定活動時，從下拉清單中選擇瀏覽器。

      此選項只會將活動的目標鎖定在使用指定瀏覽器的訪客。

      ![目標Chrome用戶](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **自定義瀏覽器訪問群體規則：** 自定義的訪問群體允許您針對多個瀏覽器，或為特定瀏覽器、瀏覽器版本或瀏覽器語言設定規則或排除。 此功能在基於瀏覽器屬性確定活動目標時提供了極大的靈活性。

   1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
   1. 命名訪問群體並添加可選說明。
   1. 拖放 **[!UICONTROL 瀏覽器]** 到「受眾構建器」。

      ![規則>瀏覽器](assets/target_browser.png)

   1. 按一下&#x200B;**[!UICONTROL 「選取」]**，然後選取下列其中一個選項:

      * **類型:** 將特定瀏覽器鎖定作為目標或排除。請參閱[類型](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56)。
      * **語言：** 目標或排除某些設定為使用特定語言的瀏覽器。 請參閱[語言](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1)。
      * **版本:** 將特定瀏覽器版本鎖定作為目標或排除。請參閱[版本](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF)。
   1. （可選）為受眾設定其他規則。
   1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

   以下示例顯示了包括版本91或92上的Microsoft邊緣用戶的受眾：

   ![目標邊緣91或92](assets/target_edge.png)

## 瀏覽器選項 {#concept_221D8EEF53CC45AEACEB17CF336A3658}

根據活動加入者的瀏覽器類型、語言或版本來鎖定或排除活動加入者。

### 類型 {#section_6ADC758F23F145B3A310151546D83D56}

將特定瀏覽器鎖定作為目標或排除。

選取&#x200B;**[!UICONTROL 「類型」]**，然後選擇等於或不等於。

* 等於: 將所選取的瀏覽器鎖定作為目標。
* 不等於: 排除所選取的瀏覽器。

選取一或多個瀏覽器。多個選項是使用「或」連接。

### 語言 {#section_7520D1AA464A45A6843EABE2D2B431A1}

將設為使用特定語言的特定瀏覽器鎖定作為目標或排除。

例如，如果選件只有英文版，您可以會將語言設為英文的瀏覽器鎖定作為目標。或者，如果頁面未啟用雙位元組功能，您可以排除設為東亞語言的瀏覽器。

在語言比位置更重要的情況下，透過包含或排除瀏覽器語言來鎖定目標訪客，將會比根據地理來鎖定目標更準確。例如，如果您提供以英文撰寫的文章，您可以將目標鎖定在說英語的國家/地區，或將設為英文的瀏覽器作為鎖定目標。對於不以英文為母語的國家/地區中說英語的人，鎖定目標瀏覽器可讓他們閱讀這篇文章。

選取&#x200B;**[!UICONTROL 「語言」]**，然後選擇等於或不等於。

* 等於: 將所選取的瀏覽器語言鎖定作為目標。
* 不等於: 排除所選取的瀏覽器語言。

選取一或多種語言。多個選項是使用「或」連接。

下列瀏覽器語言可鎖定作為目標或排除:

* 英文
* 法語
* 德文
* 日文
* 韓文
* 葡萄牙語
* 俄文
* 西班牙語
* 繁體中文

### 版本 {#section_37CC8CE45DA04E8682AE6388321BA6EF}

將特定瀏覽器版本鎖定作為目標或排除。

例如，如果頁面在 Internet Explorer 版本 11 或更早的版本中無法正確呈現，您可以建立對象來排除這些版本。在此情況下，您可以設定規則來指定瀏覽器類型等於 Internet Explorer，再新增第二個規則來指定版本小於或等於 11。

選取 **[!UICONTROL 「版本」]**，然後選取運算子:

* 等於
* 不等於
* 大於
* 大於或等於
* 小於
* 小於或等於

輸入版本號碼。在文字欄位中僅能輸入主要版本。指定的版本包含此次發行的任何次要版本。例如，如果指定版本10，則還包括版本10.1的訪問者。

多個選項是使用「或」連接。

## 訓練影片: 建立對象 ![Tutorial badge](/help/main/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

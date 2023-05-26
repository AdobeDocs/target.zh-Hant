---
keywords: 鎖定目標;目標類別;目標條件;audience manager;自訂設定檔參數;訪客設定檔;自訂使用者參數;目標規則
description: 瞭解如何使用類別（例如瀏覽器、地理、網路、作業系統、訪客設定檔）來鎖定目標內容。
title: 對象有哪些類別？
feature: Audiences
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 50%

---

# 對象的類別

您可以使用以下專案鎖定多個類別屬性中的任一個： [!DNL Adobe Target]. 若要為每個屬性建立鎖定目標規則（或群組），請將所需屬性拖放至「對象產生器」窗格。

![對象的屬性](/help/main/c-target/c-audiences/assets/attributes.png)

選取特定類別時，您可以套用一個或多個定位條件。例如，在「地理」類別中，定義如下的規則: City=San Francisco。新增多個值會建立一個 OR 條件。訪客只需要符合其中一個值，就算滿足目標條件。如果要在相同參數上使用 AND 條件，請建立自訂運算式目標。

建立規則之後，按一下&#x200B;**[!UICONTROL 完成]**。此規則的摘要會顯示在要定位的那一層級的定位連結旁。

您可以藉由新增更多條件，或在其他類別中建立額外條件，以進一步重新定義規則。例如，您只能鎖定從Google存取您網站的舊金山Firefox使用者。 設定 [!UICONTROL 地理] 類別來鎖定來自舊金山、 [!UICONTROL 瀏覽器] 類別來鎖定使用Firefox的使用者，以及 [!UICONTROL 流量來源] 類別以定位來自的使用者 [!UICONTROL 來自Google]. 跨類別建立的規則會與AND運運算元結合。

若要建立包含跨類別之OR運算的複雜目標規則，請建立運算式目標。

您也可以鎖定自訂設定檔參數和 `user.` 參數。新增對象時，請拖放 **[!UICONTROL 訪客設定檔]**，然後選擇要用來鎖定目標活動的引數。 如果未顯示所需的引數，表示引數並未由mbox引發。

使用搜尋方塊來搜尋您的[!UICONTROL 對象]清單。您可以搜尋對象名稱的任何部分，或您可以將特定字串放在引號內。

您可以排序 [!UICONTROL 對象] 依對象名稱或上次修改日期列出。 若要依名稱排序，請按一下欄標題，然後選擇依遞增或遞減順序來顯示對象。

## 訓練影片：建立對象 ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

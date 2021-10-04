---
keywords: 鎖定目標;目標類別;目標條件;audience manager;自訂設定檔參數;訪客設定檔;自訂使用者參數;目標規則
description: 了解如何使用類別（例如瀏覽器、地理、網路、作業系統、訪客設定檔）來鎖定內容。
title: 對象的類別為何？
feature: Audiences
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
source-git-commit: b74cccdc43c34367819ed8a908a304b567d7ecbb
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 50%

---

# 對象的類別

您可以使用[!DNL Adobe Target]鎖定數個類別屬性中的任何一個。 若要針對每個屬性建立目標規則（或群組），請將所需的屬性拖放至Audience Builder窗格中。

![對象的屬性](/help/c-target/c-audiences/assets/attributes.png)

選取特定類別時，您可以套用一個或多個定位條件。例如，在「地理」類別中，定義如下的規則: City=San Francisco。新增多個值會建立一個 OR 條件。訪客只需要符合其中一個值，就算滿足目標條件。如果要在相同參數上使用 AND 條件，請建立自訂運算式目標。

建立規則之後，按一下&#x200B;**[!UICONTROL 完成]**。此規則的摘要會顯示在要定位的那一層級的定位連結旁。

您可以藉由新增更多條件，或在其他類別中建立額外條件，以進一步重新定義規則。例如，您只能鎖定從Google存取您網站之舊金山的Firefox使用者。 設定[!UICONTROL Geo]類別，將目標定位為來自舊金山的使用者，將[!UICONTROL Browser]類別設為使用Firefox的目標使用者，將[!UICONTROL Traffic Sources]類別設為目標定位來自[!UICONTROL Google]的使用者。 跨類別建立的規則會與AND運算子結合。

若要建立包含跨類別OR操作的複雜目標規則，請建立運算式目標。

您也可以鎖定自訂設定檔參數和 `user.` 參數。新增對象時，請拖放&#x200B;**[!UICONTROL 訪客設定檔]**，然後選擇您要用來鎖定目標活動的參數。 如果未顯示所需的參數，則mbox尚未觸發參數。

使用搜尋方塊來搜尋您的[!UICONTROL 對象]清單。您可以搜尋對象名稱的任何部分，或您可以將特定字串放在引號內。

您可以依對象名稱或上次修改日期來排序[!UICONTROL 對象]清單。 若要依名稱排序，請按一下欄標題，然後選擇依遞增或遞減順序來顯示對象。

## 訓練影片：建立對象![教學課程徽章](/help/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

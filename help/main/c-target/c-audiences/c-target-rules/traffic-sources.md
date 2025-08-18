---
keywords: 鎖定目標;流量來源;目標流量來源;目標搜尋引擎;搜尋引擎;登陸頁面;目標登陸頁面;引用登陸頁面
description: 瞭解如何在Adobe [!DNL Target] 中建立受眾，根據參照至您網站的搜尋引擎或著陸頁面來鎖定訪客。
title: 我可以根據搜尋引擎或反向連結網站鎖定訪客嗎？
feature: Audiences
exl-id: 61902d29-36ea-4d9a-8650-f6f6690a545b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 53%

---

# 流量來源

在[!DNL Adobe Target]中建立受眾，根據參照至您網站的搜尋引擎或著陸頁面鎖定訪客。

例如，你可基於訪客瀏覽器、搜尋引擎或反向連結著陸頁面進行指向。反向連結著陸頁面是訪客為存取本作業目前頁面而點按的頁面。(例如，如果訪客在 Google 上按一下廣告，然後被帶往 `adobe.com` 的首頁，則引用登陸頁面就是 `google.com`。)

您可以合併多個流量來源建立一個複雜的目標規則。

1. 在[!DNL Target]介面中，按一下&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**。
1. &#x200B;
   1. 為對象命名並新增選擇性說明。
1. 將&#x200B;**[!UICONTROL Traffic Sources]**&#x200B;拖放至對象產生器窗格。

   ![target_traffic_source圖片](assets/target_traffic_source.png)

1. 按一下&#x200B;**[!UICONTROL Select]**，然後選取下列其中一個選項：

   * **[!UICONTROL From Baidu]**
   * **[!UICONTROL From Bing]**
   * **[!UICONTROL From Google]**
   * **[!UICONTROL From Yahoo]**
   * **[!UICONTROL Referring Landing Page: URL]**
   * **[!UICONTROL Referring Landing Page: Domain]**
   * **[!UICONTROL Referring Landing Page: Query]**

   根據您的選擇，您可能需要提供其他資訊（求值器和/或值）。

1. （選用）為對象設定其他規則。
1. 按一下 **[!UICONTROL Done]**。

您可以將目標鎖定在由特定搜尋引擎轉介至您的網站，或來自特定登陸頁面的使用者。

## 訓練影片：建立對象![Overview badge](/help/main/assets/overview.png)

此影片包括關於使用對象類別的資訊。

* 建立客群
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

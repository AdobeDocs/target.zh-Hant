---
keywords: visitor profile;target visitor profile
description: 在 Adobe Target 中建立受眾，將目標鎖定於符合特定設定檔參數的訪客。
title: Adobe Target觀眾中的訪客資料選項
feature: audiences
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 94%

---


# 訪客資料{#visitor-profile}

建立受眾以將目標鎖定於符合特定設定檔參數的訪客。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 為對象命名。
1. 按一下「**[!UICONTROL 新增規則]** > **[!UICONTROL 訪客設定檔]**」。

   ![](assets/target_visitor_profile.png)

1. 按一下&#x200B;**[!UICONTROL 「選取」]**，然後選取下列其中一個選項:

   訪客設定檔參數會透過 mbox (設定檔) 來傳遞。您可以將目標鎖定在新訪客或再度訪問的訪客，或包含所有使用者。

   * 新訪客
   * 再度訪問的訪客
   * 在其他測試中
   * 不在其他測試中
   * 工作階段首頁
   * 不是工作階段首頁
   * 類別相關性

   訪客設定檔會針對每個具有新 `mboxPC` 的 mbox 呼叫，建立於本機 Edge 記憶體。30 分鐘未使用後，設定檔會儲存至 Target 資料庫，並可從其他 Edge 存取。

   網站訪客在工作階段中途登入並取得 `3rdpartyId` 時，所有先前繫結至 `3rdPartyId` 的載入設定檔屬性都立即可用。

   您可以鎖定自訂設定檔參數和 `user.` 參數。選擇您要用來鎖定目標活動的參數。如果需要的參數並未出現，表示參數尚未由 mbox 觸發。

1. (可選) 按一下&#x200B;**[!UICONTROL 「新增規則」]**&#x200B;並設定對象的其他規則。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 訓練影片：建立觀眾![概觀標章](/help/assets/overview.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

---
keywords: 訪客設定檔;目標訪客設定檔
description: 瞭解如何在中建立對象 [!DNL Adobe Target] 定位符合特定設定檔引數（例如新訪客或回訪訪客、類別相關性等）的訪客。
title: 我可以鎖定符合特定設定檔引數的訪客嗎？
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 46%

---

# 訪客設定檔

在中建立對象 [!DNL Adobe Target] 以定位符合特定設定檔引數的訪客。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 為對象命名並新增選擇性說明。
1. 拖放 **[!UICONTROL 訪客設定檔]** 放入對象產生器窗格。

1. 按一下&#x200B;**[!UICONTROL 「選取」]**，然後選取下列其中一個選項:

   ![target_visitor_profile圖片](assets/target_visitor_profile.png)

   訪客設定檔參數會透過 mbox (設定檔) 來傳遞。您可以將目標鎖定在新訪客或再度訪問的訪客，或包含所有使用者。

   * [!UICONTROL 新訪客]
   * [!UICONTROL 回訪訪客]
   * [!UICONTROL 在其他測試中]
   * [!UICONTROL 不在其他測試中]
   * [!UICONTROL 工作階段首頁]
   * [!UICONTROL 不是工作階段首頁]
   * [!UICONTROL 類別相關性]

   訪客設定檔會針對每個具有新 `mboxPC` 的 mbox 呼叫，建立於本機 Edge 記憶體。閒置30分鐘後，設定檔會儲存至 [!DNL Target] 資料庫，並可從其他edge存取。

   網站訪客在工作階段中途登入並取得 `3rdpartyId`，所有先前連結至的載入設定檔屬性 `3rdPartyId` 立即可用。

   您可以鎖定自訂設定檔參數和 `user.` 參數。選擇您要用來鎖定目標活動的參數。如果未顯示所需的引數，表示引數並未由mbox引發。

1. （選用）為對象設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

## 訓練影片：建立對象 ![Overview badge](/help/main/assets/overview.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

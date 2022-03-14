---
keywords: 訪客設定檔;目標訪客設定檔
description: 瞭解如何在 [!DNL Adobe Target] 目標訪問者滿足特定的配置檔案參數，如新訪問者或返回訪問者、類別關聯性等。
title: 我能否瞄準符合特定配置檔案參數的訪問者？
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 47%

---

# 訪客設定檔

在 [!DNL Adobe Target] 目標符合特定配置檔案參數的訪問者。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 命名訪問群體並添加可選說明。
1. 拖放 **[!UICONTROL 訪問者簡介]** 對話框。

1. 按一下&#x200B;**[!UICONTROL 「選取」]**，然後選取下列其中一個選項:

   ![](assets/target_visitor_profile.png)

   訪客設定檔參數會透過 mbox (設定檔) 來傳遞。您可以將目標鎖定在新訪客或再度訪問的訪客，或包含所有使用者。

   * [!UICONTROL 新訪客]
   * [!UICONTROL 回訪訪客]
   * [!UICONTROL 在其他測試中]
   * [!UICONTROL 不在其他測試中]
   * [!UICONTROL 工作階段首頁]
   * [!UICONTROL 不是工作階段首頁]
   * [!UICONTROL 類別相關性]

   訪客設定檔會針對每個具有新 `mboxPC` 的 mbox 呼叫，建立於本機 Edge 記憶體。處於非活動狀態30分鐘後，配置檔案將保存到 [!DNL Target] 可從其他邊訪問。

   當站點訪問者在中間會話中登錄並獲取 `3rdpartyId`，所有先前載入的配置檔案屬性都與 `3rdPartyId` 的子菜單。

   您可以鎖定自訂設定檔參數和 `user.` 參數。選擇您要用來鎖定目標活動的參數。如果不顯示所需參數，則該參數未被mbox激發。

1. （可選）為受眾設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

## 培訓視頻：建立受眾 ![概述徽章](/help/main/assets/overview.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

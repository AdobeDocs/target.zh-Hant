---
keywords: 鎖定目標；衝突；衝突
description: 在Adobe Target中正確設定活動，防止相同頁面上發生內容傳遞衝突。
title: 如何避免活動衝突？
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
TQID: 'https://experienceleague.adobe.com/R6cwp4KnoYPO9Wxr47HswtBX6jKPJ0i-UGdtA1ZHawU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 18%
---
# 活動衝突 {#activity-collisions}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何使用&#x200B;**[!UICONTROL 衝突]**&#x200B;索引標籤來尋找可能傳送內容至相同頁面的活動。

>[!ENDSHADEBOX]

有多個活動設定成在相同頁面上提供內容時，就會發生活動衝突。 如果發生活動衝突，頁面上可能不會顯示預期的內容。

在[!DNL Adobe Target]中的&#x200B;**[!UICONTROL 活動概覽]**&#x200B;頁面上的&#x200B;**[!UICONTROL 衝突]**&#x200B;索引標籤會列出網站上的活動衝突，並顯示活動是否包含潛在衝突。 **[!UICONTROL 衝突]**&#x200B;清單有助於：

* 在設定新活動之前，識別頁面上是否已在執行測試
* 如果預期的內容沒有出現，請對活動進行疑難排解。

## 存取「衝突」標籤 {#access-collisions}

按一下&#x200B;**[!UICONTROL 活動]**，從清單中按一下所需的活動，然後存取&#x200B;**[!UICONTROL 衝突]**&#x200B;功能表。

![設定圖示](assets/collisions_1.png)

系統會列出相同 URL 上的所有活動，而無論每個活動中鎖定的任何對象為何。 索引標籤會列出可能衝突的活動。 如果衝突改變預期的體驗，請編輯活動。

## 讀取衝突清單 {#collisions-list}

**[!UICONTROL 衝突]**&#x200B;清單會顯示每個使用mbox且使用相同URL的[!DNL Target]案例。 對於每個潛在衝突，清單會顯示活動URL、可能發生衝突的mbox名稱，以及任何符合這兩個條件的活動。 如果有多個 Mbox，則每個皆會列出。

此清單也會顯示每個潛在碰撞的狀態和優先順序，以及其他資訊。 狀態和優先順序有助於判斷發生衝突的可能性。 針對兩個可能衝突的活動：

* 如果某個活動目前不在作用中，則不會發生衝突。 只有當非使用中活動變為使用中時，才可能發生衝突。
* 如果具有相同優先順序和相同對象的兩個已上線活動之間可能發生衝突，則會發生衝突。 可以變更優先順序或狀態以防止衝突。
* 如果對象不同，則仍可能會發生衝突，因為特定訪客可能屬於多個對象。

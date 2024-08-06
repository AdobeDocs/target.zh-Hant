---
keywords: 鎖定目標；衝突；衝突
description: 在Adobe Target中正確設定活動，防止相同頁面上發生內容傳遞衝突。
title: 如何避免活動衝突？
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
source-git-commit: 5c963e97dae11326396a5c1c5e32d19f4d463c74
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 46%

---

# 活動衝突

[!DNL Adobe Target]中[!UICONTROL Activity Overview]頁面上的[!UICONTROL Collisions]索引標籤會列出您網站上的活動衝突。

有多個活動設定成在相同頁面上提供內容時，就會發生活動衝突。如果發生活動衝突，您可能無法在頁面上看到預期的內容。

[!UICONTROL Collisions]索引標籤可在活動概觀頁面上使用，且如果您的活動包含潛在衝突，此索引標籤會通知您。

若要存取「[!UICONTROL Collisions]」標籤，請按一下「**[!UICONTROL Activities]**」>從清單按一下需要的活動>然後按一下左側邊欄中的「**[!UICONTROL Collisions]**」。

系統會列出相同 URL 上的所有活動，而無論每個活動中鎖定的任何對象為何。開啟此標籤以顯示可能衝突的活動清單。如果衝突改變預期的體驗，請編輯活動。

[!UICONTROL Collisions]清單可協助您：

* 在設定新活動之前，查明頁面上是否已有測試在執行。
* 如果預期的內容沒有出現，請對活動進行疑難排解。

[!UICONTROL Collisions]清單會顯示每個[!DNL Target]狀況（其中使用mbox且使用相同URL）。 對於每個潛在衝突，清單會顯示活動URL、可能發生衝突的mbox名稱，以及任何符合這兩個條件的活動。 如果有多個 Mbox，則每個皆會列出。

此清單會列出每個潛在衝突的狀態和優先順序，還有其他資訊。您可以利用狀態和優先順序，協助您判斷衝突發生的可能性。考慮兩個可能衝突的活動。 如果某個活動目前不在作用中，則不會發生衝突。 只有當非使用中活動變為使用中時，才可能發生衝突。 如果具有相同優先順序和相同對象的兩個已上線活動之間可能發生衝突，則會發生衝突。 您可以變更優先順序和狀態來防止衝突。

即使對象不同，仍會有潛在衝突，因為特定訪客可能屬於多個對象。

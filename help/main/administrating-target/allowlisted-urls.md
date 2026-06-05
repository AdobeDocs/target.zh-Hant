---
keywords: 允許清單；遠端選件；管理；URL模式；驗證；活動；選件；萬用字元；規則運算式
description: 瞭解如何在Adobe Target管理區段中檢視、搜尋、新增和刪除遠端選件的允許清單URL，包括驗證行為和全帳戶範圍。
title: 管理已加入允許清單的遠端選件URL
feature: Administration & Configuration
topic: Implementation
role: Admin
level: Intermediate
solution: Target
product: Target
source-git-commit: 882c91244e5dae0977c8a6a1e5878525f497a720
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# 已加入允許清單的URL

列入允許清單的URL會定義貴組織可建立和執行[!DNL Adobe Target]體驗的受信任URL模式，包括當您使用遠端或重新導向選件時。 此清單可與[主機管理](/help/main/administrating-target/hosts.md)和[環境](/help/main/administrating-target/environments.md)搭配使用，但特別適用於允許的遠端選件URL模式和相關驗證。

若要管理加入允許清單的URL，請按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 加入允許清單的URL]**。

![已加入允許清單的URL頁面顯示URL清單、搜尋欄位和新增URL控制項](../administrating-target/assets/allowlist-1.png)

## 管理加入允許清單的URL {#add-url}

主表格會以單一欄列出每個允許清單的圖樣。 支援的專案可包含確切的URL、萬用字元路徑或您的組織接受用於遠端體驗的模式格式。

1. 按一下&#x200B;**[!UICONTROL 新增URL]**。

   ![](../administrating-target/assets/allowlist-2.png)

1. 在對話方塊中，輸入您的組織必須允許的URL或模式。

   ![](../administrating-target/assets/allowlist-3.png)

1. 儲存您的變更。

   在模式加入允許清單後，使用者可以建立或執行依賴該URL的活動和選件，但受限於您的其他[!DNL Target]規則。

1. 使用&#x200B;**[!UICONTROL 搜尋URL]**&#x200B;欄位來篩選資料表。

1. 若要刪除URL，請尋找您不再需要之模式的列，然後按一下![刪除](../administrating-target/assets/do-not-localize/Smock_Delete_18_N.svg)圖示。

   ![](../administrating-target/assets/allowlist-4.png)



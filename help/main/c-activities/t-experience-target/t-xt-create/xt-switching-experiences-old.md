---
keywords: 優先順序; 體驗建立; 體驗; 客群; 切換體驗; 可視化體驗撰寫器
description: 瞭解訪客如何隨著設定檔的演化，在 [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT)活動中的體驗之間切換。
title: 訪客可以在[!UICONTROL Experience Targeting]活動中切換體驗嗎？
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 43%

---

# 在[!UICONTROL Experience Targeting]中切換體驗

透過[!UICONTROL Experience Targeting]，您可以控制訪客在其設定檔演化時看到的體驗。

下列清單呈現的只是訪客設定檔可能演變的少數案例，您可能會想要根據這些變更呈現不同的內容：

| 藍本 | 詳細資料 |
|--- |--- |
| 地理位置 | 隨著訪客因商業或休閒目的周遊，他們可能會從不同地理位置檢視您的網站或行動應用程式。 |
| 客戶狀態 | 訪客在建立帳戶或購買產品之前，可能會被視為潛在商機。 |
| 類別相關性 | [!DNL Target]中的[類別相關性](/help/main/c-target/c-visitor-profile/category-affinity.md)功能會自動擷取訪客檢視的類別，然後針對鎖定目標目的計算該類別的訪客相關性。 例如，在您網站上檢視數篇關於特定主題的文章的訪客，會看到與該主題相關的內容。 |
| 星期 | 隨著週末到來，您可能要對訪客顯示關於電影、餐飲或其他娛樂形式的內容。 |

若要在[!DNL Target]中使用這些功能，在處理[!UICONTROL Experience Targeting]活動時，請務必瞭解下列資訊：

* **優先順序是由體驗的順序控制，由上到下。**&#x200B;如果訪客符合兩個以上對象的資格，則該訪客會從較高優先順序的體驗接收內容。
* **如果訪客開始符合較高優先順序體驗對象的資格，則訪客會在[!UICONTROL Experience Targeting]活動中的體驗之間切換。**

  例如，在下列活動設定中，某位訪客從美國存取了您的網站，然後周遊至德國並第二次造訪您的網站。在第一次造訪期間，此訪客符合體驗 A (美國訪客) 的資格。從德國檢視您的網站之後，此訪客切換到體驗 B (德國訪客)。

  ![優先順序美國 > 德國](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **如果訪客停止符合目前對象的資格，但開始符合較低優先順序體驗的資格，則訪客也會在體驗之間切換。**
* **如果訪客停止符合目前體驗的資格，而沒有符合其他體驗的資格，他們會看到預設內容。**

  例如，在下列活動設定中，某位訪客從美國存取了您的網站，然後周遊至法國並第二次造訪您的網站。在第一次造訪期間，此訪客符合體驗 A (美國訪客) 的資格。從法國檢視您的網站之後，此訪客會保留原始體驗。

  ![優先順序美國 > 德國](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **鎖定在「所有訪客」的體驗，可用作[!UICONTROL Experience Targeting]活動中的最後一個體驗，以「捕捉」未符合任何其他體驗資格的訪客。 如果鎖定在「所有訪客」的體驗不是順序中的最後一個，仍會評估列出低於此體驗的其他鎖定目標體驗。**

  例如，在下列活動設定中，某位訪客從美國存取了您的網站，然後周遊至德國並第二次造訪您的網站。在第一次造訪期間，此訪客符合體驗 A (美國訪客) 的資格。從德國檢視您的網站之後，此訪客仍會留在體驗A （美國訪客）。

  ![優先順序美國 > 所有訪客](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

  如果這不是您預期的行為，您可以建立新客群，明確定義為您鎖定客群的相片，如下列範例所示:

  ![優先順序美國 > 非美國](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **如果只有單一體驗[!UICONTROL Experience Targeting]活動，即使訪客不再符合將其放在該體驗中對象的資格，訪客仍會保留在該體驗中。**

  如果這不是您預期的行為，您可以建立另一個體驗，鎖定在相反的客群 (例如，與「美國」相對的「非美國」)。

  作為另一個選項，您可以建立[!UICONTROL A/B Test]活動，以100%的流量分配鎖定在您需要的對象，如下所示：

  ![優先順序一體驗](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **體驗的優先順序是由其在[!DNL Target] UI中的顯示順序（由上到下）所定義。**

  請務必注意訪客可能符合多個對象的案例。例如，如果您有兩個體驗：一個以「美國」為目標，另一個以「紐約」為目標，則位於紐約的訪客符合兩個對象的資格。 因此，您必須確保在[!DNL Target] UI中先定義「New York」體驗，然後再定義「United States」體驗。 此作法可確保目標較明確的「紐約」體驗有較高的優先順序，如下列範例所示：

  ![優先順序紐約 > 美國](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)

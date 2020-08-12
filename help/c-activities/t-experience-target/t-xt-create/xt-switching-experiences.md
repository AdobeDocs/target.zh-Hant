---
keywords: priority;experience create;priority;experience;audience;experience;switching experiences;visual experience composer
description: 關於訪客如何可以隨著其設定檔的演進，在體驗鎖定目標 (XT) 活動中的體驗之間切換的資訊。
title: 切換體驗鎖定目標中的體驗
feature: null
topic: Advanced,Standard,Classic
uuid: a4fa4cf0-509c-4c31-a778-09c5edacc9b0
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 100%

---


# 切換體驗鎖定目標中的體驗{#switching-experiences-in-experience-targeting}

關於訪客如何可以隨著其設定檔的演進，在體驗鎖定目標 (XT) 活動中的體驗之間切換的資訊。

>[!NOTE]
>
>**2017 年 9 月 21 日**
>
>隨著 2017 年 9 月 21 日的發行版本，Target 已變更將使用者放置到體驗鎖定目標 (XT) 活動中體驗的方式 (Target Classic 中的登陸頁面促銷活動)。針對所有新的和現有活動，使用者必須符合在每次曝光時的體驗鎖定目標規則，才能繼續看見體驗的內容以及在報表中計入。先前，如果使用者不再符合任何體驗的資格，從使用者上次符合資格的體驗起，使用者會繼續看見內容，並且在報表中計入。
>
>此變更已隨著此發行針對所有現有活動與針對發行後所建立新活動自動發生。如果需要舊方法 (9 月 21 日之前)，您可以使用設定檔指令碼建立對象，使得未來使用者只必須符合一個條件一次，便可繼續計入該對象。然後對活動中的每個體驗使用這些對象。

利用「體驗鎖定目標」，您可以控制隨著訪客的設定檔演進，訪客可看到的體驗。下列清單呈現的只是訪客的設定檔可以演進的一些案例，您可能想要呈現不同的內容:

| 藍本 | 詳細資料 |
|--- |--- |
| 地理位置 | 隨著訪客因商業或休閒目的周遊，他們可能會從不同地理位置檢視您的網站或行動應用程式。 |
| 客戶狀態 | 訪客在建立帳戶或購買產品之前，可能會被視為潛在商機。 |
| 類別相關性 | Target 中的[類別相關性](/help/c-target/c-visitor-profile/category-affinity.md)功能會自動擷取使用者造訪的類別，然後針對鎖定目標目的計算該類別的使用者相關性。例如，可以對檢視您的網站上關於特定主題之數個文章的訪客呈現與該主題相關的內容。 |
| 星期 | 隨著週末到來，您可能要對訪客顯示關於電影、餐飲或其他娛樂形式的內容。 |

若要在 [!DNL Target] 中利用這些功能，在處理 XT 活動時，請務必瞭解下列資訊:

* **優先順序是由體驗的順序控制，由上到下。**&#x200B;如果訪客符合超過兩個以上對象的資格，他或她會收到來自較高優先順序體驗的內容。
* **如果訪客開始符合較高優先順序體驗對象的資格，則訪客將在 XT 活動中的體驗之間切換。**

   例如，在下列活動設定中，某位訪客從美國存取了您的網站，然後周遊至德國並第二次造訪您的網站。在第一次造訪期間，此訪客符合體驗 A (美國訪客) 的資格。從德國檢視您的網站之後，此訪客切換到體驗 B (德國訪客)。

   ![優先順序美國 > 德國](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **如果訪客不再符合目前對象的資格，但開始符合較低優先順序體驗的資格時，訪客也將在體驗之間切換。**
* **如果訪客不再符合其目前體驗的資格，不且不符合另一個體驗的資格，訪客將看到預設內容。**

   例如，在下列活動設定中，某位訪客從美國存取了您的網站，然後周遊至法國並第二次造訪您的網站。在第一次造訪期間，此訪客符合體驗 A (美國訪客) 的資格。從法國檢視您的網站之後，此訪客將停留在原始體驗。

   ![優先順序美國 > 德國](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **鎖定在「所有訪客」的體驗，可用來做為體驗鎖定目標活動中的最後一個體驗，以「捕捉」未落入任何其他體驗的任何訪客。如果鎖定在「所有訪客」的體驗不是順序中的最後一個，將評估所列出低於此體驗的其他鎖定體驗。**

   例如，在下列活動設定中，某位訪客從美國存取了您的網站，然後周遊至德國並第二次造訪您的網站。在第一次造訪期間，此訪客符合體驗 A (美國訪客) 的資格。從德國檢視您的網站之後，此訪客將停留在體驗 A (美國訪客)。

   ![優先順序美國 > 所有訪客](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

   如果這不是您預期的行為，您可以建立新對象，明確定義為您鎖定對象的相片，如下列範例所示:

   ![優先順序美國 > 非美國](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **利用單一體驗 XT 活動，即使訪客不再符合將其放在該體驗中對象的資格，訪客亦將停留在體驗中。**

   如果這不是您預期的行為，您可以建立另一個體驗，鎖定在相反的對象 (例如，與「美國」相對的「非美國」)。

   作為另一個選項，您可以建立 A/B 活動，以 100% 的流量分配鎖定在您需要的對象，如下所示:

   ![優先順序一體驗](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **體驗的優先順序的定義方式是，透過其在 Target UI 中的顯示順序 (由上到下)。**

   請務必注意訪客可能符合多個對象的案例。例如，如果您有兩個體驗: 一個鎖定在「美國」而一個鎖定在「紐約」，位於「紐約」的訪客可能同時符合這兩個對象。因此，您必須確保在 Target UI 中「紐約」體驗的定義在「美國」體驗之前。這可確保更為鎖定的「紐約」體驗具有較高的優先順序，如下列範例所示:

   ![優先順序紐約 > 美國](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)


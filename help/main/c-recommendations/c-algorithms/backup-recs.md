---
keywords: 建議;備用
description: 瞭解如何在Adobe [!DNL Target Recommendations]中使用備份建議。
title: 使用備份推薦
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
TQID: 'https://experienceleague.adobe.com/TziWJoAuEdCqa7uMTpX0O0InnlnjtbPXP-0wzQ-FCM0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 18%
---
# 使用備份推薦 {#backup-recommendations}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解備份建議如何在[!DNL Adobe Target Recommendations]中填滿設計的剩餘位置。

>[!ENDSHADEBOX]

當建議沒有足夠的建議專案來填滿設計時，[!DNL Adobe Target]中的備份建議功能會顯示備份演演算法的結果，而非預設內容。 如果沒有備份建議，系統會向使用者顯示預設內容。

>[!NOTE]
>
>如需詳細資訊，包括說明使用&#x200B;**[!UICONTROL 部分設計呈現]**&#x200B;和&#x200B;**[!UICONTROL 顯示備份內容]**&#x200B;選項之結果的矩陣，請參閱建立條件[&#128279;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)的備份內容區段。

備份建議功能一律會使用網站上檢視次數最多的專案，在使用演演算法的資料後填滿任何剩餘的位置。 例如，一個設計被設定為顯示五個建議專案，但演演算法有足夠的資料填補五個位置中的兩個。 接著，備用建議功能會將其他三個位置填入檢視次數最多的專案。

從整個網站前 500 個最常檢視的產品中，隨機挑選備份建議。 備份建議的日期時段為 1 週。

500 個最常檢視的結果會依序排序，然後分割成每 20 個一組。 值區會依順序提供，但每個值區內的結果會隨機化並傳回至頁面，因此重新整理頁面的使用者會看到新的隨機結果。 如果集合的聯集和篩選規則的結果集小於20，則會從集合中隨機選取專案。

此分組程序表示備用建議會依下列順序顯示:

1. 檢視次數最多的20個專案，隨機。
1. 接下來20個檢視次數最多的專案，隨機進行。
1. 接下來的20個檢視次數最多的專案，隨機化等等。

若不進行分組，則會顯示檢視次數最多的第499個專案，然後是檢視次數最多的第200個專案，最後是檢視次數最多的第380個專案，以此類推。 分組可確保首先推薦檢視次數最多的專案。

如果專案分組到集合，為每個條件產生的備用建議也會使用該集合，因此只有集合中的專案會包含在備用建議中。 全域排除規則所排除的任何項目都不會做為備份建議。 從多批建議中移除重複部份。

預設會啟用備用建議，並隨機選取網站上最受歡迎的專案，以填滿設計中額外的位置。

使用備份建議通常是初始設定期間與實作團隊討論的一部分。 若要在實施後變更備份建議設定，請聯絡客戶經理。

當&#x200B;**[!UICONTROL 部分設計呈現]** （請參閱[備份內容](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)）未啟用且無法填滿設計時，將改為顯示備份建議（啟用時）或預設內容。

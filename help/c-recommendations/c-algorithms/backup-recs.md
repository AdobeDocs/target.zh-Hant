---
keywords: recommendation;backup;back up
description: 如果您在Adobe Target中使用備份建議功能，則任何沒有足夠建議項目的建議都不會顯示預設內容。 建議會改為顯示備份演算法的結果。
title: 使用備份建議 在Adobe Target Recommendations中
feature: criteria
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 83%

---


# ![PREMIUM](/help/assets/premium.png) 使用備用建議{#use-a-backup-recommendation}

如果您在Adobe Target中使用備份建議功能，則任何沒有足夠建議項目的建議都不會顯示預設內容。 建議會改為顯示備份演算法的結果。

如果您未使用備份建議，而建議沒有足夠的項目來顯示，則系統會對使用者顯示預設內容。

>[!NOTE]
>
>Create criteria](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)主題的[Content部分包含其他資訊，包括矩陣，說明搭配使用[!UICONTROL Partial Design Rendering]和[!UICONTROL Show Backup Recommendations]選項時，您將觀察到的結果。

使用演算法資料後，備份建議功能會始終使用網站上檢視次數最多的項目來填充任何剩余區段。例如，您的範本設定為顯示五個建議項目，且您使用的是&#x200B;*購買相關性*&#x200B;演算法。然而，您僅有足夠的資料來填充五個區段中的其中兩個，因此備份建議功能可用檢視次數最多的項目來填充另外三個區段。

從整個網站前 500 個最常檢視的產品中，隨機挑選備份建議。備份建議的日期時段為 1 週。

500 個最常檢視的結果會依序排序，然後分割成每 20 個一組。各組依序提供，但每一組內的結果會隨機化並傳回給頁面。如果使用者重新整理頁面，則會看到新的隨機化結果。如果結合集合與篩選規則而傳回的結果集小於 20，則會從集合中隨機選取。

此分組程序表示備用建議會依下列順序顯示:

1. 顯示 20 個最常檢視的項目、隨機化，然後
1. 顯示接下來 20 個最常檢視的項目、隨機化，然後
1. 顯示接下來 20 個最常檢視的項目、隨機化，
1. 以此類推。

如果備用建議不分組，可能會顯示第 499 個最常檢視的項目、接著第 200 個最常檢視的項目、接著第 380 個最常檢視的項目，以此類推。分組程序可確保最先建議檢視次數最多的項目。

>[!NOTE]
>
>如果您將項目群組至目錄，建議內針對每個演算法產生的備用建議也會使用該目錄，因此只有目錄中的項目會包含在備用建議中。

全域排除規則所排除的任何項目都不會做為備份建議。

備份建議會依預設啟用，並且會將隨機選取的網站上最熱門項目填入範本中的額外位置。

從多批建議中移除重複部份。

備份建議的使用通常是初始設定期間與實施團隊進行討論的內容之一。如要在實施後變更備份建議設定，請聯絡客戶經理。

如果「啟用部分設計呈現」(請參閱[內容設定](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)) 未啟用，且範本未顯示，則會改為顯示備份建議或預設內容。

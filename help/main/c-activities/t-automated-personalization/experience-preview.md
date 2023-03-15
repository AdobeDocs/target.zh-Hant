---
keywords: 體驗預覽; 體驗 URL; 產生 URL; 檢視體驗 URL
description: 了解如何使用體驗預覽URL來Adobe [!DNL Target] Automated Personalization活動，在活動上線之前直接在您的網站上查看體驗內容。
title: 如何在Automated Personalization活動中使用體驗預覽URL?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
exl-id: 9f329b8a-5f86-4cae-a3be-eed24fa0a9cd
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 51%

---

# 使用體驗預覽 URL 預覽 Automated Personalization 活動

可為產生體驗預覽URL [!DNL Target] [!UICONTROL Automated Personalization] 活動，在活動上線之前直接在您的網站上查看體驗內容，以供預覽和QA之用。 體驗預覽URL會略過鎖定目標以強制檢視特定體驗。

>[!NOTE]
>
>您可以建立其他類型的體驗預覽URL [!DNL Target] 活動。 不過，程式稍有不同。 如需詳細資訊，請參閱[活動 QA](/help/main/c-activities/c-activity-qa/activity-qa.md#preview).

使用體驗預覽URL來與團隊成員共用體驗，以及跨瀏覽器和環境執行QA體驗，而不需要建立個別的QA活動。 如果網站很複雜，或如果您的安全性原則不允許在模擬器中檢視網站，此功能特別有用。

1. 建立[自動個人化活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)或按一下活動以開啟。

   活動不需要上線即可預覽體驗。

1. 在活動概覽頁面上，按一下三個垂直點，然後按一下 **[!UICONTROL 檢視體驗URL]**.

1. 檢閱和/或指定您的 URL。

   * 如果您使用 [!UICONTROL 可視化體驗撰寫器] (VEC)，系統會自動輸入您為活動指定的預設URL，並為活動中的每個體驗產生連結。 您可以變更此 URL 和新增其他 URL (如需要)。
   * 如果您使用 [!UICONTROL 表單式體驗撰寫器]，則不會自動輸入預設URL。 如果您先前未建立體驗預覽URL，請按一下 **新增URL**. 您必須指定您要預覽的所有 URL 以及每個 URL 的名稱。

   您可以新增多個 URL，當您執行多頁測試或範本測試，且要在一個以上的頁面上預覽活動時相當實用。

   強制回應視窗會顯示您網站上的體驗連結，以取得外部體驗的「真正預覽」 [!DNL Target] VEC. 您必須分享來自訊息的連結以分享預覽。按一下連結，然後從頁面複製產生的 URL 將沒有作用，因為 URL 包含的參數只會在您透過訊息中的連結存取頁面時正確顯示頁面。請改為複製強制回應視窗中的文字，並透過電子郵件傳送給您的團隊。

1. 按一下&#x200B;**[!UICONTROL 「全部產生」]**，然後按一下每個體驗來預覽。

   如果您接著變更體驗，請確定傳回強制回應視窗並按一下，為您的團隊產生新的預覽連結 **續約連結** 來取得新連結。

   >[!NOTE]
   >
   >預覽連結在新索引標籤中開啟，並要求您瀏覽器上的快顯封鎖程式已停用。

1. 按一下每個體驗名稱以預覽活動。

   頁面隨即開啟並顯示活動。

1. 按一下&#x200B;**[!UICONTROL 「完成」]**&#x200B;以回到活動摘要。

## 考量事項 {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**產生體驗預覽URL**

* 體驗預覽URL不受體驗之間流量分割的影響。
* 對象層級的鎖定目標不會影響預覽。
* 針對每個活動，您可以自動產生最多 300 個體驗 URL。在那之後，您必須手動產生 URL。
* 根據體驗的數量，可能需要最多五分鐘才能產生 URL。請勿關閉對話方塊，否則產生的URL會遺失。
* 產生的預覽連結的有效期為兩個月。在此時間之後，您必須重新產生您的預覽 URL。
* 每當體驗變更時，您必須重新產生。

**共用體驗預覽URL**

* 即便您不屬於鎖定的對象，您也可以預覽體驗。
* 您可以與無權存取的同事共用體驗預覽URL [!DNL Adobe Target].

**使用體驗預覽URL檢視體驗**

* 只要頁面未變更，預覽皆能用於任何已儲存的活動。
* 無論活動是使用中或非使用中，體驗預覽URL都可供使用。
* 您無法預覽 [!UICONTROL 草稿] 狀態。
* 檢視體驗預覽URL不會影響報表。

**疑難排解體驗預覽URL**

* 如果您無法在新索引標籤中查看預覽 (由於瀏覽器快取)，請嘗試重新整理兩或三次，或是複製連結並在新的瀏覽器、新工作階段或是在私密瀏覽器模式中開啟它。

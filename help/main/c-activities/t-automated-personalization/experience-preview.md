---
keywords: 體驗預覽; 體驗 URL; 產生 URL; 檢視體驗 URL
description: 瞭解如何在Adobe [!DNL Target] Automated Personalization活動使用體驗預覽URL，在活動上線之前直接在網站上檢視體驗內容。
title: 如何在Automated Personalization活動中使用體驗預覽URL？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: 9f329b8a-5f86-4cae-a3be-eed24fa0a9cd
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 49%

---

# 使用體驗預覽 URL 預覽 Automated Personalization 活動

可以產生[!DNL Target] [!UICONTROL Automated Personalization]活動的體驗預覽URL，在活動上線進行預覽和QA之前，直接在您的網站上檢視體驗內容。 體驗預覽URL略過鎖定目標以強制檢視特定體驗。

>[!NOTE]
>
>您可以為其他型別的[!DNL Target]活動建立體驗預覽URL。 不過，程式稍有不同。 如需詳細資訊，請參閱[活動 QA](/help/main/c-activities/c-activity-qa/activity-qa.md#preview)。

使用體驗預覽URL可與團隊成員共用體驗，並跨瀏覽器和環境進行QA體驗，而不需建立個別的QA活動。 如果網站很複雜，或如果您的安全性原則不允許在模擬器中檢視網站，此功能特別有用。

1. 建立[自動個人化活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)或按一下活動以開啟。

   活動不需要上線即可預覽體驗。

1. 在活動概觀頁面上，按一下垂直三點圖示，然後按一下「**[!UICONTROL View Experience URLs]**」。

1. 檢閱和/或指定您的 URL。

   * 如果您使用[!UICONTROL Visual Experience Composer] (VEC)，則會自動輸入您為活動指定的預設URL，並為活動中的每個體驗產生連結。 您可以變更此 URL 和新增其他 URL (如需要)。
   * 如果您使用[!UICONTROL Form-Based Experience Composer]，則不會自動輸入預設URL。 如果您先前未建立體驗預覽URL，請按一下[新增URL] ****。 您必須指定您要預覽的所有 URL 以及每個 URL 的名稱。

   您可以新增多個 URL，當您執行多頁測試或範本測試，且要在一個以上的頁面上預覽活動時相當實用。

   強制回應視窗會顯示您網站上體驗的連結，以取得[!DNL Target] VEC外部體驗的「真實預覽」。 您必須分享來自訊息的連結以分享預覽。按一下連結，然後從頁面複製產生的 URL 將沒有作用，因為 URL 包含的參數只會在您透過訊息中的連結存取頁面時正確顯示頁面。請改為複製強制回應視窗中的文字，並透過電子郵件傳送給您的團隊。

1. 按一下&#x200B;**[!UICONTROL Generate All]**，然後按一下每個體驗來預覽。

   如果您接著變更體驗，請務必回到模組視窗並按一下&#x200B;**更新連結**&#x200B;以取得新連結，為您的團隊產生新的預覽連結。

   >[!NOTE]
   >
   >預覽在新標籤中開啟的連結，並需要停用瀏覽器上的快顯封鎖程式。

1. 按一下每個體驗名稱以預覽活動。

   頁面隨即開啟並顯示活動。

1. 按一下&#x200B;**[!UICONTROL Done]**&#x200B;以返回活動摘要。

## 考量事項 {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**正在產生體驗預覽URL**

* 體驗預覽URL不受體驗之間的流量劃分影響。
* 對象層級的鎖定目標不會影響預覽。
* 針對每個活動，您可以自動產生最多 300 個體驗 URL。在那之後，您必須手動產生 URL。
* 根據體驗的數量，可能需要最多五分鐘才能產生 URL。請勿關閉對話方塊，否則產生的URL會遺失。
* 產生的預覽連結的有效期為兩個月。在此時間之後，您必須重新產生您的預覽 URL。
* 每當體驗變更時，您必須重新產生。

**共用體驗預覽URL**

* 即便您不屬於鎖定的對象，您也可以預覽體驗。
* 您可以與沒有[!DNL Adobe Target]存取權的同事共用體驗預覽URL。

**使用體驗預覽URL檢視體驗**

* 只要頁面未變更，預覽皆能用於任何已儲存的活動。
* 無論活動是作用中或非作用中，都可以使用體驗預覽URL。
* 您無法預覽處於[!UICONTROL Draft]狀態的體驗。
* 檢視體驗預覽URL不會影響報表。

**疑難排解體驗預覽URL**

* 如果您無法在新索引標籤中查看預覽 (由於瀏覽器快取)，請嘗試重新整理兩或三次，或是複製連結並在新的瀏覽器、新工作階段或是在私密瀏覽器模式中開啟它。

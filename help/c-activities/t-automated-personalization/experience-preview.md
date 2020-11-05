---
keywords: experience preview;experience urls;generate urls;view experience urls
description: 體驗預覽URL可針對Target自動個人化活動產生，以便在活動上線以供預覽和QA之用前，直接在您的網站上查看體驗內容。 體驗預覽URL會略過定位，強制檢視特定體驗。
title: 使用體驗預覽URL預覽自動個人化活動
feature: ap
topic: Standard
uuid: 2ef07b6c-086d-43ac-bf02-efe217652a3a
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 64%

---


# ![PREMIUM](/help/assets/premium.png) Preview使用體驗預覽URL自動個人化活動{#share-experience-urls-to-preview-automated-personalization-outside-of-target}

體驗預覽URL可針對Target自動個人化活動產生，以便在活動上線以供預覽和QA之用前，直接在您的網站上查看體驗內容。 體驗預覽URL會略過定位，強制檢視特定體驗。

>[!NOTE]
>
>「自動個人化」的體驗預覽URL與「活動QA」模式不同。 活動 QA 模式可讓您為其他類型的活動建立活動 URL。如需詳細資訊，請參閱[活動 QA](/help/c-activities/c-activity-qa/activity-qa.md)。
>
>AP活動的體驗預覽URL僅在使用at.js 1.x時可用。at.js 2.x目前不支援AP活動的體驗預覽URL。

使用體驗預覽URL與團隊成員分享體驗，並跨瀏覽器和環境分享QA體驗，毋需建立個別的QA活動。 如果網站很複雜，或如果您的安全性原則不允許在模擬器中檢視網站，此功能特別有用。

1. 建立[自動個人化活動](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)或按一下活動以開啟。

   活動不需要上線即可預覽體驗。
1. 在活動摘要頁面上，按一下垂直三點圖示，然後按一下 **[!UICONTROL 「檢視體驗 URL」]**。
1. 檢閱和/或指定您的 URL。

   * 如果您使用可視化體驗撰寫器，則會自動輸入您為活動指定的預設的 URL，並且為您的活動中的每個體驗產生連結。您可以變更此 URL 和新增其他 URL (如需要)。
   * 如果您使用表單式體驗撰寫器，則不會自動輸入預設的 URL。If you haven&#39;t previously created experience preview URLs, click **Add New URL**. 您必須指定您要預覽的所有 URL 以及每個 URL 的名稱。

   您可以新增多個 URL，當您執行多頁測試或範本測試，且要在一個以上的頁面上預覽活動時相當實用。

   互動視窗會顯示您的網站上體驗的連結，以獲得在 Target 的可視化體驗撰寫器外部的體驗「真正預覽」。您必須分享來自訊息的連結以分享預覽。按一下連結，然後從頁面複製產生的 URL 將沒有作用，因為 URL 包含的參數只會在您透過訊息中的連結存取頁面時正確顯示頁面。請改為複製強制回應視窗中的文字，並透過電子郵件傳送給您的團隊。
1. 按一下&#x200B;**[!UICONTROL 「全部產生」]**，然後按一下每個體驗來預覽。

   If you then make changes to the experience, make sure to generate new preview links for your team by returning to the modal window and clicking **Renew Links** to get new links.

   **注意:** 預覽連結會在新標籤中開啟，並且需要停用您的瀏覽器中的快顯封鎖程式。

1. 按一下每個體驗名稱以預覽活動。

   頁面隨即開啟並顯示活動。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**&#x200B;以回到活動摘要。

## 考量事項 {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**產生體驗預覽URL**

* 體驗預覽URL不受體驗之間流量劃分的影響。
* 對象層級的鎖定目標不會影響預覽。
* 針對每個活動，您可以自動產生最多 300 個體驗 URL。在那之後，您必須手動產生 URL。
* 針對每個活動，您可以自動產生最多 300 個體驗 URL。在那之後，您必須手動產生 URL。
* 根據體驗的數量，可能需要最多五分鐘才能產生 URL。請勿關閉對話方塊，否則將會失去產生的 URL。
* 產生的預覽連結的有效期為兩個月。在此時間之後，您必須重新產生您的預覽 URL。
* 每當體驗變更時，您必須重新產生。

**共用體驗預覽URL**

* 即便您不屬於鎖定的對象，您也可以預覽體驗。
* 您可以與無法存取Adobe Target的同事共用體驗預覽URL。

**使用體驗預覽URL檢視體驗**

* 只要頁面未變更，預覽皆能用於任何已儲存的活動。
* 無論活動是活動中或非活動中，體驗預覽URL都可用。
* 您無法預覽處於「草稿」狀態的體驗。
* 檢視體驗預覽URL不會影響報告。

**疑難排解體驗預覽URL**

* 如果您無法在新索引標籤中查看預覽 (由於瀏覽器快取)，請嘗試重新整理兩或三次，或是複製連結並在新的瀏覽器、新工作階段或是在私密瀏覽器模式中開啟它。

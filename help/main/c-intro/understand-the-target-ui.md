---
keywords: target使用者介面；使用者介面；ui；公告；事件；通知
description: 熟悉使用者介面並尋找更深入資訊的連結，以協助您充分利用 [!DNL Target]。
title: 如何使用 [!DNL Target] UI？
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 6bef27637c06f39ffc0e755f19e8a0870ec749e5
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 31%

---

# 了解 [!DNL Target] UI

使用者介面以邏輯且方便使用的格式排列，以協助您充分運用 [!DNL Adobe Target]。以下簡短概述可協助您熟悉[!DNL Target]，並提供連結，以取得更深入的資訊和逐步指示。

[!DNL Target] UI頂端的標題包含一些頁簽和選項，可協助您導覽解決方案的不同功能。 您也可以切換組織和[!DNL Adobe Experience Cloud]解決方案、取得說明和通知、管理您的[!DNL Adobe]設定檔，以及登出[!DNL Target]。

![Target 標題](/help/main/c-intro/assets/target-header.png)

左側的標籤可讓您存取[!DNL Target]的各種功能，稍後將討論這些功能。 首先，我們先討論右側的選項，然後再跳至標籤。

## 組織

*組織*&#x200B;是可讓管理員設定用戶、群組，以及控制 [!DNL Adobe Experience Cloud] 中單一登入存取的實體。組織的作用就像一個登入公司，涵蓋所有的 [!DNL Experience Cloud] 產品和解決方案。最常見的組織就是您的公司名稱。不過，公司可以有許多組織。

如果您的公司有多個組織，請從[!UICONTROL Organization]下拉式清單中選取所需的組織：

![組織下拉式清單](/help/main/c-intro/assets/organizations.png)

## 應用程式

應用程式切換器可讓您快速存取您可存取的 [!DNL Adobe Experience Cloud] 解決方案。

![應用程式切換器](/help/main/c-intro/assets/apps.png)

## 說明

「說明」圖示可讓您存取資訊、影片、部落格等，以協助您更有效率地使用 [!DNL Target]。您可以建立支援票證、尋找支援電話號碼、透過Twitter提出問題，或提供有關[!DNL Target]的意見回饋，讓我們瞭解[!DNL Target]團隊的表現。

![說明](/help/main/c-intro/assets/help.png)

## 通知和公告 {#notifications-announcements}

[!UICONTROL Notifications]和[!UICONTROL Announcements]面板可協助您隨時掌握[!DNL Adobe Target]的所有最新資訊。 主動通知可協助您隨時掌握[!DNL Adobe Experience Cloud]解決方案和[!DNL Target]事件的狀態。 主動公告會提醒您發生中斷事件和維護事件。

按一下標題的鈴鐺圖示可檢視通知：

通知和公告的![鈴鐺圖示](assets/bell-icon.png)

面板包含[!UICONTROL Notifications]和[!UICONTROL Announcements]的索引標籤。

![通知](assets/notifications.png)

以下區段包含每個標籤的相關資訊，以及如何設定通知和公告：

### 通知 {#notifications}

[!DNL Target]個事件通知包含下列專案：

* **活動**：當活動被批准或停用時（手動或達到其開始或結束日期時），所有活動類型的通知。 通知包含具有活動概述頁面連結的活動名稱。

  通知是可設定的，並且預設會由產品管理員、發佈者和核准者在活動工作區中接收[!DNL Target Premium]帳戶。 針對[!DNL Target Standard]帳戶，所有發行者和核准者都會收到通知。

  通知的格式如下所示：

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **設定檔指令碼**：手動或由[!DNL Target]啟動或停用設定檔指令碼時通知。

  通知是可設定的，而且預設會由[!DNL Target Premium]和[!DNL Target Standard]帳戶的產品管理員和核准者接收。

  通知的格式如下所示：

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Recommendations摘要**：手動或由[!DNL Target]啟動或停用[!DNL Recommendations]摘要時通知。 當[!DNL Recommendations]摘要失敗時也會傳送通知。

  通知是可設定的，而且預設會由[!DNL Target Premium]帳戶的產品管理員和核准者接收。 [!DNL Recommendations]是[!DNL Target Premium]功能，無法在[!DNL Target Standard]中使用。

  通知的格式如下所示：

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed`
   * `Feed {target.feed.name} has failed to import from source`

您可以將個別通知標示為已讀取，方法是暫留在所需的通知上，然後按一下核取記號。 您可以按一下面板底部的[!UICONTROL "Mark as Read"]或[!UICONTROL "View All"]，將所有通知標籤為已讀取或檢視所有通知。

您也可以將滑鼠游標停留在通知上，按一下&quot;[!UICONTROL Remind me]&quot;圖示，然後選取您想要收到通知的時間：5分鐘、15分鐘、1小時或明天，藉此設定要再次收到通知的提醒。

### 公告

主動公告會提醒您發生中斷事件和維護事件。

如需深入資訊，請參閱[Adobe狀態](https://status.adobe.com/)頁面。

### 設定通知和公告

若要編輯您的通知偏好設定：

1. 按一下齒輪圖示，然後按一下&#x200B;**[!UICONTROL Notifications]**。
1. 在&#x200B;**[!UICONTROL Target]**&#x200B;底下，按一下&#x200B;**[!UICONTROL Customize]**。
1. 選取或取消選取您要接收通知的類別：

   * 請求：有人傳送請求，要您核准物件或授予物件存取權時。 您無法取消訂閱此類別。
   * 指派給我：有人將物件指派給您時。
   * 提及次數：有人在評論中提及您時。
   * 新版本：您可存取的產品或服務有新版本可用時。
   * 與我共用：有人與您共用物件時。
   * 內容更新：有人編輯、刪除或評論您建立或關注的物件時。
   * 其他：

   >[!NOTE]
   >
   >「新版本」和「內容更新」是僅適用於[!DNL Target]的通知類別。 其他類別適用於其他Adobe解決方案。


1. 選取您要視為高優先順序的類別。
1. 選取您希望警報在瀏覽器中顯示的通知。

   這些警報會出現在瀏覽器的右上角幾秒鐘。 您可以選擇檢視高優先順序類別、所有類別，或隱藏所有通知快顯視窗。 您也可以設定是否希望通知保持可見，直到關閉為止，或者您可以設定通知持續時間。

1. 選取您想要接收通知電子郵件的頻率：

   * 不要傳送電子郵件
   * 即時通知
   * 每日摘要
   * 每週摘要

## 設定檔

按一下您的設定檔頭像以編輯您的 [!DNL Adobe Experience Cloud] 偏好設定或登出 [!DNL Target]。您也可以存取或編輯您的 [!DNL Adobe] 設定檔。

![設定檔頭像](/help/main/c-intro/assets/change-language.png)

現在，讓我們討論 [!DNL Target] 標題左側的標籤。

## 活動

**[!UICONTROL Activities]**&#x200B;清單是您開啟[!DNL Target]時的預設檢視。 您可以從此頁面建立活動，並管理現有活動。

![活動清單](/help/main/c-intro/assets/activities-list.png)

如需[!DNL Target]中可用活動型別的深入資訊，請參閱[活動](/help/main/c-activities/activities.md)，並進一步瞭解[!UICONTROL Activity]清單的使用者介面。

## 客群

按一下「**[!UICONTROL Audiences]**」標籤以顯示[!UICONTROL Audiences]清單，您可在其中建立對象並管理現有對象。

![客群清單](/help/main/c-intro/assets/audience-list.png)

對象是看到鎖定活動的一組類似的活動加入者。 客群是具有相同特性的一組人員，例如新訪客、回頭客或來自中西部的回頭客。[!UICONTROL Audience]功能可讓您將不同的內容和體驗鎖定在特定對象，利用在正確時間向正確的人員顯示正確的訊息來最佳化您的數位行銷。 如果驗明訪客屬於目標客群，[!DNL Target] 會根據活動建立期間所定義的條件，決定要顯示的體驗。

如需[!DNL Target]中對象型別的深入資訊，請參閱[建立對象](/help/main/c-target/c-audiences/create-audience.md)，並進一步瞭解[!UICONTROL Audience]清單的使用者介面。

## 選件

按一下「**[!UICONTROL Offers]**」標籤以顯示[!UICONTROL Offers]清單，您可在其中建立體驗和選件，並管理現有的體驗和選件。

![選件清單](/help/main/c-intro/assets/offers.png)

體驗可以是選件、影像、文字、按鈕、影片或將這些不同元素加以組合，放在頁面、整個網頁或一組頁面上，可能會形成購買漏斗或一些其他的頁面邏輯順序。也可以是語音助理的回應、客戶服務指令碼，或甚至是飲料機的個人化口味。您可以在 [!DNL Target] 活動中測試或個人化體驗。

如需[!DNL Target]中選件型別的深入資訊，請參閱[選件](/help/main/c-experiences/c-manage-content/manage-content.md)，並進一步瞭解[!UICONTROL Offer]清單的使用者介面。

## 建議

按一下&#x200B;**[!UICONTROL Recommendations]**&#x200B;索引標籤以存取[!DNL Target Recommendations]。

>[!NOTE]
>
>Recommendations 活動是 [!DNL Target Premium] 解決方案內建的功能。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。如需更多資訊，請參閱 *Target 簡介*&#x200B;中的 [Target Premium](/help/main/c-intro/intro.md#premium)。

![Recommendations](/help/main/c-intro/assets/recommendations.png)

[!UICONTROL Recommendations]活動可依據先前的使用者活動或其他演演算法，自動顯示可能使客戶感興趣的產品或內容。 Recommendations 有助於將客戶引導至他們可能尚不知道的相關項目。

如需[!DNL Target]中[!UICONTROL Recommendations]的深入資訊，請參閱[Recommendations](/help/main/c-recommendations/recommendations.md)，並進一步瞭解[!UICONTROL Recommendations]使用者介面。

## 管理

按一下&#x200B;**[!UICONTROL Administration]**&#x200B;索引標籤以存取[!UICONTROL Administration]頁面。

![管理頁面](/help/main/c-intro/assets/administration.png)

[!UICONTROL Administration]頁面可讓您管理[!DNL Target]，包括[!UICONTROL Visual Experience Composer] (VEC)、報告、[!DNL Scene7]組態、實作、主機、環境、回應權杖和使用者的組態設定。

如需深入資訊，請參閱[管理 Target 總覽](/help/main/administrating-target/administrating-target.md)，並進一步瞭解使用者介面。

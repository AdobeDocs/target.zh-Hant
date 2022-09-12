---
keywords: 目標使用者界面;使用者界面;ui；公告；事件；通知
description: 熟悉使用者界面，找到更多深入資訊的連結以協助充分運用 [!DNL Target].
title: 如何使用 [!DNL Target] UI？
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 6bef27637c06f39ffc0e755f19e8a0870ec749e5
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 48%

---

# 了解 [!DNL Target] UI

使用者介面以邏輯且方便使用的格式排列，以協助您充分運用 [!DNL Adobe Target]。以下簡要概述可協助您熟悉 [!DNL Target] 提供連結，以取得更深入的資訊和逐步指示。

頂端的標題 [!DNL Target] UI包含標籤和選項，可協助您導覽解決方案的不同功能。 您也可以切換組織和 [!DNL Adobe Experience Cloud] 解決方案，獲取幫助和通知，管理 [!DNL Adobe] 設定檔，並登出 [!DNL Target].

![Target 標題](/help/main/c-intro/assets/target-header.png)

左側的標籤可讓您存取 [!DNL Target]，稍後將討論。 首先，我們先討論右側的選項，然後再跳至標籤。

## 組織

*組織*&#x200B;是可讓管理員設定用戶、群組，以及控制 [!DNL Adobe Experience Cloud] 中單一登入存取的實體。組織的作用就像一個登入公司，涵蓋所有的 [!DNL Experience Cloud] 產品和解決方案。最常見的組織就是您的公司名稱。不過，公司可以有許多組織。

如果您的公司有多個組織，請從[!UICONTROL 組織]下拉式清單中選擇所需的組織：

![組織下拉式清單](/help/main/c-intro/assets/organizations.png)

## 應用程式

應用程式切換器可讓您快速存取您可存取的 [!DNL Adobe Experience Cloud] 解決方案。

![應用程式切換器](/help/main/c-intro/assets/apps.png)

## 說明

「說明」圖示可讓您存取資訊、影片、部落格等，以協助您更有效率地使用 [!DNL Target]。您可以建立支援票證、尋找支援電話號碼、透過Twitter提出問題，或提供相關意見 [!DNL Target] 讓我們知道 [!DNL Target] 團隊在做。

![說明](/help/main/c-intro/assets/help.png)

## 通知和公告 {#notifications-announcements}

[!UICONTROL 通知]和[!UICONTROL 公告]面板可協助您隨時掌握所有 [!DNL Adobe Target] 相關資訊。主動通知有助於您及時了解 [!DNL Adobe Experience Cloud] 解決方案和 [!DNL Target] 事件。 主動公告會提醒您發生中斷事件和維護事件。

按一下標題中的鈴聲圖示以檢視通知：

![通知和公告的鈴聲表徵圖](assets/bell-icon.png)

面板包含 [!UICONTROL 通知] 和 [!UICONTROL 公告].

![通知](assets/notifications.png)

以下小節包含每個標籤的相關資訊，以及如何設定通知和公告：

### 通知 {#notifications}

[!DNL Target] 事件通知包含下列項目：

* **活動**：當活動被批准或停用時（手動或達到其開始或結束日期時），所有活動類型的通知。 通知包含具有活動概覽頁面連結的活動名稱。

   通知是可設定的，預設情況下，由活動工作區中的產品管理員、發佈者和核准者接收 [!DNL Target Premium] 帳戶。 針對 [!DNL Target Standard] 帳戶、通知由所有發佈者和批准者接收。

   通知的格式如下：

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **設定檔指令碼**:手動或停用設定檔指令碼時的通知 [!DNL Target].

   可配置通知，預設情況下，由產品管理員和兩者的批准者接收通知 [!DNL Target Premium] 和 [!DNL Target Standard] 帳戶。

   通知的格式如下：

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Recommendations摘要**:通知 [!DNL Recommendations] 手動或停用摘要 [!DNL Target]. 當 [!DNL Recommendations] 摘要失敗。

   通知可配置，預設情況下，由產品管理員和批准者接收 [!DNL Target Premium] 帳戶。 [!DNL Recommendations] 是 [!DNL Target Premium] 功能，且在 [!DNL Target Standard].

   通知的格式如下：

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed`
   * `Feed {target.feed.name} has failed to import from source`

您可以將游標移至所需的通知上，然後按一下核取標籤，將個別通知標示為已讀取。 您可以將所有通知標示為已讀取，或按一下 [!UICONTROL &quot;標籤為已讀&quot;] 或 [!UICONTROL &quot;查看全部&quot;] 在面板底部。

您也可以將游標暫留在通知上，按一下「[!UICONTROL 提醒我]」表徵圖，然後選擇要通知的時間：5分鐘、15分鐘、1小時或明天。

### 公告

主動公告會提醒您發生中斷事件和維護事件。

如需深入資訊，請參閱 [Adobe 狀態](https://status.adobe.com/)頁面。

### 設定通知和公告

要編輯通知首選項，請執行以下操作：

1. 按一下齒輪圖示，然後按一下 **[!UICONTROL 通知]**.
1. 在 **[!UICONTROL 目標]**，按一下 **[!UICONTROL 自訂]**.
1. 選擇或取消選擇要接收通知的類別：

   * 請求：當有人向您發送批准對象或授予對象訪問權限的請求時。 不能取消訂閱此類別。
   * 指派給我：當有人指派物件給您時。
   * 提及次數：有人在留言中提及你時。
   * 新版本：當您有權存取的產品或服務有新版本時。
   * 與我共用：當有人與你共用物件時。
   * 內容更新：當某人編輯、刪除或註解您建立或追蹤的物件時。
   * 其他:

   >[!NOTE]
   >
   >「新版本」和「內容更新」是唯一適用於 [!DNL Target]. 其他類別則套用至其他Adobe解決方案。


1. 選取您要視為高優先順序的類別。
1. 選取您要在瀏覽器中顯示警報的通知。

   這些警報會在您瀏覽器的右上角出現幾秒鐘。 您可以選擇查看高優先順序類別、所有類別，或隱藏所有通知快顯視窗。 您也可以設定是否希望在關閉通知之前仍可顯示通知，或設定通知持續時間。

1. 選取您要接收通知電子郵件的頻率：

   * 請勿傳送電子郵件
   * 即時通知
   * 每日摘要
   * 每週摘要

## 設定檔

按一下您的設定檔頭像以編輯您的 [!DNL Adobe Experience Cloud] 偏好設定或登出 [!DNL Target]。您也可以存取或編輯您的 [!DNL Adobe] 設定檔。

![設定檔頭像](/help/main/c-intro/assets/change-language.png)

現在，讓我們討論 [!DNL Target] 標題左側的標籤。

## 活動

**[!UICONTROL 活動]**&#x200B;清單是您開啟 [!DNL Target] 時的預設檢視。您可以從此頁面建立活動，並管理現有活動。

![活動清單](/help/main/c-intro/assets/activities-list.png)

如需 [!DNL Target] 中可用活動類型的深入資訊，請參閱[活動](/help/main/c-activities/activities.md)，並進一步瞭解[!UICONTROL 活動]清單的使用者介面。

## 對象

按一下 **[!UICONTROL 對象]** 標籤來顯示 [!UICONTROL 對象] 清單中，您可以在此建立對象及管理現有對象。

![對象清單](/help/main/c-intro/assets/audience-list.png)

對象是一組看到鎖定活動的類似活動加入者。 對象是具有相同特性的一組人員，例如新訪客、回訪訪客或來自中西部的回訪訪客。[!UICONTROL 對象]功能可讓您將不同的內容和體驗鎖定在特定對象，利用在正確時間向正確的人員顯示正確的訊息來最佳化您的數位行銷。如果驗明訪客屬於目標對象，[!DNL Target] 會根據活動建立期間所定義的條件，決定要顯示的體驗。

請參閱[建立對象](/help/main/c-target/c-audiences/create-audience.md)以取得 [!DNL Target] 中對象類型的深入資訊，並進一步瞭解[!UICONTROL 對象]清單的使用者介面。

## 選件

按一下 **[!UICONTROL 選件]** 標籤來顯示 [!UICONTROL 選件] 列出您可以在其中建立體驗和選件，以及管理現有體驗和選件。

![選件清單](/help/main/c-intro/assets/offers.png)

體驗可以是選件、影像、文字、按鈕、影片或將這些不同元素加以組合，放在頁面、整個網頁或一組頁面上，可能會形成購買漏斗或一些其他的頁面邏輯順序。也可以是語音助理的回應、客戶服務指令碼，或甚至是飲料機的個人化口味。您可以在 [!DNL Target] 活動中測試或個人化體驗。

如需 [!DNL Target] 中選件類型的深入資訊，請參閱[選件](/help/main/c-experiences/c-manage-content/manage-content.md)，並進一步瞭解[!UICONTROL 選件]清單的使用者介面。

## Recommendations

按一下&#x200B; **[!UICONTROL Recommendations]**&#x200B; 標籤以存取 [!DNL Target Recommendations]。

>[!NOTE]
>
>Recommendations 活動是 [!DNL Target Premium] 解決方案內建的功能。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。如需更多資訊，請參閱 *Target 簡介*&#x200B;中的 [Target Premium](/help/main/c-intro/intro.md#premium)。

![Recommendations](/help/main/c-intro/assets/recommendations.png)

[!UICONTROL Recommendations] 活動可依據先前的使用者行為或其他演算法，自動顯示可能使客戶感興趣的產品或內容。Recommendations 有助於將客戶引導至他們可能尚不知道的相關項目。

有關 [!DNL Target] 中 [!UICONTROL Recommendations] 的深入資訊，請參閱 [Recommendations](/help/main/c-recommendations/recommendations.md)，並進一步瞭解 [!UICONTROL Recommendations]用戶介面。

## 管理

按一下&#x200B;**[!UICONTROL 管理&#x200B;]**&#x200B;標籤以存取[!UICONTROL 管理]頁面。

![管理頁面](/help/main/c-intro/assets/administration.png)

[!UICONTROL 管理]頁面可讓您管理 [!DNL Target]，包括 [!UICONTROL Visual Experience Composer] (VEC)、報告、[!DNL Scene7] 設定、實施、主機、環境、回應權杖和使用者的設定。

如需深入資訊，請參閱[管理 Target 總覽](/help/main/administrating-target/administrating-target.md)，並進一步瞭解使用者介面。

---
keywords: 目標使用者界面;使用者界面;ui；公告；事件；通知
description: 熟悉使用者界面，找到更多深入資訊的連結以協助充分運用 [!DNL Target].
title: 如何使用 [!DNL Target] UI？
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: be0f2289afd0c808b3ab4cb390bd28bedd8a315d
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 46%

---

# 了解 [!DNL Target] UI

使用者介面以邏輯且方便使用的格式排列，以協助您充分運用 [!DNL Adobe Target]。以下簡要概述可幫助您熟悉 [!DNL Target] 並提供連結，以獲取更深入的資訊和逐步說明。

位於 [!DNL Target] UI包含頁籤和選項，可幫助您導航解決方案的不同功能。 您還可以切換組織和 [!DNL Adobe Experience Cloud] 解決方案，獲取幫助和通知，管理 [!DNL Adobe] 配置檔案，並註銷 [!DNL Target]。

![Target 標題](/help/main/c-intro/assets/target-header.png)

左側的頁籤允許您訪問 [!DNL Target]，稍後將討論。 首先，我們先討論右側的選項，然後再跳至標籤。

## 組織

*組織*&#x200B;是可讓管理員設定用戶、群組，以及控制 [!DNL Adobe Experience Cloud] 中單一登入存取的實體。組織的作用就像一個登入公司，涵蓋所有的 [!DNL Experience Cloud] 產品和解決方案。最常見的組織就是您的公司名稱。不過，公司可以有許多組織。

如果您的公司有多個組織，請從[!UICONTROL 組織]下拉式清單中選擇所需的組織：

![組織下拉式清單](/help/main/c-intro/assets/organizations.png)

## 應用程式

應用程式切換器可讓您快速存取您可存取的 [!DNL Adobe Experience Cloud] 解決方案。

![應用程式切換器](/help/main/c-intro/assets/apps.png)

## 說明

「說明」圖示可讓您存取資訊、影片、部落格等，以協助您更有效率地使用 [!DNL Target]。您可以建立支援票證、查找支援電話號碼、通過Twitter提出問題或提供有關 [!DNL Target] 讓我們知道 [!DNL Target] 團隊在做。

![說明](/help/main/c-intro/assets/help.png)

## 通知和公告 {#notifications-announcements}

[!UICONTROL 通知]和[!UICONTROL 公告]面板可協助您隨時掌握所有 [!DNL Adobe Target] 相關資訊。主動通知有助於您及時瞭解 [!DNL Adobe Experience Cloud] 解決方案和 [!DNL Target] 事件。 主動公告會提醒您發生中斷事件和維護事件。

按一下標題中的鈴表徵圖以查看通知：

![通知和通知的鈴表徵圖](assets/bell-icon.png)

該面板包含的頁籤 [!UICONTROL 通知] 和 [!UICONTROL 公告]。

![通知](assets/notifications.png)

以下各節包含有關每個頁籤的資訊以及如何配置通知和公告：

### 通知

[!DNL Target] 事件通知包括以下內容：

* **活動**:當活動被批准或停用時（手動或達到其開始或結束日期時），所有活動類型的通知。 通知包括活動的名稱，其中包含指向活動概述頁的連結。

   通知是可配置的，預設情況下，通知由活動工作區中的產品管理員、發佈者和批准者接收 [!DNL Target Premium] 帳戶。 對於 [!DNL Target Standard] 所有發佈者和批准者都會收到通知。

   通知的格式與以下示例類似：

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **配置檔案指令碼**:手動或由激活或停用配置檔案指令碼時的通知 [!DNL Target]。

   通知是可配置的，預設情況下，由產品管理員和批准者為兩者接收 [!DNL Target Premium] 和 [!DNL Target Standard] 帳戶。

   通知的格式與以下示例類似：

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Recommendations飼料**:通知 [!DNL Recommendations] 源已激活或停用，可手動或通過 [!DNL Target]。 在 [!DNL Recommendations] 饋送失敗。

   通知是可配置的，預設情況下，由產品管理員和批准者接收 [!DNL Target Premium] 帳戶。 [!DNL Recommendations] 是 [!DNL Target Premium] 功能，在中不可用 [!DNL Target Standard]。

   通知的格式與以下示例類似：

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed to import from source`

通過將滑鼠懸停在所需通知上，然後按一下複選標籤，可以將單個通知標籤為已讀。 您可以將所有通知標籤為已讀或通過按一下查看所有通知 [!UICONTROL &quot;標籤為已讀&quot;] 或 [!UICONTROL &quot;查看全部&quot;] 的下界。

您還可以通過懸停在通知上，按一下「 」，將提醒設定為再次通知。[!UICONTROL 提醒我]表徵圖，然後選擇要通知的時間：5分鐘，15分鐘，1小時，或明天。

### 公告

主動公告會提醒您發生中斷事件和維護事件。

如需深入資訊，請參閱 [Adobe 狀態](https://status.adobe.com/)頁面。

### 配置通知和公告

要編輯通知首選項，請執行以下操作：

1. 按一下齒輪表徵圖，然後按一下 **[!UICONTROL 通知]**。
1. 下 **[!UICONTROL 目標]**&#x200B;按一下 **[!UICONTROL 自定義]**。
1. 選擇或取消選擇要接收通知的類別：

   * 請求：當有人向您發送批准對象或授予對對象訪問權限的請求時。 不能取消訂閱此類別。
   * 分配給我：當有人給你分配對象時。
   * 提及：當有人在評論中提到你時。
   * 新版本：當您有權訪問的產品或服務有新版本時。
   * 與我共用：當有人和你分享物品時。
   * 內容更新：當有人對您建立或跟蹤的對象進行編輯、刪除或注釋時。
   * 其他:

   >[!NOTE]
   >
   >「新版本」和「內容更新」是唯一適用於 [!DNL Target]。 其他類別適用於其他Adobe解決方案。


1. 選擇要被視為高優先順序的類別。
1. 選擇要在瀏覽器中顯示警報的通知。

   這些警報會在瀏覽器的右上角出現幾秒鐘。 您可以選擇查看高優先順序類別、所有類別或隱藏所有通知彈出窗口。 您還可以配置，如果希望通知在您關閉之前保持可見狀態，或者您可以配置通知持續時間。

1. 選擇要接收通知電子郵件的頻率：

   * 不發送電子郵件
   * 即時通知
   * 每日摘要
   * 每週摘要

## 設定檔

按一下您的設定檔頭像以編輯您的 [!DNL Adobe Experience Cloud] 偏好設定或登出 [!DNL Target]。您也可以存取或編輯您的 [!DNL Adobe] 設定檔。

![設定檔頭像](/help/main/c-intro/assets/change-language.png)

現在，讓我們討論 [!DNL Target] 標題左側的標籤。

## 活動

**[!UICONTROL 活動]**&#x200B;清單是您開啟 [!DNL Target] 時的預設檢視。您可以從此頁建立活動並管理現有活動。

![活動清單](/help/main/c-intro/assets/activities-list.png)

如需 [!DNL Target] 中可用活動類型的深入資訊，請參閱[活動](/help/main/c-activities/activities.md)，並進一步瞭解[!UICONTROL 活動]清單的使用者介面。

## 對象

按一下 **[!UICONTROL 觀眾]** 頁籤 [!UICONTROL 觀眾] 列出您可以在其中建立受眾和管理現有受眾。

![對象清單](/help/main/c-intro/assets/audience-list.png)

受眾是一組類似活動的進入者，他們看到了目標活動。 對象是具有相同特性的一組人員，例如新訪客、回訪訪客或來自中西部的回訪訪客。[!UICONTROL 對象]功能可讓您將不同的內容和體驗鎖定在特定對象，利用在正確時間向正確的人員顯示正確的訊息來最佳化您的數位行銷。如果驗明訪客屬於目標對象，[!DNL Target] 會根據活動建立期間所定義的條件，決定要顯示的體驗。

請參閱[建立對象](/help/main/c-target/c-audiences/create-audience.md)以取得 [!DNL Target] 中對象類型的深入資訊，並進一步瞭解[!UICONTROL 對象]清單的使用者介面。

## 選件

按一下 **[!UICONTROL 優惠]** 頁籤 [!UICONTROL 優惠] 列出您可以建立體驗和優惠以及管理現有體驗和優惠。

![選件清單](/help/main/c-intro/assets/offers.png)

體驗可以是選件、影像、文字、按鈕、影片或將這些不同元素加以組合，放在頁面、整個網頁或一組頁面上，可能會形成購買漏斗或一些其他的頁面邏輯順序。也可以是語音助理的回應、客戶服務指令碼，或甚至是飲料機的個人化口味。您可以在 [!DNL Target] 活動中測試或個人化體驗。

如需 [!DNL Target] 中選件類型的深入資訊，請參閱[選件](/help/main/c-experiences/c-manage-content/manage-content.md)，並進一步瞭解[!UICONTROL 選件]清單的使用者介面。

## Recommendations

按一下&#x200B; **[!UICONTROL Recommendations]**&#x200B; 標籤以存取 [!DNL Target Recommendations]。

>[!NOTE]
>
>Recommendations 活動是 [!DNL Target Premium] 解決方案內建的功能。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。如需更多資訊，請參閱 *Target 簡介*&#x200B;中的 [Target Premium](/help/main/c-intro/intro.md#premium)。

![Recommendations](/help/main/c-intro/assets/recommendations.png)

[!UICONTROL Recommendations] 活動可依據先前的使用者行為或其他演算法，自動顯示可能使客戶感興趣的產品或內容。Recommendations幫助引導客戶訪問他們可能不知道的相關項目。

有關 [!DNL Target] 中 [!UICONTROL Recommendations] 的深入資訊，請參閱 [Recommendations](/help/main/c-recommendations/recommendations.md)，並進一步瞭解 [!UICONTROL Recommendations]用戶介面。

## 管理

按一下&#x200B;**[!UICONTROL 管理&#x200B;]**&#x200B;標籤以存取[!UICONTROL 管理]頁面。

![管理頁面](/help/main/c-intro/assets/administration.png)

[!UICONTROL 管理]頁面可讓您管理 [!DNL Target]，包括 [!UICONTROL Visual Experience Composer] (VEC)、報告、[!DNL Scene7] 設定、實施、主機、環境、回應權杖和使用者的設定。

如需深入資訊，請參閱[管理 Target 總覽](/help/main/administrating-target/administrating-target.md)，並進一步瞭解使用者介面。

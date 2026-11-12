---
keywords: scene7;dynamic media classic;數位資產管理;資產;dam;內容庫;交換影像
description: 將Adobe Target連線至Adobe Dynamic Media Classic (Scene7)，讓作者能在活動中使用來自Experience Cloud資產的影像選件和交換影像。
landing-page-description: 在「管理」中設定Scene7設定，以啟用VEC和表單式體驗撰寫器中的影像選件、內容庫DAM工作流程以及交換影像動作。
short-description: 在「管理」中設定Scene7設定，以啟用VEC和表單式體驗撰寫器中的影像選件、內容庫DAM工作流程以及交換影像動作。
title: 如何設定 Dynamic Media Classic (Scene7) 整合？
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
TQID: 'https://experienceleague.adobe.com/LKbjwlGIxrgaU-2i6Ddn1wi-VjsSmpQPAxYkFHRNOYQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: da3860b0-d637-47df-bef0-273751180266
    internal-label: Digital asset management
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 5%
---
# 設定Dynamic Media Classic (Scene7)

使用&#x200B;**[!UICONTROL 管理]**&#x200B;下的&#x200B;**[!UICONTROL Scene7設定]**&#x200B;索引標籤將[!DNL Adobe Target]連線到[!DNL Adobe Dynamic Media Classic] （以前稱為[!DNL Scene7]）。 整合將數位資產管理(DAM)帶入[!UICONTROL 內容庫]，並在活動中啟用影像交換工作流程。

如需此索引標籤如何與其他管理任務配合，請參閱[如何管理Target？](/help/main/administrating-target/administrating-target.md)。 若要在介面中尋找&#x200B;**[!UICONTROL 管理]**，請參閱[瞭解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)。

**概述**

1. [整合可啟用哪些功能](#what-it-enables)：影像選件、交換影像和合格的資產。
1. [帳戶和認證](#account-and-credentials)：現有[!DNL Dynamic Media]帳戶和支援的帳戶型別。
1. [使用准則](#usage-guidelines)： URL、傳遞及不支援的內容。
1. [在Target中設定Scene7](#configure-scene7)：登入和區域設定。

{{permissions-update}}

## 整合可讓哪些方面受益 {#what-it-enables}

設定&#x200B;**[!UICONTROL Scene7設定]**&#x200B;時，作者可以使用上傳至[!DNL Target]活動中[!DNL Adobe Experience Cloud]資產資料夾的影像。 **[!UICONTROL 交換影像選件]**&#x200B;選項出現在活動工作流程中，包括在[視覺化體驗撰寫器和表單式體驗撰寫器](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中。 如需VEC中的交換行為，請參閱[視覺化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

如果未設定此設定，則在活動建立期間無法使用&#x200B;**[!UICONTROL 交換影像選件]**。

整合提供的資產屬於Experience Cloud資產資料夾活動的一部分。 它&#x200B;**不會**&#x200B;公開[!DNL Dynamic Media Classic]中的所有資產，以用於[!DNL Target]活動。

設定之後，請管理[!UICONTROL 選件]資料庫中的影像選件。 請參閱[管理內容](/help/main/c-experiences/c-manage-content/manage-content.md)。

## 帳戶和認證 {#account-and-credentials}

如果您已有[!DNL Dynamic Media]帳戶，請在&#x200B;**[!UICONTROL Scene7設定]**&#x200B;頁面上輸入這些認證。

Adobe不再為新[!DNL Target]客戶或新使用者提供受限制使用、免費的[!DNL Dynamic Media Classic]帳戶。 如果您的組織已有此整合的登入認證，系統仍可繼續運作。 如有帳戶問題，請連絡您的[!DNL Adobe]代表。

## 使用指南 {#usage-guidelines}

搭配此整合使用影像時，請記住下列限制：

* **影像選件，而非儲存體URL。** [!DNL Dynamic Media]個儲存體URL和已發佈的傳遞URL不相同。 請勿從儲存連結建立選件；傳送失敗。 請改用[影像選件](/help/main/c-experiences/c-manage-content/manage-content.md)和交換影像工作流程。
* **自訂程式碼中的公用URL。** 若要直接在選件或自訂程式碼中參考公用影像URL，請在您自己的Web伺服器上託管影像，並使用該URL。 您無法取得已上傳Experience Cloud影像的已發佈URL，以用於目標定位工作流程[!DNL Target]以外的專案；合約不允許使用該專案。
* **合格資產。** 只有上傳到Experience Cloud資產資料夾（以及此整合支援的工作流程）的資產在範圍中，而不是完整的[!DNL Dynamic Media Classic]目錄。

## 在Target中設定Scene7 {#configure-scene7}

使用以下步驟連線[!DNL Dynamic Media Classic] ([!DNL Scene7])：

1. 按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL Scene7設定]**。
1. 輸入您的[!DNL Dynamic Media Classic]帳戶資訊：

   | 欄位 | 說明 |
   | --- | --- |
   | **地區** | 您的[!DNL Dynamic Media]帳戶的地區：北美、歐洲或亞洲。 |
   | **臨機資料夾** | 您手動上傳至[!DNL Dynamic Media]的Target資料夾外部內容位置。 |
   | **電子郵件地址** | 用來登入[!DNL Dynamic Media Classic] ([!DNL Scene7])的電子郵件地址。 |
   | **密碼** | 用來登入[!DNL Dynamic Media Classic] ([!DNL Scene7])的密碼。 |

   ![Scene7設定欄位](/help/main/administrating-target/assets/scene7-1.png)

1. 按一下&#x200B;**[!UICONTROL 「提交」]**。

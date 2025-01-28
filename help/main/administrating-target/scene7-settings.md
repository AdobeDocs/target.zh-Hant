---
keywords: scene7;dynamic media classic;數位資產管理;資產;dam;內容庫;交換影像
description: 了解如何將 Adobe [!DNL Target] 與 Adobe Dynamic Media Classic (先前稱為 Scene7) 整合以在內容庫中提供數位資產管理 (DAM)。
title: 如何設定 Dynamic Media Classic (Scene7) 整合？
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: 484971ab0fcd07205935c0fef3ea1484f40c3e96
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 92%

---

# Dynamic Media Classic (先前稱為 Scene7) 設定

[!DNL Adobe Target]可以與[!DNL Adobe Dynamic Media Classic] （先前為[!DNL Scene7]）整合以在[!UICONTROL Content Library]中提供數位資產管理(DAM)。

>[!NOTE]
>
>將 [!DNL Target] 與 [!DNL Dynamic Media Classic] 整合可讓您將資產 (屬於活動一部分) 的傳送上傳至 [!DNL Adobe Experience Cloud] 資產資料夾。此整合不會啟用對於在 [!DNL Dynamic Media Classic]  上傳以在 [!DNL Target] 活動中傳送之所有資產的存取。

如果您已有 [!DNL Dynamic Media] 帳戶，您可以提供現有的認證。如果您沒有帳戶，您可以向 [!DNL Adobe] 客戶代表免費索取限定使用的 [!DNL Dynamic Media Classic] 帳戶。此帳戶僅可針對受限制的用途在 [!DNL Target] 中使用。此服務已提供給工作流程需要影像交換功能的客戶。

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

如果未設定此設定，則活動建立工作流程內的[!UICONTROL Swap Image offer]選項將不可用。 進行此設定後，[可視化體驗撰寫器 (VEC) 和表單式體驗撰寫器](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中都可以使用交換/變更影像產品建議的選項。然後您可以針對已從 [!DNL Adobe Experience Cloud] 上傳以用於 [!DNL Target] 活動的影像，利用影像產品建議。

如果您想要直接在產品建議中或在活動建立期間的自訂程式碼中參考公用影像 URL，應該將影像部署至您自己的 Web 伺服器，並在程式碼中使用您自己的 URL。沒有方法可取得已上傳至 [!DNL Experience Cloud] 之已發佈影像的 URL，以直接使用或在使用 [!DNL Target] 的鎖定目標工作流程之外使用。根據合約，此功能是不被允許的。

請注意，來自 [!DNL Dynamic Media] 之影像的儲存 URL 和最終發行 URL 是不同的，並且任何人「*不應*」使用影像儲存連結來建立產品建議，因為傳送在此情況下將無法作用。您必須使用我們的說明文件中所解釋的影像產品建議功能。

若要與 [!DNL Dynamic Media Classic] ([!DNL Scene7]) 整合，您必須指定下列資訊。

1. 按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Scene7 Configuration]**。

1. 指定下列 [!DNL Dynamic Media Classic] 帳戶資訊：

   **地區：**&#x200B;您的 [!DNL Dynamic Media] 帳戶的地區：北美、歐洲或亞洲。

   **隨選資料夾：**&#x200B;用於 Target 資料夾外部內容的位置，並且會手動上傳至 [!DNL Dynamic Media]。

   **電子郵件地址：**&#x200B;用來登入 [!DNL Dynamic Media Classic] ([!DNL Scene7]) 的電子郵件地址。

   **密碼：**&#x200B;用來登入 [!DNL Dynamic Media Classic] ([!DNL Scene7]) 的密碼。

1. 按一下 **[!UICONTROL Submit]**。

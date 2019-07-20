---
description: Target Standard可與Adobe Dynamic Media Classic(之前稱為Scene7)整合，在內容庫中提供數位資產管理(DAM)。
seo-description: Target Standard可與Adobe Dynamic Media Classic(之前稱為Scene7)整合，在內容庫中提供數位資產管理(DAM)。
seo-title: Dynamic Media Classic整合
solution: Target
subtopic: 快速入門
title: Dynamic Media Classic整合
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: c6a59843c80017e6f072f65ffad822fe198ebb55

---


# Dynamic Media Classic integration{#scene-settings}

Target Standard可與Adobe Dynamic Media Classic(之前稱為Scene7)整合，在內容庫中提供數位資產管理(DAM)。

>[!NOTE]
>
>將Target與Dynamic Media Classic整合，可讓您傳送上傳至Adobe Experience Cloud資產資料夾的資產(做為活動的一部分)。此整合並不允許存取Dynamic Media Classic中上傳的所有資產，以便在Target活動中傳遞。

如果您已擁有動態媒體帳戶，則可提供現有的認證。如果您沒有帳戶，可以要求受限制的Dynamic Media Classic帳戶，不需向Adobe代表額外付費。此帳戶僅可針對受限制的用途在 Target 中使用。此服務已提供給工作流程需要影像交換功能的客戶。

如果未進行此設定，則活動建立工作流程內的「交換影像」選件選項將不可用。完成此設定之後，交換/變更影像選件的選項可同時在[可視化體驗撰寫器 (VEC) 和表單式體驗撰寫器](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中取得。然後您可以對已從 Adobe Experience Cloud 上傳以用於 Target 活動的影像利用影像選件。

如果您想要直接在選件中或在活動建立期間的自訂代碼中參考公用影像 URL，應該將影像部署至您自己的 Web 伺服器，並在代碼中使用您自己的 URL。沒有方法可取得已上傳至 Experience Cloud 之已發佈影像的 URL，以直接使用或在使用 Adobe Target 的鎖定目標工作流程之外使用。根據合約，此功能是不被允許的。

請注意，來自動態媒體的影像儲存URL和最終發佈URL是不同的，而不能使用影像的儲存連結來建立選件，這在這種情況下無法運作。使用者必須使用我們的文件中所說明的影像選件功能。

若要與Dynamic Media Classic(Scene7)整合，您必須指定下列資訊。

1. 按一下&#x200B;**[!UICONTROL 「設定]** &gt; **[!UICONTROL Scene7 設定」]**。
1. 指定下列Dynamic Media Classic帳戶資訊：

   **地區：** 動態媒體帳戶的地區：北美洲、歐洲或亞洲。

   **臨機資料夾：** 位於目標資料夾之外並手動上傳至動態媒體的內容位置。

   **電子郵件地址：** 用來登入Dynamic Media Classic(Scene7)的電子郵件地址。

   **密碼：** 用來登入Dynamic Media Classic(Scene7)的密碼。
1. 按一下&#x200B;**[!UICONTROL 「提交」]**。

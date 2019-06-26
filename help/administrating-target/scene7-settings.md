---
description: Target Standard 可以與 Adobe Scene7 整合以在內容庫中提供數位資產管理 (DAM)。
seo-description: Target Standard 可以與 Adobe Scene7 整合以在內容庫中提供數位資產管理 (DAM)。
seo-title: Scene7 設定
solution: Target
subtopic: 快速入門
title: Scene7 設定
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Scene7 設定{#scene-settings}

Target Standard 可以與 Adobe Scene7 整合以在內容庫中提供數位資產管理 (DAM)。

>[!NOTE]
>
>將 Target 與 Scene7 整合可讓您將資產 (屬於活動一部分) 的傳送上傳至 Adobe Experience Cloud 資產資料夾。此整合不會啟用對於在 Scene7 上傳以在 Target 活動中傳送之所有資產的存取。

如果您有 Scene7 帳戶，可以提供您的 Scene7 憑證。如果您沒有 Scene7 帳戶，請連絡您的 Adobe 代表，他可以使用您的 Target 帳戶專屬的免費 Scene7 帳戶設定此功能。此帳戶僅可針對受限制的用途在 Target 中使用。此服務已提供給工作流程需要影像交換功能的客戶。

如果未進行此設定，則活動建立工作流程內的「交換影像」選件選項將不可用。完成此設定之後，交換/變更影像選件的選項可同時在[可視化體驗撰寫器 (VEC) 和表單式體驗撰寫器](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中取得。然後您可以對已從 Adobe Experience Cloud 上傳以用於 Target 活動的影像利用影像選件。

如果您想要直接在選件中或在活動建立期間的自訂代碼中參考公用影像 URL，應該將影像部署至您自己的 Web 伺服器，並在代碼中使用您自己的 URL。沒有方法可取得已上傳至 Experience Cloud 之已發佈影像的 URL，以直接使用或在使用 Adobe Target 的鎖定目標工作流程之外使用。根據合約，此功能是不被允許的。

請注意，影像的儲存 URL 和最終 Scene7 發行 URL 是不同的，並且任何人「不應」使用影像儲存連結來建立選件，因為傳送在此情況下將無法作用。使用者必須使用我們的文件中所說明的影像選件功能。

若要與 Scene7 整合，您需要指定您的 Scene7 的一些資訊。

1. 按一下 **[!UICONTROL 「設定]** &gt; **[!UICONTROL Scene7 設定」]**。
1. 指定下列 Scene7 帳戶資訊:

   **Scene7 地區:** 您的 Scene7 帳戶的地區: 北美洲、歐洲或亞洲。

   **Scene7 adhoc 資料夾:** 用於 target 資料夾外部內容的位置，並且會手動上傳至 Scene7。

   **Scene7 電子郵件地址:** 用來登入 Scene7 的電子郵件地址。

   **Scene7 密碼:** 用來登入 Scene7 的密碼。
1. 按一下 **[!UICONTROL 「提交」]**。

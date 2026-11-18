---
keywords: 鎖定目標； Analytics；追蹤伺服器； Analytics for Target； A4T
description: 瞭解如何在[!DNL Adobe Target]中設定活動以使用[!DNL Adobe Analytics]作為報表來源(A4T)。
title: 如何在[!DNL Target]中使用[!DNL Analytics]資料？
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
TQID: 'https://experienceleague.adobe.com/x38YsYI4a6-92oOr6Fs3RfKrJHbSaLNj0cki5CInPPg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 891742a5-242d-5099-966a-ca76c17cd2d2
    internal-label: Analytics for Target (A4T)
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%
---
# 使用[!DNL Adobe Analytics]資料 {#create-a4t}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何設定活動以使用[!DNL Adobe Analytics]作為報告來源(A4T)、開始前要準備什麼，以及如何選擇活動的目標。

>[!ENDSHADEBOX]

Analytics for Target (A4T)會測量資料和量度為[!DNL Adobe Analytics]的[!DNL Adobe Target]活動的結果。 若要使用A4T，請設定活動，讓[!DNL Analytics]成為其報表來源。 如需將[!DNL Analytics]設定為[!DNL Target]資料來源的詳細資訊，請參閱[Adobe Analytics作為Adobe Target的報表Source](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

## 開始之前 {#before-you-begin}

>[!NOTE]
>
>當您的[!DNL Adobe Experience Cloud]帳戶同時連結至[!DNL Analytics]和[!DNL Target]時，**[!UICONTROL Adobe Analytics]**&#x200B;選項可供使用，即使尚未為您的帳戶設定[!DNL Target]和[!DNL Analytics]之間的整合。

建立活動之前，請先建立其目標，例如提高每位訪客帶來的收入(RPV)或增加購物車的點按次數。 然後選擇測量此目標的最終成功量度。 任何時候都可以在[!DNL Analytics]中選取其他量度，但您仍須指定此測試預計會影響的一個量度。

## 選取Analytics作為報表來源 {#select-reporting-source}

>[!NOTE]
>
>如果您使用at.js 0.9.1版或更新版本，當您建立使用[!DNL Adobe Analytics]作為報表來源的活動時，不需要指定追蹤伺服器。 at.js程式庫會自動傳送追蹤伺服器值給[!DNL Target]。 **[!UICONTROL 目標與設定]**&#x200B;頁面上的&#x200B;**[!UICONTROL 追蹤伺服器]**&#x200B;欄位可以保持空白。

已在活動的&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面上選取報表來源。 在此頁面中，您選擇接收[!DNL Target]活動資料的[!DNL Analytics]公司和報表套裝，然後驗證追蹤伺服器。

➡️如需步驟、報表套裝需求以及追蹤伺服器的詳細資訊，請參閱[報告Source](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source)。

當[!DNL Analytics]為報表來源時，活動不提供選項來設定報表對象。 [!DNL Analytics]區段可在[!DNL Target] **[!UICONTROL 活動]**&#x200B;報表中使用。

## 設定活動的目標 {#set-goal}

每個活動都需要成功量度作為目標。 目標是代表活動成功的轉換活動。 可以使用[!DNL Analytics]量度選取器中可用的任何量度。 最佳實務是絕對不要在沒有目標的情況下以特定方式執行測試。

設定目標不會妨礙您使用其他量度來評估測試結果。 然而，目標會識別您想要透過測試改善的專案。

訪客完成目標後，該訪客將不再納入活動中。 如果訪客在完成活動後重新進入活動，則該訪客會計為新訪客。

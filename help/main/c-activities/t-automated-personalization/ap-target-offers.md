---
keywords: 自動個人化；選件；鎖定目標；對象；鎖定規則；鎖定目標
description: 探索如何使用[!UICONTROL Automated Personalization] (AP)活動將個別優惠方案鎖定在特定對象。
title: 如何鎖定[!UICONTROL Automated Personalization]選件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
TQID: 'https://experienceleague.adobe.com/AVqyD-Von-gzuVXC09N9qHY5hEe1QLQwSavCE0mp7Ok'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 8%
---
# 目標[!UICONTROL Automated Personalization]選件 {#target-ap-offers}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中鎖定個別優惠方案給特定對象。

>[!ENDSHADEBOX]

在[!DNL Adobe Target] **[!UICONTROL Automated Personalization]** (AP)活動中，鎖定目標規則可讓您將選件限制在特定對象，只有屬於這些對象的訪客才能看到它。 請謹慎使用鎖定目標規則，且只在業務需求需要這些規則時使用，因為這些規則會減少訪客有資格檢視的選件數量，並可能降低[!DNL Target]個人化模型的有效性。

例如，假設AP活動有三個選件。 選件1有目標規則，限制向對象A曝光。有兩個訪客看到此活動。

| | 訪客 1 | 訪客 2 |
|--- |--- |--- |
| 客群資格篩選 | 對象 A | 對象 B |
| 選件1 [!DNL Target]個人化模型分數 | 90 | 90 |
| 選件2 [!DNL Target]個人化模型分數 | 50 | 70 |
| 選件3 [!DNL Target]個人化模型分數 | 80 | 60 |

訪客1符合對象A的資格，因此此訪客會看到具有最高分數的選件1。 訪客2不是對象A的一部分，因此此訪客會看到選件2，即使最高分是選件1。

## 設定鎖定規則 {#set-up-targeting-rules}

<a id="task_F207ED7A41B84FD39BB6FCBFABF4B23E"></a>

對象鎖定目標規則會控制哪些訪客可以看到每個選件，讓您符合特定業務需求，例如將選件保留給客戶區段。 每個規則都會縮小個人化模型的選擇範圍，因此僅將規則套用至需要規則的優惠方案。

1. 建立或編輯包含您要鎖定選件的[Automated Personalization活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)。

   您可以設定 50 個位置，且每個位置最多可設定 250 個產品建議。

1. 在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;中設定活動的選件之後，請按一下&#x200B;**[!UICONTROL 管理內容]**&#x200B;圖示（ ![管理內容圖示](/help/main/assets/icons/Experience.svg)）。 **[!UICONTROL 管理內容]**&#x200B;對話方塊隨即顯示。

   ![管理內容圖示](../assets/ap-offers-1.png)

1. 按一下「**[!UICONTROL 選件]**」標籤。

1. 選擇要鎖定的選件，然後選擇有資格看見這些選件的對象。

   * 若要針對單一選件設定鎖定目標，請按一下選件旁的「更多資訊」 （![更多資訊圖示](/help/main/assets/icons/MoreSmallList.svg) ）圖示，然後按一下「**[!UICONTROL 目標對象]**」，以顯示「**[!UICONTROL 新增對象]**」對話方塊。
   * 若要針對多個選件設定鎖定目標，請選取選件的核取方塊，然後按一下顯示於清單底部的&#x200B;**[!UICONTROL 鎖定對象]**&#x200B;連結。

   ![管理內容圖示](../assets/ap-offers-2.png)

1. 在&#x200B;**[!UICONTROL 新增對象]**&#x200B;對話方塊中，選取選件的對象，然後按一下&#x200B;**[!UICONTROL 指派對象]**&#x200B;以返回&#x200B;**[!UICONTROL 管理內容]**&#x200B;對話方塊。

   >[!NOTE]
   >
   >您可以結合多個對象與現有的對象，以建立隨選結合的對象，而不建立新的對象。 如需詳細資訊，請參閱[合併多個客群](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

鎖定目標規則現在套用至選取的選件，因此只有屬於指派對象的訪客才能看到這些選件。

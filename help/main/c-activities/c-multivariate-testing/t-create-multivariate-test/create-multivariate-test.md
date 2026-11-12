---
keywords: MVT; 多變數測試; 多變數測試建立; 多變數測試建立; MVT 建立; MVT 建立; MVT 如何; 多變數測試如何
description: 瞭解如何在[!DNL Adobe Target]中使用[!UICONTROL 視覺化體驗撰寫器] (VEC)來建立[!UICONTROL 多變數測試] (MVT)。
title: 如何建立[!UICONTROL 多變數測試]？
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
TQID: 'https://experienceleague.adobe.com/gxrnY43A7OWsiW48Rlq1Orp7ZxBswdAPZEAbRQrCDZA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 16%
---
# 建立多變數測試 {#create-mvt}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)中建立&#x200B;**[!UICONTROL 多變數測試]** (MVT)。 您可以建立活動、建置並檢閱體驗、設定目標，然後設定目標與設定。

>[!ENDSHADEBOX]

在[!DNL Adobe Target]中的&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)可讓您輕鬆建立&#x200B;**[!UICONTROL 多變數測試]**，以及在[!DNL Target]內修改頁面的部分。

[!DNL Target]點選編輯器可讓您挑選任何位置並新增多個選件。

**[!UICONTROL 多變數測試]** (MVT)需要頁面優先的報表。 換句話說，測試會在具有您為頁面所設計體驗的特定 URL 上執行。

請依照下列步驟建立&#x200B;**[!UICONTROL 多變數測試]** (MVT)：

1. [建立活動](#create-activity)
1. [建置並檢閱體驗](#build-experiences)
1. [設定目標](#set-targeting)
1. [設定目標與設定](#configure-goals-and-settings)

## 建立活動 {#create-activity}

選擇活動型別和傳送型別，指定要測試的頁面，並命名活動。

1. 按一下&#x200B;**[!UICONTROL 建立活動]** > **[!UICONTROL 多變數測試]**。

   如需有關 [!DNL Target] 提供的各種活動類型及其差異的詳細資訊，請參閱[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。 請參閱[Target 活動類型](/help/main/c-activities/target-activities-guide.md)，協助您決定哪種活動類型最適合您的需求。

   ![](../../assets/create-mvt-1.png)

1. 選擇傳遞型別： **[!UICONTROL 網頁]**、**[!UICONTROL 行動裝置]**、**[!UICONTROL 電子郵件]**&#x200B;或&#x200B;**[!UICONTROL 其他/API]**。

1. （視條件而定）如果您是[Target Premium](/help/main/c-intro/intro.md#premium)客戶，[請選擇工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. [為您要測試的頁面指定URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#ab-activity-url)。 請使用完整的URL，開頭要包括HTTP或HTTPS。

1. 然後，按一下&#x200B;**[!UICONTROL 建立]**。 **[!UICONTROL 視覺化體驗撰寫器]**&#x200B;開啟。

1. 若要為活動命名，請按一下&#x200B;**[!UICONTROL 編輯]**&#x200B;圖示（![編輯圖示](/help/main/assets/icons/Edit.svg)）並指定活動的描述性名稱，然後按一下&#x200B;**[!UICONTROL 儲存]**。

   {{activity-name-rules}}

   ![](../../assets/create-mvt-2.png)

## 建置並檢閱體驗 {#build-experiences}

將選件新增至每個位置、預覽產生的體驗，以及檢查您的測試計畫是否可行。

1. [在每個位置中建立產品建議](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   您可以新增下列類型的產品建議:

   * HTML
   * 影像
   * 文字

1. 按一下&#x200B;**[!UICONTROL 預覽]**&#x200B;以[預覽您的體驗](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md)。

1. 按一下&#x200B;**[!UICONTROL 顯示體驗]**&#x200B;圖示（![顯示體驗圖示](/help/main/assets/icons/WebPages.svg)）以顯示左側框架中的所有體驗清單，然後按一下清單中的特定體驗以檢視該體驗。

1. [使用流量估算程式](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)來測試您的測試計劃的可行性。

### 排除體驗（選擇性） {#exclude-experiences}

您可能會選擇排除顯示發生衝突變數的體驗，或是審美觀點上不平衡的體驗。

1. 按一下&#x200B;**[!UICONTROL 管理內容]**&#x200B;圖示（![管理體驗圖示](/help/main/assets/icons/Experience.svg)）以顯示&#x200B;**[!UICONTROL 管理體驗]**&#x200B;對話方塊。

1. 若要排除一個體驗，請按一下該體驗旁的&#x200B;**[!UICONTROL 更多動作]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg)），然後按一下&#x200B;**[!UICONTROL 排除]**。

1. 若要排除多個體驗，請選取所需體驗的核取方塊，然後按一下[排除]。****

## 設定目標 {#set-targeting}

選擇哪些訪客進入測試，並檢閱測試摘要。

1. 按一下[下一步]****&#x200B;以存取&#x200B;**[!UICONTROL 鎖定目標]**&#x200B;頁面。

   流程圖表將引導您進行指派對象及其流量百分比、選取流量分配方法，以及指定活動中每個體驗的流量分配的步驟。

1. （視條件而定）按一下&#x200B;**[!UICONTROL 所有訪客]**&#x200B;控制項以選取活動的其他對象。

   **[!UICONTROL 所有訪客]**&#x200B;對象已設定為預設值。 如果您選取其他對象，其名稱會顯示在最左側的控制項中。 例如，您可將項目限制為所有訪客的 50%，或「加州人」客群的 45%。

   +++ 選取不同對象的步驟

   右側框架隨即顯示，可讓您新增或刪除對象，以及指派活動的訪客百分比。

   1. 若要變更對象，請按一下右側框架中的&#x200B;**[!UICONTROL 取代]**&#x200B;圖示（ ![取代圖示](/help/main/assets/icons/Retweet.svg)）。
   1. 在&#x200B;**[!UICONTROL 新增對象]**&#x200B;對話方塊中，[選取所需的對象](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，然後按一下&#x200B;**[!UICONTROL 指派對象]**。

      若要建立結合多個對象的對象，請按一下&#x200B;**[!UICONTROL 結合對象]**。 如需詳細資訊，請參閱[合併多個對象](/help/main/c-target/combining-multiple-audiences.md)。

      若要建立不在&#x200B;**[!UICONTROL 對象庫]**&#x200B;中的新對象，請按一下&#x200B;**[!UICONTROL 建立對象]**。 在[建立對象工作流程](/help/main/c-target/c-audiences/audiences.md)中，選擇下列其中一個選項：

      * **[!UICONTROL 對象庫]**：建立儲存至&#x200B;**[!UICONTROL 對象庫]**&#x200B;的隨選對象，並可在其他活動中重複使用。
      * **[!UICONTROL 僅此活動]**：建立未儲存至&#x200B;**[!UICONTROL 對象庫]**&#x200B;且僅能用於目前活動的[活動特定對象](/help/main/c-target/creating-activity-only-audience.md)。

   1. 按一下右側框架中的&#x200B;**[!UICONTROL 訪客百分比]**，然後選擇符合您要讓其進入活動之訪客的百分比。

   +++

1. [檢閱測試摘要](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7)並進行任何需要的變更，然後按一下[下一步]]**。**[!UICONTROL 

## 設定目標與設定 {#configure-goals-and-settings}

在&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面上，您指示[!DNL Target]如何測量測試。 可用的設定視您使用[!DNL Target]或[!DNL Analytics]作為報表來源而定。

1. 檢閱頁面的區段並設定您需要的專案。 檢視[您在目標與設定頁面](#goals-settings-overview)上設定的專案。


   | 區域 | 您設定的專案 |
   |---|---|
   | **[!UICONTROL 活動設定]** | 選擇性目標&#x200B;**[!UICONTROL 優先順序]** （用於數個活動共用一個位置和一個對象時）和&#x200B;**[!UICONTROL 期間]** （開始和結束日期）。 |
   | **[!UICONTROL 報表設定]** | 報表來源、目標量度（例如&#x200B;**[!UICONTROL 轉換]**&#x200B;量度）、其他量度和報表對象。 此處也提供目標量度的進階設定。 |
   | **[!UICONTROL 其他中繼資料]** | 對您或其他專案團隊成員有用的活動附註。 |

1. 按一下&#x200B;**[!UICONTROL 儲存並關閉]**&#x200B;以建立活動。

如需每個選項的詳細資訊，請參閱[目標與設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#ab-goals-and-settings)。

## 訓練影片：建立多變數測試(9:25) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片示範如何使用[!DNL Target]三步驟引導式工作流程來規劃和建立多變數測試。

* 定義和設計多變數測試
* 建立多變數測試

>[!VIDEO](https://video.tv.adobe.com/v/17395)

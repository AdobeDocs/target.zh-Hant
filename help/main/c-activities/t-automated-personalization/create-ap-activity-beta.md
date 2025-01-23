---
keywords: 自動個人化；ap
description: 瞭解如何使用[!UICONTROL Visual Experience Composer]建立[!UICONTROL Automated Personalization] (AP)活動。
title: 如何建立[!UICONTROL Automated Personalization]活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
hide: true
hidefromtoc: true
exl-id: fe6e5130-53a0-4254-8299-b52086c20004
source-git-commit: 2c10ec521ceed1901ef8c3f95eb11654a7182590
workflow-type: tm+mt
source-wordcount: '1844'
ht-degree: 23%

---

# 建立[!UICONTROL Automated Personalization]活動

使用[!UICONTROL Visual Experience Composer] (VEC)在[!DNL Adobe Target]中建立[!UICONTROL Automated Personalization] (AP)活動。

[!DNL Target]中的[!UICONTROL Automated Personalization] (AP)活動工作流程與其他活動型別的工作流程不同。

1. 從[!DNL Target] [!UICONTROL Activities]清單中，按一下&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]**。

1. 若要使用[!UICONTROL Visual Experience Composer] (VEC)，請按一下&#x200B;**[!UICONTROL Visual]**。

   若要使用[!UICONTROL Form-Based Experience Composer]，請選取[!UICONTROL Form]。 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL Form-Based Experience Composer]，[!DNL Target]還提供[!UICONTROL Single Page Application VEC]。 如需各種撰寫器的詳細資訊，請參閱[體驗和產品建議](/help/main/c-experiences/experiences.md)。
   >
   >如需VEC的疑難排解資訊，請參閱[疑難排解視覺化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （視條件而定） [選擇工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 在&#x200B;**[!UICONTROL Enter Activity URL]**&#x200B;方塊中，指定您的[活動URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)。

   如果您的帳戶[設定了預設的 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，該 URL 依預設會顯示。您可以視需要將預設URL變更為其他URL。

   [!DNL Target]不會區分URL通訊協定（[!DNL https]和[!DNL http]）。 因此，[!DNL `http://www.adobe.com`]和[!DNL `https://wwww.adobe.com`]都相符。

1. 按一下 **[!UICONTROL Create]**。

   具有指定URL的頁面會在VEC中開啟。

1. 按一下&#x200B;**[!UICONTROL Rename]**&#x200B;圖示（![重新命名圖示](/help/main/assets/icons/MoreSmallListVert.svg)）、按一下&#x200B;**[!UICONTROL Rename]**、指定活動的名稱，然後按一下&#x200B;**[!UICONTROL Save]**。

   活動名稱的開頭不能是下列任一字元：

   | 字元 | 說明 |
   |--- |--- |
   | `=` | 等號 |
   | `+` | 加號 |
   | `-` | 減號 |
   | `@` | 「@」符號 |

   活動名稱不能包含下列任一字元順序：

   | 字元順序 | 說明 |
   |--- |--- |
   | ；= | 分號，等於 |
   | ；+ | 分號，加號 |
   | ；- | 分號，減號 |
   | ；@ | 分號， At sign |
   | ，= | 逗號，等於 |
   | ，+ | 逗號，加號 |
   | ，- | 逗號，減號 |
   | ，@ | 逗號， At sign |
   | `[`&quot; | 左方括弧，雙引號 |
   | &quot;`]` | 雙引號，右方括弧 |

1. 按照[可視化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)中的說明修改頁面元素。

   您可以從資產管理員一次選取多個影像。這可讓您快速檢視頁面，其中包含為活動設定的每個影像。 您也可以輕鬆在您的產品建議中編輯文字元素。編輯元素時，該元素上會出現一個橫條，指出您已變更它。

1. 按一下&#x200B;**[!UICONTROL Manage Content]**&#x200B;圖示（![管理內容圖示](/help/main/assets/icons/Experience.svg) ）來設定可用的組合。

   畫面上方會顯示一個對話方塊，其中有兩個選項： [!UICONTROL Experiences]和[!UICONTROL Offers]。

   >[!NOTE]
   >
   >雖然您可以在AP活動中建立最多30,000個體驗，但使用的體驗少於5,000個時，活動的執行效能最佳。 即使活動已啟用[!UICONTROL Disalow Duplicates]選項，此限制也會套用。

   [!UICONTROL Experiences]清單會顯示為活動選取的每個內容片段，及其獲指派的位置。

   您可以選取所需體驗旁的核取方塊，然後按一下「[!UICONTROL Exclude]」圖示，以排除特定體驗。

   您可以選取相關體驗的核取方塊，然後按一下[!UICONTROL Exclude]圖示，以分批排除或包含體驗。

1. （依條件）按一下「**[!UICONTROL Offers]**」來選取內容片段，並將它們指派給報表群組，或只允許特定訪客檢視特定具有鎖定目標的選件。

   如需報表群組的詳細資訊，請參閱[Automated Personalization中的選件報表群組](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)。

<!--
1. (Conditional) Click **[!UICONTROL Exclusion Groups]** to choose any combination of elements that you want to exclude from the activity.

   ![Exclusion Groups tab of Manage Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Although you can create up to 30,000 experiences in an AP test, the algorithm performs its best when fewer than 10,000 distinct experiences are used. This same limit is applied even when the activity has enabled the [!UICONTROL Disalow Duplicates] option.

   If you do not currently have any exclusion groups included in your activity, click **Create Exclusion Group**. You can filter to create a list that shows only the combinations you want to exclude. Name your exclusion group, then click **Save**.

   To edit an existing exclusion group, hover over the group you want to edit, then click the pencil icon.-->

1. 完成活動內容的設定時，請按一下&#x200B;**[!UICONTROL Done]**。

1. 按一下[!UICONTROL Visual Experience Composer]頂端的&#x200B;**[!UICONTROL Targeting]**，以前往三步驟引導工作流程中的下一個步驟。

   如果您曾使用其他[!DNL Target]活動型別，**鎖定目標**&#x200B;步驟看起來會很熟悉。 您可以在此選取受眾，並指定看到每個體驗的訪客百分比。

   流程圖表隨即開啟。

   ![AP測試鎖定目標步驟](/help/main/c-activities/t-automated-personalization/assets/ap-traffic-flow.png)

   流程圖表將引導您進行指派對象及其流量百分比、選取流量分配方法，以及指定活動中每個體驗的流量分配的步驟。

1. （視條件而定）按一下&#x200B;**[!UICONTROL All Visitors]**&#x200B;控制項以選取活動的其他對象。

   [!UICONTROL All Visitors]對象已設定為預設值。 如果您選取其他對象，其名稱會顯示在最左側的控制項中。

   右側框架隨即顯示，可讓您新增或刪除對象，以及指派活動的訪客百分比。

   1. 若要變更對象，請按一下右側框架中的&#x200B;**[!UICONTROL Replace]圖示** （ ![取代圖示](/help/main/assets/icons/Retweet.svg) ）。
   1. 在[!UICONTROL Add Audience]對話方塊中，[選取所需的對象](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，然後按一下&#x200B;**[!UICONTROL Assign Audience]**。

      您可以按一下&#x200B;**結合對象**&#x200B;到[建立結合多個對象的對象](/help/main/c-target/combining-multiple-audiences.md)。

      如果您需要建立不在[!UICONTROL Audience Library]中的新對象，請按一下&#x200B;**建立對象**。 在[建立對象工作流程](/help/main/c-target/c-audiences/audiences.md)期間，您可以從下列選項中選擇：

      * **[!UICONTROL Audience Library]**：建立儲存至[!UICONTROL Audience Library]、可於其他活動中重複使用的隨選對象。
      * **[!UICONTROL This activity only]**：建立未儲存至[!UICONTROL Audience Library]且只能用於目前活動的[活動特定對象](/help/main/c-target/creating-activity-only-audience.md)。

   1. 按一下右側框架中的&#x200B;**[!UICONTROL Visitor Percentage]**，然後選擇符合您要讓其進入活動之訪客的百分比。

   例如，您可將項目限制為所有訪客的 50%，或「加州人」客群的 45%。

1. 按一下&#x200B;**[!UICONTROL Traffic Allocation]**&#x200B;控制項以從下列選項中選擇：

   ![流量分配目標選項](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap-new.png)

   * **[!UICONTROL Evaluate Personalization Algorithm (50/50)]：**&#x200B;如果您的目標是要測試演演算法，請在控制與鎖定的演演算法之間使用訪客的50/50百分比分割。 此分割可提供提升度更準確的預估。建議搭配使用「隨機體驗」作為控制。
   * **[!UICONTROL Maximizing Personalization Traffic (90/10)]：**&#x200B;如果您的目標是要建立「一律開啟」的活動，請將10%的訪客放入控制項。 此選項可確保有足夠的資料供演演算法隨著時間繼續學習。 這裡的取捨是以更大比例的流量交換個人化，因此在確切的提升度方面較不精確。 無論您的目標為何，此選項都是使用特定體驗作為控制時的建議流量分割。
   * **[!UICONTROL Custom Allocation]：**&#x200B;視需要手動分割百分比。

1. （視條件而定）從[!UICONTROL Control]下拉式清單中，[選取要用來作為控制的特定體驗](/help/main/c-activities/t-automated-personalization/experience-as-control.md)或選取[!UICONTROL Random Experience.]

   控制體驗提供比較來判斷自動測試提供了多少提升度。

   [!UICONTROL Automated Personalization]一律會針對控制組測量效能。 最佳作法是放置至少 10% 的加入者至控制群組。如果您的目標是測試為其提供資料的個人化演演算法是否比沒有個人化更好（例如，隨機提供的控制），則控制和個人化演演算法之間的50/50流量分割是實現此目標的最快和最準確的方式。 如果您想要最大化個人化的流量量，而且不太在意活動正在產生的確切提升度，在控制與個人化演演算法之間分配10/90%的流量是實現此目標的最快速且最準確的方式。

   >[!NOTE]
   >
   >在[!UICONTROL Automated Personalization]活動中，會評估每個要求的輸入條件（URL鎖定目標、範本規則和對象目標）。 在舊版中，會對每個工作階段評估輸入條件。

1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;以顯示&#x200B;**[!UICONTROL Goals & Settings]**&#x200B;頁面。
1. 使用下列設定來設定活動，然後按一下&#x200B;**[!UICONTROL Save & Close]**。

   | 設定 | 說明 |
   |--- |--- |
   | [!UICONTROL Name] | 為活動命名。為活動提供一個描述清楚的名稱，讓團隊成員可以在[!UICONTROL Activities]清單中識別它。 請查閱上表以瞭解哪些字元不得用於活動名稱中。 |
   | [!UICONTROL Objective] | (可選) 輸入測試的目標。目標可幫助您記住活動的目的。 |
   | [!UICONTROL Priority] | 根據您的設定，[!UICONTROL Priority]的[!DNL Target] UI和選項會有所不同。 您可以使用[!UICONTROL Low]、[!UICONTROL Medium]或[!UICONTROL High]的舊版設定，也可以啟用0到999的精細優先順序。<P>如果將多個活動指派至具有相同客群的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。<P>如果未在[!UICONTROL Administration] > [!UICONTROL Reporting] （預設）中啟用此選項，請指定優先順序： [!UICONTROL Low]、[!UICONTROL Medium]或[!UICONTROL High]。<P>若要啟用微調優先順序，請按一下「[!UICONTROL Administration] > [!UICONTROL Reporting]」，然後將「[!UICONTROL Enable Fine-Grained Priorities]」選項切換到「開啟」位置。<P>如果已啟用此選項，請指定從0到999的值：<ul><li>0 = 低</li><li>999 = 高</li></ul>對於在舊版[!DNL Target Standard/Premium]中建立的活動，[!UICONTROL Low]優先順序會轉換為0，[!UICONTROL Medium]優先順序會轉換為5，而[!UICONTROL High]優先順序會轉換為10。 您可以視需要調整這些值。<P>**注意**：在使用微調優先順序後，在您可以停用此選項之前，必須將所有優先順序設定回0、5和10。 |
   | [!UICONTROL Duration] | 設定活動的開始和結束日期。 您可以選取[!UICONTROL When Activated]或指定特定的日期和時間。 |
   | [!UICONTROL Optimization Goal] | 指定最佳化目標，其中包含兩個參數:<ul><li>要使用活動測量的項目</li><li>活動加入者採取的動作，顯示已達成目標。</li></ul>您可以選取[!UICONTROL My Primary Goal]右側的三個點，以命名最佳化目標。 [!UICONTROL Automated Personalization]個活動可以測量[!UICONTROL Conversion]或[!UICONTROL Revenue]。 可透過檢視頁面或檢視mbox來達到轉換。 也可以追蹤點擊。<P>主要目標也會變成模型系統用來計算體驗成功的模型量度。<P>您可以在達到模型目標之後，基於追蹤目的，讓使用者保持在活動中。例如，通常使用[!UICONTROL Automated Personalization]活動來改善點按率，並且設為模型目標。 不過，務必查看增加的點擊率如何造成最終轉換，使得透過最終的轉換進行追蹤非常必要。<P>您可以提供多個量度上的相依性，並且具有彈性可選擇量度應為達到或未到達時計數才會增加。<P>您必須定義兩個 (或多個) 成功量度，之後才可以讓某個量度相依於另一個量度。<P>[!UICONTROL Add Dependency]選項允許在已達到另一個成功量度或尚未達到時遞增成功量度。<P>若要新增相依性:<ol><li>新增其他量度後，按一下[!UICONTROL Additional Goal]右側的三個點功能表下的&#x200B;**[!UICONTROL Advanced Settings]**。</li><li>按一下[!UICONTROL Reporting Settings]區段底部的&#x200B;**[!UICONTROL Add Dependency]**&#x200B;選項。</li><li>將需要的量度從左窗格拖曳到右窗格，然後按一下[!UICONTROL Reached]以在[!UICONTROL Reached]與[!UICONTROL Not Reached]之間切換設定。</li></ol>您可以在新增相依性之後加以編輯或移除。 |
   | [!UICONTROL Conversion Metric] | 依預設，轉換量度與最佳化目標量度相同。 不過，您可以取消勾選[!UICONTROL Same as Optimization Goal]選項，以定義個別的轉換量度。 |
   | [!UICONTROL Additional Metrics] | 新增您要使用的任何其他報表量度。 您可以新增轉換或收入量度。<P>**注意**： [!UICONTROL Engagement]量度不支援作為額外的量度。 [!DNL Target] UI可讓您選取[!UICONTROL Engagement]量度，但資料未準確顯示在報表中。 |
   | [!UICONTROL Audiences for Reporting] | 新增對象以在報表中啟用按對象篩選。依預設，報表會顯示所有合格訪客的結果。新增對象以篩選結果，以獲得更明確的訪客子集。<P>**附註**：與其他活動型別不同，[!UICONTROL Automated Personalization]無法使用[!UICONTROL Adobe Analytics]作為其報告來源(A4T)。 |
   | [!UICONTROL Notes] | 輸入任何對您或其他專案團隊成員有用的活動相關資訊。 [!UICONTROL Notes]窗格可調整大小。 |

   為量度命名或重新命名時，不得使用下列字元：

   | 字元 | 說明 |
   |--- |--- |
   | / | 正斜線 |
   | ? | 問號 |
   | # | 數字符號 |
   | : | 冒號 |
   | = | 等號 |
   | + | 加號 |
   | - | 減號 |
   | @ | 「@」符號 |

按一下&#x200B;**[!UICONTROL Save & Close]**&#x200B;之後，會顯示活動的[!UICONTROL Overview]頁面。 按一下&#x200B;**預覽體驗**&#x200B;以預覽您的體驗在傳遞時的外觀。 快顯視窗會顯示出來，您可以使用它來檢視和共用您網站上的AP體驗連結，以取得[!UICONTROL Target] [!UICONTROL Visual Experience Composer] (VEC)外部體驗的「真實預覽」。 您必須分享來自訊息的連結以分享預覽。按一下連結然後直接從瀏覽器複製URL無法運作。 複製連結會導致URL包含引數，只有在您從訊息中的連結存取頁面時，才會正確顯示頁面。

如需關於報告的資訊，請參閱[Automated Personalization報告](/help/main/c-reports/personalization-reports/reports-ap.md)。

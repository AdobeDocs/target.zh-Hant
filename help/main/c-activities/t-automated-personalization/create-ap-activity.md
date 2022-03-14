---
keywords: 自動個性化；ap;avociems;ensemble；隨機森林；殘差方差；誤差方差；生存期值
description: 瞭解如何建立 [!UICONTROL Automated Personalization] (AP) [!DNL Adobe Target] 使用Visual Experience Composer。
title: 如何建立 [!UICONTROL Automated Personalization] 活動？
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '2048'
ht-degree: 91%

---

# ![PREMIUM](/help/main/assets/premium.png) 建立自動個人化活動

的 [!UICONTROL Automated Personalization] (AP)中的活動工作流 [!DNL Adobe Target] 不同的活動類型。

1. 從 [!DNL Target] [!UICONTROL 活動] 清單，按一下 **[!UICONTROL 建立活動]** > **[!UICONTROL Automated Personalization]**。

   ![建立活動: Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap_create-new.png)

1. 使用 [!UICONTROL 視覺體驗作曲家] (VEC)，按一下 **[!UICONTROL 可視（預設）]**。

   ![建立 Automated Personalization 活動對話方塊](/help/main/c-activities/t-automated-personalization/assets/ap_url-new.png)

   如果你想用 [!UICONTROL 基於表單的體驗作曲家]選中 [!UICONTROL 窗體]。 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和 [!UICONTROL 基於表單的體驗作曲家]。 [!DNL Target] 提供 [!UICONTROL 單頁應用程式VEC] 和移動應用的VEC。 如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/main/c-experiences/experiences.md)。
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上圖中的[!UICONTROL 選擇工作區]選項是 [Target Premium](/help/main/c-intro/intro.md) 功能。如果您沒有看到此選項，表示您的組織擁有的是 Target Standard 授權。

1. （條件）如果您是 [!DNL Target] 高級客戶， [選擇工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 驗證或輸入活動 URL，然後按一下&#x200B;**[!UICONTROL 「下一步」]**。

   >[!NOTE]
   >
   >[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `http://www.adobe.com`] 和 [!DNL `https://wwww.adobe.com`] 都相符。

   具有指定 URL 的頁面會在可視化體驗撰寫器中開啟。

1. 要命名活動，請按一下 **[!UICONTROL 名稱]** 並鍵入活動名稱。

   ![名稱欄位](/help/main/c-activities/t-automated-personalization/assets/ab_newname-new.png)

   活動名稱不能以下列任何字元開頭：

   | 字元 | 說明 |
   |--- |--- |
   | `=` | 等號 |
   | `+` | 加號 |
   | `-` | 減號 |
   | `@` | 「@」符號 |

1. 按照[可視化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)中的說明修改頁面元素。

   您可以從資產管理員一次選取多個影像。此可讓您快速檢視頁面上對活動設定的每個影像。您也可以輕鬆在您的選件中編輯文字元素。編輯元素時，該元素上會出現一個橫條，指出您已變更它。

1. 按一下&#x200B;**[!UICONTROL 「管理內容」]**&#x200B;來設定可用的組合。

   ![管理內容選項](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   畫面上方隨即出現對話方塊，並帶有三個選項: 體驗、選件和排除群組。

   ![管理內容對話方塊](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >雖然您可以在 AP 活動中建立最多 30,000 個體驗，但使用的體驗少於 5,000 個時，活動的執行效能最佳。

   [!UICONTROL 體驗]清單會顯示為活動選取的每個內容片段，及其獲指派的位置。

   您可以暫留在所需的體驗上，然後按一下排除圖示，以排除特定的體驗。

   ![排除圖示暫留](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   您可以選取相關體驗的核取方塊，然後按一下對話方塊右上角的排除圖示，以分批排除/包含體驗。

   ![分批排除選項](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   您可以按一下&#x200B;**狀態**&#x200B;下拉式清單以篩選此清單檢視，以顯示僅限排除或僅限包含的活動。

1. (依條件) 按一下&#x200B;**[!UICONTROL 「選件」]**，選取內容片段並將它們指派給報表群組，或只允許特定訪客查看特定具有鎖定目標的選件。

   如需詳細資訊，請參閱[自動個人化中的選件報表群組](/help/main/c-reports/offer-reporting-groups-in-automated-personalization.md#concept_194128C0B56B4B26AAB57DB49892960C)。

   使用[!UICONTROL 「位置」]清單，依位置篩選選件。使用[!UICONTROL 「報表群組」]清單，依報表群組篩選選件。您也可以使用[!UICONTROL 「報表群組」]清單，篩選[!UICONTROL 「未指派的選件」]，為目前未指派任何報表群組的選件，指派報表群組。

   您可以將游標移至所需的選件上，然後按一下資料夾圖示，藉此將特定體驗新增至報表群組中。

   ![資料夾圖示暫留](/help/main/c-activities/t-automated-personalization/assets/icon-folder.png)

   您可以選取相關體驗的核取方塊，然後按一下對話方塊右上角的報表群組資料夾圖示按鈕，藉此將體驗分批新增至報表群組中。

   ![報表群組選項](/help/main/c-activities/t-automated-personalization/assets/report-group-options.png)

   請務必瞭解報表群組影響 Target 建置其模型的方式。因此，建議您僅在計劃於活動上線時取代或新增選件時才使用報表群組。如果對已上線活動推出新選件，將新選件放到具有現有類似選件的群組中，可允許機器使用已為其群組中其他選件所收集的資料，以學習新選件的相關資訊。您永遠不應將所有選件放置在單一報表群組中。

   如需將選件鎖定在特定對象的相關資訊，請參閱[Target AP 選件](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E)。

1. (依條件) 按一下&#x200B;**[!UICONTROL 「排除群組」]**&#x200B;來選擇您要從活動中排除的任何元素組合。

   ![管理內容對話方塊的排除群組標籤](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   雖然您可以在 AP 測試中建立最多 30,000 個體驗，使用少於 10,000 相異體驗時，演算法的執行效能最佳。

   如果您目前尚未在您的活動中包括任何排除群組，請按一下&#x200B;**「建立排除群組」**。您可以篩選以建立僅顯示您要排除之組合的清單。命名您的排除群組，然後按一下&#x200B;**「儲存」**。

   若要編輯現有的排除群組，請將游標暫留在您要編輯的群組上方，然後按一下鉛筆圖示。

1. 完成活動內容的設定時，請按一下&#x200B;**[!UICONTROL 完成]**。

1. 如果您曾使用其他 Target 活動類型，**「鎖定目標」**&#x200B;步驟將很熟悉。您可以在此按一下&#x200B;**[!UICONTROL 「自訂分配」]**&#x200B;下拉式清單，然後按一下&#x200B;**「下一步」**，以選取對象並指定會看見控制體驗之訪客的百分比。

   [!UICONTROL 「自訂分配」]下拉式清單可讓您從下列選項中選擇:

   ![流量分配目標下拉式清單](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **評估個人化演算法 (50/50):**&#x200B;如果您的目標是要測試演算法，請在控制與鎖定的演算法之間使用訪客的 50/50 百分比分割。此分割可提供提升度更準確的預估。建議「隨機體驗」搭配使用以作為控制。
   * **最大化個人化流量 (90/10):**&#x200B;如果您的目標是要建立「一律開啟」的活動，請將 10% 的訪客放入控制，以確保有足夠的資料供演算法隨著時間繼續學習。請注意，這裡的取捨是以更大比例的流量交換個人化，因此在確切的提升度方面較不精確。無論您的目標為何，這是使用特定體驗作為控制時的建議流量分割。
   * **自訂分配:** 視需要手動分割百分比。

1. (視條件而定) 從[!UICONTROL 控制]下拉式清單中，[選取要用來作為控制的特定體驗](/help/main/c-activities/t-automated-personalization/experience-as-control.md)，或選取[!UICONTROL 隨機體驗]。

   控制體驗提供比較來判斷自動測試提供了多少提升度。

   自動個人化一律會測量控制群組的效能。最佳作法是放置至少 10% 的加入者至控制群組。如果您的目標是要測試資料上個人化演算法是否比無個人化項目 (亦即隨機提供的控制) 執行得更好，那麼在控制和個人化演算法之間使用 50/50 百分比的流量分割會是達成此目標最快和最準確的方式。如果您想要將個人化的流量最大化，並且較不在意瞭解您的活動所產生的確切提升度，那麼，在控制和個人化演算法之間使用 10/90 百分比的流量分割會是達成此目標最快和最準確的方式。

   >[!NOTE]
   >
   >在自動個人化活動中，系統會評估每個要求的輸入條件 (URL 鎖定目標、範本規則、對象目標)。在舊版中，會對每個工作階段評估輸入條件。

1. 按一下&#x200B;**[!UICONTROL 下一步]**&#x200B;以顯示&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面。
1. 使用下列設定來設定活動，然後按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

   | 設定 | 說明 |
   |--- |--- |
   | 名稱 | 為活動命名。請為活動提供描述清楚的名稱，讓團隊成員能夠在活動清單中識別出來。請查閱上表以瞭解哪些字元不得用於活動名稱中。 |
   | 目標 | (可選) 輸入測試的目標。目標可幫助您記住活動的目的。 |
   | 優先順序 | 視您的設定而定，優先順序的 UI 和選項可能有所不同。您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。<br>如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。<br>如果未在中啟用此選項 [!UICONTROL 管理] > [!UICONTROL 報告] （預設值），指定優先順序：低、中或高。<br>要啟用細粒度優先順序，請按一下 [!UICONTROL 管理] > [!UICONTROL 報告]，然後切換 [!UICONTROL 啟用細粒度優先順序] 的雙曲餘切值。<br>如果已啟用此選項，請指定介於 0 和 999 之間的值:<ul><li>0 = 低</li><li>999 = 高</li></ul>對於在舊版 Target Standard/Premium 中建的立活動，低優先順序會轉換為 0，中會轉換為 5，而高則轉換為 10。您可以視需要調整這些值。<br>****&#x200B;注意: 在使用微調優先順序後，在您可以停用此選項之前，必須將所有優先順序設定回 0、5 和 10。 |
   | 持續時間 | 設定活動的開始和結束日期。 |
   | 最佳化目標 | 指定最佳化目標，其中包含兩個參數:<ul><li>要使用活動測量的項目</li><li>活動加入者採取的動作，顯示已達成目標。</li></ul>您可以透過選取「我的主要目標」右側的三個點，來選擇為最佳化目標命名。自動個人化活動可以測量轉換、RPV 和 AOV。轉換可透過檢視頁面或檢視 mbox 來達成。也可以追蹤點擊。<br>主要目標也會變成模型量度，供模型系統用來計算體驗的成功。<br>您可以在達到模型目標之後，基於追蹤目的，讓使用者保持在活動中。例如，Automated Personalization 活動經常用來改善點擊率，並且設為模型目標。不過，務必查看增加的點擊率如何造成最終轉換，使得透過最終的轉換進行追蹤非常必要。<br>您可以提供多個量度上的相依性，並且具有彈性可選擇量度應為達到或未到達時計數才會增加。<br>您必須定義兩個 (或多個) 成功量度，之後才可以讓某個量度相依於另一個量度。<br>「新增相依性」選項允許在已達到另一個成功量度或尚未達到時遞增成功量度。<br>若要新增相依性:<ol><li>新增其他量度之後，請按一下「其他目標」右側的三個點功能表下的[!UICONTROL 「進階設定」]。</li><li>按一下[!UICONTROL 「報表設定」]區段底部的[!UICONTROL 「新增相依性」]選項。</li><li>將需要的量度從左窗格拖曳到右窗格，然後按一下[!UICONTROL 「達到」]以在[!UICONTROL 「達到」]與[!UICONTROL 「未達到」]之間切換設定。</li></ol>您可以在新增相依性之後加以編輯或移除。 |
   | 轉換量度 | 根據預設，轉換量度與最佳化目標量度相同。不過，您可以取消勾選[!UICONTROL 與最佳化目標相同]選項，以定義不同的轉換量度。 |
   | 其他量度 | 新增您要使用的任何其他報表量度。您可以新增轉換或收入量度。<br>**注意**: 參與量度也不支援作為其他量度。UI 可能會讓您選取參與量度，但資料將不會在報表中準確顯示。 |
   | 報表的對象 | 新增對象以在報表中啟用按對象篩選。依預設，報表會顯示所有合格訪客的結果。新增對象以篩選結果，以獲得更明確的訪客子集。<br>**注意**: 與其他活動類型不同，自動個人化無法使用 Adobe Analytics 作為其報表來源。 |
   | 附註 | 輸入關於活動的任何資訊，將該資訊放在手邊對您或其他團隊成員來說很有用。「備註」窗格可調整大小。 |

   請注意，為量度命名或重新命名時，不得使用下列字元:

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

按一下&#x200B;**[!UICONTROL 「建立」]**&#x200B;之後，活動摘要隨即出現。按一下&#x200B;**「預覽體驗」**&#x200B;即可預覽體驗傳遞後的外觀。隨即會出現彈出視窗，您可用來檢視和共用網站上 AP 體驗的連結，以獲得在 Target 可視化體驗撰寫器外部的「實際預覽」體驗。您必須分享來自訊息的連結以分享預覽。按一下連結，然後直接從頁面複製 URL 將沒有作用，因為 URL 包含的參數只會在您透過訊息中的連結存取頁面時正確顯示頁面。

如需關於報表的資訊，請參閱[自動個人化報表](/help/main/c-reports/reports-ap.md#concept_C02BAFC922114A44846998FD956E345A)。

---
keywords: 自動個人化；ap；對象；整體；隨機森林；殘差變異；錯誤變異；期限值
description: 了解如何建立 [!UICONTROL Automated Personalization] (AP)中的活動 [!DNL Adobe Target] 使用 [!UICONTROL 可視化體驗撰寫器].
title: 如何建立 [!UICONTROL Automated Personalization] 活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '1853'
ht-degree: 60%

---

# [!UICONTROL 建立 Automated Personalization 活動]

建立 [!UICONTROL Automated Personalization] (AP)中的活動 [!DNL Adobe Target] 使用 [!UICONTROL 可視化體驗撰寫器] (VEC)。

此 [!UICONTROL Automated Personalization] (AP)中的活動工作流程 [!DNL Adobe Target] 會與其他活動類型的工作流程有所不同。

1. 從 [!DNL Target] [!UICONTROL 活動] 清單，按一下 **[!UICONTROL 建立活動]** > **[!UICONTROL Automated Personalization]**.

   ![建立活動: Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. 若要使用VEC，請按一下 **[!UICONTROL 視覺（預設）]**.

   ![建立 Automated Personalization 活動對話方塊](/help/main/c-activities/t-automated-personalization/assets/ap_url-new.png){width="300"}

   若要使用 [!UICONTROL 表單式體驗撰寫器]，選取 [!UICONTROL 表單]. 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和 [!UICONTROL 表單式體驗撰寫器], [!DNL Target] 選件 [!UICONTROL 單頁應用程式VEC]. 如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/main/c-experiences/experiences.md)。
   >
   >如需VEC的疑難排解資訊，請參閱 [疑難排解可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. （有條件） [選擇工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. 驗證或輸入活動 URL，然後按一下&#x200B;**[!UICONTROL 「下一步」]**。

   >[!NOTE]
   >
   >[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `http://www.adobe.com`] 和 [!DNL `https://wwww.adobe.com`] 都相符。

   具有指定URL的頁面會在VEC中開啟。

1. 若要為活動命名，請按一下 **[!UICONTROL 名稱]** 欄位並輸入活動名稱。

   ![名稱欄位](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

   活動名稱不能以下列任一字元開頭：

   | 字元 | 說明 |
   |--- |--- |
   | `=` | 等號 |
   | `+` | 加號 |
   | `-` | 減號 |
   | `@` | 「@」符號 |

   此外，活動名稱不能包含下列任何字元序列：&#39;;=&#39;, &#39;;+&#39;, &#39;;-&#39;, &#39;;@&#39;, &#39;,=&#39;, &#39;,+&#39;, &#39;,-&#39;, &#39;,@&#39;[&quot;&#39;, &#39;&#39;]&#39;, &#39;[&quot;, &quot;]&#39;。

1. 按照[可視化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)中的說明修改頁面元素。

   您可以從資產管理員一次選取多個影像。此可讓您快速檢視頁面上對活動設定的每個影像。您也可以輕鬆在您的選件中編輯文字元素。編輯元素時，該元素上會出現一個橫條，指出您已變更它。

1. 按一下&#x200B;**[!UICONTROL 「管理內容」]**&#x200B;來設定可用的組合。

   ![管理內容選項](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   畫面頂端會出現一個對話方塊，包含三個選項： [!UICONTROL 體驗], [!UICONTROL 選件]，和 [!UICONTROL 排除群組].

   ![管理內容對話方塊](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >雖然您可以在 AP 活動中建立最多 30,000 個體驗，但使用的體驗少於 5,000 個時，活動的執行效能最佳。即使活動已啟用 [!UICONTROL 不允許重複項目] 選項，此限制亦適用。

   此 [!UICONTROL 體驗] 清單會顯示為活動選取的每個內容片段，以及指派給該活動的位置。

   您可以暫留在所需的體驗上，然後按一下 [!UICONTROL 排除] 表徵圖。

   ![排除圖示暫留](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   您可以選取相關體驗的核取方塊，然後按一下 [!UICONTROL 排除] 對話框的右上角。

   ![分批排除選項](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   您可以按一下[!UICONTROL 狀態]下拉式清單以篩選此清單檢視，以顯示僅限排除或僅限包含的活動。

1. (依條件) 按一下&#x200B;**[!UICONTROL 「選件」]**，選取內容片段並將它們指派給報表群組，或只允許特定訪客查看特定具有鎖定目標的選件。

   如需報告群組的詳細資訊，請參閱 [Automated Personalization中的選件報表群組](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. (依條件) 按一下&#x200B;**[!UICONTROL 「排除群組」]**&#x200B;來選擇您要從活動中排除的任何元素組合。

   ![管理內容對話方塊的排除群組標籤](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   雖然您可以在 AP 測試中建立最多 30,000 個體驗，使用少於 10,000 相異體驗時，演算法的執行效能最佳。即使活動已啟用 [!UICONTROL 不允許重複項目] 選項，此限制亦適用。

   如果您目前尚未在您的活動中包括任何排除群組，請按一下&#x200B;**「建立排除群組」**。您可以篩選以建立僅顯示您要排除之組合的清單。命名您的排除群組，然後按一下&#x200B;**「儲存」**。

   若要編輯現有的排除群組，請將游標暫留在您要編輯的群組上方，然後按一下鉛筆圖示。

1. 完成活動內容的設定時，請按一下&#x200B;**[!UICONTROL 完成]**。

1. 此 **定位** 如果您使用其他步驟，則步驟看起來很熟悉 [!DNL Target] 活動類型。 您可以在此按一下 **[!UICONTROL 自訂分配]** 下拉式清單，然後按一下 **下一個**.

   [!UICONTROL 「自訂分配」]下拉式清單可讓您從下列選項中選擇:

   ![流量分配目標下拉式清單](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL 評估個人化演算法(50/50)]:** 如果您的目標是要測試演算法，請在控制與目標演算法之間使用訪客的50/50%分割。 此分割可提供提升度更準確的預估。建議與「隨機體驗」搭配使用，作為您的控制。
   * **[!UICONTROL 最大化個人化流量(90/10)]:** 如果您的目標是建立「一律開啟」活動，請將10%的訪客放入控制中。 此選項可確保有足夠的資料供演算法隨著時間繼續學習。 請注意，這裡的取捨是，為了將較大比例的流量個人化，您在確切提升度方面的精確度較低。 無論您的目標為何，這是使用特定體驗作為控制時的建議流量分割。
   * **[!UICONTROL 自訂分配]:** 視需要手動分割百分比。

1. (視條件而定) 從[!UICONTROL 控制]下拉式清單中，[選取要用來作為控制的特定體驗](/help/main/c-activities/t-automated-personalization/experience-as-control.md)，或選取[!UICONTROL 隨機體驗]。

   控制體驗提供比較來判斷自動測試提供了多少提升度。

   [!UICONTROL 自動個人化一律會測量控制群組的效能。]最佳作法是放置至少 10% 的加入者至控制群組。如果您的目標是要測試資料上個人化演算法是否比無個人化項目 (亦即隨機提供的控制) 執行得更好，那麼在控制和個人化演算法之間使用 50/50 百分比的流量分割會是達成此目標最快和最準確的方式。如果您想要將個人化的流量最大化，並且較不在意瞭解您的活動所產生的確切提升度，那麼，在控制和個人化演算法之間使用 10/90 百分比的流量分割會是達成此目標最快和最準確的方式。

   >[!NOTE]
   >
   >在 [!UICONTROL Automated Personalization] 系統會評估每個請求的活動、輸入條件（URL鎖定目標、範本規則和對象目標）。 在舊版中，會對每個工作階段評估輸入條件。

1. 按一下&#x200B;**[!UICONTROL 下一步]**&#x200B;以顯示&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面。
1. 使用下列設定來設定活動，然後按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

   | 設定 | 說明 |
   |--- |--- |
   | [!UICONTROL 名稱] | 為活動命名。為活動指定描述清楚的名稱，讓團隊成員能在 [!UICONTROL 活動] 清單。 請查閱上表以瞭解哪些字元不得用於活動名稱中。 |
   | [!UICONTROL 目標] | (可選) 輸入測試的目標。目標可幫助您記住活動的目的。 |
   | [!UICONTROL 優先順序] | 視您的設定而定，[!UICONTROL 優先順序]的 UI 和選項可能有所不同。您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。<br>如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。<br>若未在 [!UICONTROL 管理] > [!UICONTROL 報表] （預設值），指定優先順序：低、中或高。<br>若要啟用微調優先順序，請按一下 [!UICONTROL 管理] > [!UICONTROL 報表]，然後切換 [!UICONTROL 啟用微調優先順序] 選項至「開啟」位置。<br>如果已啟用此選項，請指定介於 0 和 999 之間的值:<ul><li>0 = 低</li><li>999 = 高</li></ul>對於在舊版 [!DNL Target Standard/Premium] 中建的立活動，低優先順序會轉換為 0，中會轉換為 5，而高則轉換為 10。您可以視需要調整這些值。<br>****&#x200B;注意: 在使用微調優先順序後，在您可以停用此選項之前，必須將所有優先順序設定回 0、5 和 10。 |
   | [!UICONTROL 持續時間] | 設定活動的開始和結束日期。您可以選取 [!UICONTROL 啟動時] 或者，您可以指定特定的日期和時間。 |
   | [!UICONTROL 最佳化目標] | 指定最佳化目標，其中包含兩個參數:<ul><li>要使用活動測量的項目</li><li>活動加入者採取的動作，顯示已達成目標。</li></ul>您可以選取最佳化目標右側的三個點，以選擇為最佳化目標命名 [!UICONTROL 我的主要目標]. [!UICONTROL Automated Personalization] 活動可測量 [!UICONTROL 轉換] 或 [!UICONTROL 收入]. 轉換可透過檢視頁面或檢視 mbox 來達成。也可以追蹤點擊。<br>主要目標也會變成模型量度，供模型系統用來計算體驗的成功。<br>您可以在達到模型目標之後，基於追蹤目的，讓使用者保持在活動中。例如，通常 [!UICONTROL Automated Personalization] 活動可用來改善點按率，並設為模型目標。 不過，務必查看增加的點擊率如何造成最終轉換，使得透過最終的轉換進行追蹤非常必要。<br>您可以提供多個量度上的相依性，並且具有彈性可選擇量度應為達到或未到達時計數才會增加。<br>您必須定義兩個 (或多個) 成功量度，之後才可以讓某個量度相依於另一個量度。<br>「新增相依性」選項允許在已達到另一個成功量度或尚未達到時遞增成功量度。<br>若要新增相依性:<ol><li>新增其他量度後，按一下 **[!UICONTROL 進階設定]** 在右側的三點菜單下 [!UICONTROL 其他目標].</li><li>按一下[!UICONTROL 「報表設定」]區段底部的&#x200B;**[!UICONTROL 「新增相依性」]**&#x200B;選項。</li><li>將需要的量度從左窗格拖曳到右窗格，然後按一下[!UICONTROL 「達到」]以在[!UICONTROL 「達到」]與[!UICONTROL 「未達到」]之間切換設定。</li></ol>您可以在新增相依性之後加以編輯或移除。 |
   | [!UICONTROL 轉換量度] | 根據預設，轉換量度與最佳化目標量度相同。不過，您可以取消勾選[!UICONTROL 與最佳化目標相同]選項，以定義不同的轉換量度。 |
   | [!UICONTROL 其他量度] | 新增您要使用的任何其他報表量度。 您可以新增轉換或收入量度。<br>**注意**: 參與量度也不支援作為其他量度。UI可讓您選取 [!UICONTROL 參與] 量度，但資料在報表中無法正確顯示。 |
   | [!UICONTROL 報表的對象] | 新增對象以在報表中啟用按對象篩選。依預設，報表會顯示所有合格訪客的結果。新增對象以篩選結果，以獲得更明確的訪客子集。<br>**附註**:不同於其他活動類型， [!UICONTROL Automated Personalization] 無法使用 [!UICONTROL Adobe Analytics] 作為其報表來源(A4T)。 |
   | [!UICONTROL 附註] | 輸入關於活動的任何資訊，將該資訊放在手邊對您或其他團隊成員來說很有用。此 [!UICONTROL 附註] 窗格可調整大小。 |

   為量度命名或重新命名時，不允許使用下列字元：

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

按一下 **[!UICONTROL 儲存並關閉]**，活動的 [!UICONTROL 概述] 頁面。 按一下 **預覽體驗** 預覽體驗傳送時的外觀。 此時會出現快顯視窗，您可使用該快顯視窗檢視和共用您網站上AP體驗的連結，以「真正預覽」外部的體驗 [!UICONTROL 目標]的可視化體驗撰寫器(VEC)。 您必須分享來自訊息的連結以分享預覽。按一下連結，然後直接從瀏覽器複製URL將無法運作。 複製連結會使URL包含參數，只有當您從訊息中的連結存取頁面時，才會正確顯示頁面。

如需報表的相關資訊，請參閱 [Automated Personalization報表](/help/main/c-reports/personalization-reports/reports-ap.md).

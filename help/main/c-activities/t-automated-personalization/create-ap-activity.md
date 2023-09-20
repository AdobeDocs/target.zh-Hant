---
keywords: 自動個人化；ap
description: 瞭解如何建立 [!UICONTROL Automated Personalization] (AP)活動在 [!DNL Adobe Target] 使用 [!UICONTROL 視覺化體驗撰寫器].
title: 如何建立 [!UICONTROL Automated Personalization] 活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '1884'
ht-degree: 41%

---

# [!UICONTROL 建立 Automated Personalization 活動]

建立 [!UICONTROL Automated Personalization] (AP)活動在 [!DNL Adobe Target] 使用 [!UICONTROL 視覺化體驗撰寫器] (VEC)。

此 [!UICONTROL Automated Personalization] (AP)中的活動工作流程 [!DNL Target] 與其他活動型別的工作流程不同。

1. 從 [!DNL Target] [!UICONTROL 活動] 清單，按一下 **[!UICONTROL 建立活動]** > **[!UICONTROL Automated Personalization]**.

   ![建立活動: Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. 若要使用 [!UICONTROL 視覺化體驗撰寫器] (VEC)，按一下 **[!UICONTROL 視覺]**.

   若要使用 [!UICONTROL 表單式體驗撰寫器]，選取 [!UICONTROL 表單]. 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和 [!UICONTROL 表單式體驗撰寫器]， [!DNL Target] 提供 [!UICONTROL 單頁應用程式VEC]. 如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/main/c-experiences/experiences.md)。
   >
   >如需有關VEC的疑難排解資訊，請參閱 [疑難排解視覺化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. （視條件而定） [選擇工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. 驗證或輸入活動URL，然後按一下 **[!UICONTROL 建立]**.

   >[!NOTE]
   >
   >[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `http://www.adobe.com`] 和 [!DNL `https://wwww.adobe.com`] 都相符。

   具有指定URL的頁面會在VEC中開啟。

1. 按一下 **[!UICONTROL 名稱]** 欄位並輸入您的活動名稱。

   ![名稱欄位](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

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
   | ;+ | 分號，加號 |
   | ;- | 分號，減號 |
   | ;@ | 分號， At sign |
   | ,= | 逗號，等於 |
   | ,+ | 逗號，加號 |
   | ,- | 逗號，減號 |
   | ,@ | 逗號， At sign |
   | `[`&quot; | 左方括弧，雙引號 |
   | &quot;`]` | 雙引號，右方括弧 |

1. 按照[可視化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)中的說明修改頁面元素。

   您可以從資產管理員一次選取多個影像。這可讓您快速檢視頁面，其中包含為活動設定的每個影像。 您也可以輕鬆在您的選件中編輯文字元素。編輯元素時，該元素上會出現一個橫條，指出您已變更它。

1. 按一下&#x200B;**[!UICONTROL 「管理內容」]**&#x200B;來設定可用的組合。

   ![管理內容選項](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   畫面上方會顯示一個對話方塊，其中含有三個選項： [!UICONTROL 體驗]， [!UICONTROL 選件]、和 [!UICONTROL 排除群組].

   ![管理內容對話方塊](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >雖然您可以在 AP 活動中建立最多 30,000 個體驗，但使用的體驗少於 5,000 個時，活動的執行效能最佳。即使活動已啟用「 」， [!UICONTROL 不允許重複專案] 選項。

   此 [!UICONTROL 體驗] 清單會顯示為活動選取的每個內容片段，及其獲指派的位置。

   您可以將游標移至所需的體驗上，然後按一下「 」，以排除特定的體驗。 [!UICONTROL 排除] 圖示。

   ![排除圖示暫留](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   您可以選取相關體驗的核取方塊，然後按一下 [!UICONTROL 排除] 圖示來顯示這個對話方塊的右上角。

   ![分批排除選項](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   您可以按一下[!UICONTROL 狀態]下拉式清單以篩選此清單檢視，以顯示僅限排除或僅限包含的活動。

1. (依條件) 按一下&#x200B;**[!UICONTROL 「選件」]**，選取內容片段並將它們指派給報表群組，或只允許特定訪客查看特定具有鎖定目標的選件。

   如需有關報表群組的詳細資訊，請參閱 [Automated Personalization中的選件報表群組](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. （視條件而定）按一下 **[!UICONTROL 排除群組]** 以選擇要從活動中排除的任何元素組合。

   ![管理內容對話方塊的排除群組標籤](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   雖然您可以在 AP 測試中建立最多 30,000 個體驗，使用少於 10,000 相異體驗時，演算法的執行效能最佳。即使活動已啟用「 」， [!UICONTROL 不允許重複專案] 選項。

   如果您目前尚未在您的活動中包括任何排除群組，請按一下&#x200B;**「建立排除群組」**。您可以篩選以建立僅顯示您要排除之組合的清單。命名您的排除群組，然後按一下 **儲存**.

   若要編輯現有的排除群組，請將游標暫留在您要編輯的群組上方，然後按一下鉛筆圖示。

1. 完成活動內容的設定時，請按一下&#x200B;**[!UICONTROL 完成]**。

1. 此 **目標定位** 如果您曾使用其他，步驟看起來會很熟悉 [!DNL Target] 活動型別。 您可以在此按一下「 」，選取對象並指定看見控制體驗之訪客的百分比 **[!UICONTROL 自訂分配]** 下拉式清單，然後按一下 **下一個**.

   [!UICONTROL 「自訂分配」]下拉式清單可讓您從下列選項中選擇:

   ![流量分配目標下拉式清單](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL 評估個人化演演算法(50/50)]：** 如果您的目標是要測試演演算法，請在控制與鎖定的演演算法之間使用訪客的50/50百分比分割。 此分割可提供提升度更準確的預估。建議搭配使用「隨機體驗」作為控制。
   * **[!UICONTROL 最大化個人化流量(90/10)]：** 如果您的目標是要建立「一律開啟」的活動，請將10%的訪客放入控制。 此選項可確保有足夠的資料供演演算法隨著時間繼續學習。 這裡的取捨是以更大比例的流量交換個人化，因此在確切的提升度方面較不精確。 無論您的目標為何，此選項都是使用特定體驗作為控制時的建議流量分割。
   * **[!UICONTROL 自訂分配]：** 視需要手動分割百分比。

1. (視條件而定) 從[!UICONTROL 控制]下拉式清單中，[選取要用來作為控制的特定體驗](/help/main/c-activities/t-automated-personalization/experience-as-control.md)，或選取[!UICONTROL 隨機體驗]。

   控制體驗提供比較來判斷自動測試提供了多少提升度。

   [!UICONTROL 自動個人化一律會測量控制群組的效能。]最佳作法是放置至少 10% 的加入者至控制群組。如果您的目標是測試為其提供資料的個人化演演算法是否比沒有個人化更好（例如，隨機提供的控制），則控制和個人化演演算法之間的50/50流量分割是實現此目標的最快和最準確的方式。 如果您想要最大化個人化的流量量，而且不太在意活動正在產生的確切提升度，在控制與個人化演演算法之間分配10/90%的流量是實現此目標的最快速且最準確的方式。

   >[!NOTE]
   >
   >在 [!UICONTROL Automated Personalization] 系統會評估每個要求的活動、登入條件（URL鎖定目標、範本規則和對象目標）。 在舊版中，會對每個工作階段評估輸入條件。

1. 按一下&#x200B;**[!UICONTROL 下一步]**&#x200B;以顯示&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面。
1. 使用下列設定來設定活動，然後按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**。

   | 設定 | 說明 |
   |--- |--- |
   | [!UICONTROL 名稱] | 為活動命名。為活動提供一個描述清楚的名稱，讓團隊成員可以在 [!UICONTROL 活動] 清單。 請查閱上表以瞭解哪些字元不得用於活動名稱中。 |
   | [!UICONTROL 目標] | (可選) 輸入測試的目標。目標可幫助您記住活動的目的。 |
   | [!UICONTROL 優先順序] | 根據您的設定， [!DNL Target] 的UI和選項 [!UICONTROL 優先順序] 視情況而定。 您可以使用舊版設定 [!UICONTROL 低]， [!UICONTROL Medium]，或 [!UICONTROL 高]，或您可啟用0至999的精細優先順序。<P>如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。<P>如果未在中啟用此選項 [!UICONTROL 管理] > [!UICONTROL 報告] （預設值），指定優先順序： [!UICONTROL 低]， [!UICONTROL Medium]，或 [!UICONTROL 高].<P>若要啟用微調優先順序，請按一下 [!UICONTROL 管理] > [!UICONTROL 報告]，然後切換 [!UICONTROL 啟用微調優先順序] 選項切換至「開啟」位置。<P>如果已啟用此選項，請指定從0到999的值：<ul><li>0 = 低</li><li>999 = 高</li></ul>針對在舊版中建立的活動 [!DNL Target Standard/Premium]， [!UICONTROL 低] 優先順序已轉換為0， [!UICONTROL Medium] 優先順序會轉換為5，而 [!UICONTROL 高] 優先順序會轉換為10。 您可以視需要調整這些值。<P>****&#x200B;注意: 在使用微調優先順序後，在您可以停用此選項之前，必須將所有優先順序設定回 0、5 和 10。 |
   | [!UICONTROL 持續時間] | 設定活動的開始和結束日期。您可以選取 [!UICONTROL 啟用時] 或者，您可以指定特定的日期和時間。 |
   | [!UICONTROL 最佳化目標] | 指定最佳化目標，其中包含兩個參數:<ul><li>要使用活動測量的項目</li><li>活動加入者採取的動作，顯示已達成目標。</li></ul>您可以選取右側的三個點，以命名最佳化目標 [!UICONTROL 我的主要目標]. [!UICONTROL Automated Personalization] 活動可測量 [!UICONTROL 轉換] 或 [!UICONTROL 收入]. 可透過檢視頁面或檢視mbox來達到轉換。 也可以追蹤點擊。<P>主要目標也會變成模型系統用來計算體驗成功的模型量度。<P>您可以在達到模型目標之後，基於追蹤目的，讓使用者保持在活動中。例如，通常會 [!UICONTROL Automated Personalization] 活動用於改善點選率，並設為模型目標。 不過，務必查看增加的點擊率如何造成最終轉換，使得透過最終的轉換進行追蹤非常必要。<P>您可以提供多個量度上的相依性，並且具有彈性可選擇量度應為達到或未到達時計數才會增加。<P>您必須定義兩個 (或多個) 成功量度，之後才可以讓某個量度相依於另一個量度。<P>[!UICONTROL 「新增相依性」]選項允許在已達到另一個成功量度或尚未達到時遞增成功量度。<P>若要新增相依性:<ol><li>新增其他量度後，按一下 **[!UICONTROL 進階設定]** 在右側的三個點功能表下 [!UICONTROL 其他目標].</li><li>按一下[!UICONTROL 「報表設定」]區段底部的&#x200B;**[!UICONTROL 「新增相依性」]**&#x200B;選項。</li><li>將需要的量度從左窗格拖曳到右窗格，然後按一下[!UICONTROL 「達到」]以在[!UICONTROL 「達到」]與[!UICONTROL 「未達到」]之間切換設定。。</li></ol>您可以在新增相依性之後加以編輯或移除。 |
   | [!UICONTROL 轉換量度] | 依預設，轉換量度與最佳化目標量度相同。 不過，您可以取消勾選[!UICONTROL 與最佳化目標相同]選項，以定義不同的轉換量度。 |
   | [!UICONTROL 其他量度] | 新增您要使用的任何其他報表量度。 您可以新增轉換或收入量度。<P>**注意**：此 [!UICONTROL 參與] 量度不支援作為其他量度。 此 [!DNL Target] UI可讓您選取 [!UICONTROL 參與] 量度，但資料在報表中無法準確顯示。 |
   | [!UICONTROL 報表的對象] | 新增對象以在報表中啟用按對象篩選。依預設，報表會顯示所有合格訪客的結果。新增對象以篩選結果，以獲得更明確的訪客子集。<P>**注意**：與其他活動型別不同， [!UICONTROL Automated Personalization] 無法使用 [!UICONTROL Adobe Analytics] 作為其報表來源(A4T)。 |
   | [!UICONTROL 附註] | 輸入任何對您或其他專案團隊成員有用的活動相關資訊。 此 [!UICONTROL 附註] 窗格可調整大小。 |

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

在您按一下 **[!UICONTROL 儲存並關閉]**，活動的 [!UICONTROL 概觀] 頁面隨即顯示。 按一下 **預覽體驗** 以預覽您的體驗在傳送時的外觀。 系統會顯示快顯視窗，供您檢視及分享網站上的AP體驗連結，藉此在「 」以外取得體驗的「真正預覽」。 [!UICONTROL Target] [!UICONTROL 視覺化體驗撰寫器] (VEC)。 您必須分享來自訊息的連結以分享預覽。按一下連結然後直接從瀏覽器複製URL無法運作。 複製連結會導致URL包含引數，只有在您從訊息中的連結存取頁面時，才會正確顯示頁面。

如需關於報告的資訊，請參閱 [Automated Personalization報表](/help/main/c-reports/personalization-reports/reports-ap.md).

---
description: 選取在建立自動個人化(AP)或自動Target活動時做為控制項的體驗。
keywords: 體驗；控制；自動個人化；auto-target
seo-description: 選取在Adobe Target中建立自動個人化(AP)或自動Target活動時做為控制項的體驗。
seo-title: 使用特定體驗作為Adobe Target中的控制項
solution: Target、Analytics
title: 使用特定體驗做為控制
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
translation-type: tm+mt
source-git-commit: add895d353e7483dfcbe82f1bca55b277bc65f20

---


# ![PREMIUM](/help/assets/premium.png) 選取自動個人化或自動目標活動的控制權

You can select a randomly served experience or a specific experience to be used as control while creating an [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) or [Auto-Target](/help/c-activities/auto-target-to-optimize.md) (AT) activity.

此功能可讓您根據活動中設定的流量分配百分比，將控制流量路由路由至相關體驗。然後，您可以針對控制流量來評估個人化流量的績效報告，以控制該控制項。

在AP和AT活動中設定控制項的選項與其他活動類型稍有不同。在手動A/B測試中，您可以變更報告顯示為您的控制項，並根據該控制體驗的轉換率來計算提升度。您可以輕鬆地讓這項變更變得易如反掌，因為流量會隨機提供給您活動中每個體驗的隨機服務，無論最初設定的是甚麼。換言之，選取控制項並不影響流量的提供方式。在AP和AT活動中，您決定要選擇哪些項目會影響訪客流量的提供方式。因此，您需要更仔細地思考您的決定。

您的AP和AT活動中有兩個可供您控制的選項：隨機提供體驗或特定體驗。

* **隨機提供**：對於隨機控制，控制流量百分比會隨機提供活動中所有體驗，而不考慮訪客的描述檔。您可以考慮控制權，以協助回答以下問題：「我只隨機向訪客提供體驗(或優惠)給訪客，而不考慮他們的個人檔案，那該體驗的轉換率為何？」控制項就像AI活動中的A/B測試。在分析活動結果時，針對每個體驗或選件提供非個人化轉換率的資訊可能會有幫助。

* **特定體驗**：特定的體驗控制可讓您比較Target個人化模型提供給特定行銷人員定義體驗的流量(例如預設首頁)。使用此選項，控制流量百分比只會隨機支援該一個體驗。

## 指定特定體驗作為控制

1. While creating an [AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) or [AT activity](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure the experiences as desired.
1. On the [!UICONTROL Targeting] page (step 2 of the three-part guided workflow), select the desired experience as the control.
1. 指定控制體驗和其他體驗的所需流量分配。

   針對特定體驗控制，建議使用10%到30%。

1. Continue with the [!UICONTROL Goals &amp; Settings] page.

## 已知限制和考量事項

使用特定體驗做為控制時，請牢記下列幾點：

* 不建議變更已即時活動中的控制體驗。選取的最新控制體驗會在報告中命名(即使舊報表根據另一個體驗)。
* 不建議刪除控制體驗。
* 將大量的新選件/體驗新增至具有特定體驗的即時活動，以獲得控制權。
* 在AP活動中，包括定位在控制體驗上，可進一步constra，讓誰看不到體驗。
* In AP activities, lift and confidence information is *NOT* available in the offer-level report if a specific experience is selected. 提升度和可信度資訊適用於AP活動的「目標」與「控制」流量層級。如果選取「隨機」做為控制項，則可使用提升度和可信度資訊。這種差異是因為比較特定體驗的轉換率與選件轉換率的差異是因為單位差異。無論選取何種控制類型，AT活動中可用的資訊都是相同的。
* 因為當您選取控制項時，所有控制流量都會進入單一體驗或選件集合(相較於隨機，則控制流量金額會依活動的體驗或選件數分割)，而您通常不需要太多流量流向控制項。10%是開始的好地方。
* 如果您對具有特定體驗的即時活動執行下列其中一項動作，控制項會自動重設為隨機提供的體驗(而非先前選取的特定體驗)：

   * 刪除體驗
   * 移除位置或選件(僅限AP)
   * 透過移除重復選件或透過排除群組(僅限AP)排除體驗


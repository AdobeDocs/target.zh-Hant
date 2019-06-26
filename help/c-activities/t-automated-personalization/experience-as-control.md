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


# ![PREMIUM](/help/assets/premium.png) 使用特定體驗作為控制

You can select an experience to be used as control while creating an [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) or [Auto-Target](/help/c-activities/auto-target-to-optimize.md) (AT) activity.

此功能可讓您根據活動中設定的流量分配百分比，將整個控制流量路由至特定體驗。然後，您可以評估個人化流量的績效報告，以控制該一個體驗的流量。

另外也提供隨機提供體驗的控制選項。

透過使用特定體驗做為控制，您的報表可協助回答「執行AP/AT活動比以前執行的動作更好？」的問題。AP/AT活動的優點在於，您可以建立更多可能對所有使用者都沒有意義的選項，但對正確的使用者而言可能是強大的。但這表示比較我們的演算法並不公平；您絕對不會對網站上的所有訪客執行所有選項。

## 指定特定體驗作為控制

1. While creating an [AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) or [AT activity](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure the experiences as desired.
1. On the [!UICONTROL Targeting] page (step 2 of the three-part guided workflow), select the desired experience as the control.
1. 指定控制體驗和其他體驗的所需流量分配。
1. Continue with the [!UICONTROL Goals &amp; Settings] page.

## 已知限制

下列是使用特定體驗做為控制的已知限制：

* 不建議變更已即時活動中的控制體驗。選取的最新控制體驗會在報告中命名(即使舊報表根據另一個體驗)。
* 不建議刪除控制體驗。
* 在AP活動中，包括定位在控制體驗中，並不建議進一步constra可查看該體驗。
* In AP activities, lift and confidence information is *NOT* available in the offer-level report if a specific experience is selected. 如果選取「隨機」做為控制項，則可使用提升度和可信度資訊。

   Lift and confidence information *is* available at the overall &quot;targeted&quot; vs. &quot;control&quot; traffic level for the activity. 這種差異是因為比較特定體驗的轉換率與選件轉換率的差異是因為單位差異。

## 疑難排解

如果出現問題，請考慮下列疑難排解提示：

* 因為當您選取控制項時，所有控制流量都會進入單一體驗或選件集合(相較於隨機，則控制流量金額會依活動的體驗/選件數分割)，您通常不需要太多流量流向控制項。10%是開始的好地方。
* 如果您對即時活動執行下列其中一項作業，控制項會自動重設為隨機提供的體驗(而非先前選取的特定體驗)：

   * 刪除體驗
   * 移除位置或選件(僅限AP)
   * 透過移除重復選件或透過排除群組(僅限AP)排除體驗

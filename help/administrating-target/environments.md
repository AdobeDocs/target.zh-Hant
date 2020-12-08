---
keywords: environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist;blacklist;blocklist;allowlist
description: 在Adobe Target中組織您的網站和前制環境，以方便管理和分開報告。
title: 環境
feature: hosts and environments
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 65%

---


# 環境

組織您的網站和生產前環境，適用於簡易管理和分開的報表。

主機會整合至環境以便輕鬆管理。例如，您可能有許多主機聚集在兩個或三個環境中。The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. 您可以新增環境並重新命名環境 (如需要)。

One environment, the default environment, is pre-named [!UICONTROL Production]. 即使重新命名此預設環境，亦無法刪除此環境。[!DNL Target] 假設這是您提供最終批准活動與測試的地方。

When a [!DNL Target] request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. The [!UICONTROL Production] environment cannot have its settings changed, so unknown or new sites are guaranteed to see only content that is active and ready. 主機管理亦可讓您在啟動活動之前，輕鬆針對測試、預備和開發環境確保新活動和內容的品質。

若要管理環境，請按一 **[!UICONTROL 下「管理]** > **[!UICONTROL 環境]**」。

![環境清單](/help/administrating-target/assets/environments.png)

## 添加環境 {#section_32097D0993724DF3A202D164D3F18674}

1. 在「環境 [!UICONTROL 」清單] ，按一下「 **[!UICONTROL 添加環境」]**。
1. 為環境指定描述性名稱。
1. 為環境指定所需的使用中模式: [!UICONTROL 使用中的活動]或[!UICONTROL 使用中或非使用中的活動]。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## Set the default environment for reporting {#section_4F8539B07C0C45E886E8525C344D5FB0}

您可以選取想要的環境作為所有活動報表的預設環境。

If you use [!UICONTROL Production] as your default, all unknown hosts automatically are added here and report data from there is included in the default report view. 反之，建立「全新」環境可確保只包含您的核心網站/網域。

若要設定報表的預設環境:

1. 從「環 [!UICONTROL 境] 」清單中，按一下「星形」圖示

>[!NOTE]
>
>[!DNL Recommendations]如果主機會切換主機群組， 的使用者必須重建其行為資料庫和產品資料庫。

## Change the name of an environment {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. 在「環境 [!UICONTROL 」(Environment] )清單中，按一下「 **[!UICONTROL 編輯]** 」(Edit)表徵圖。
1. 變更環境名稱。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## Delete an environment {#section_737F8869612047868D03FC755B1223D3}

您可以刪除不再需要的環境。

1. 從「環境 [!UICONTROL 」(Environment] )清單中，單 **[!UICONTROL 擊「刪除]** 」(Delete)表徵圖。
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>You cannot delete the [!UICONTROL Production] environment, but you can rename it.

## 建議: 按環境 (主機群組) 篩選集合和排除項目

![Premium 徽章](/help/assets/premium.png)

您可以預覽所選環境 (主機群組) 的建議集合和排除項目。

>[!NOTE]
>
>Recommendations activities are available as part of the [!DNL Target] Premium solution. 在沒有 [!DNL Target] Premium 授權的 [!DNL Target] Standard 中無法使用。

您可以使用環境來區隔目錄中的可用項目，以供不同用途使用。 For example, you can use host groups for [!UICONTROL Development] and [!UICONTROL Production] environments, different brands, or different geographies. 依照預設，「目錄搜尋」、「集合」和「排除項目」中的預覽結果是根據預設主機群組所產生。(您也可以使用「環境」篩選器，選取不同的主機群組來預覽結果。)依照預設，除非在建立或更新項目時指定環境 ID，否則新增的項目可在所有主機群組中使用。提供的建議取決於要求中指定的主機群組。

如果沒有看見您的產品，請確定您使用正確的主機群組。例如，假設您將建議設定為使用測試環境，並將主機群組設為「測試」，則可能需要在測試環境中重建集合，才會顯示產品。若要查看每個環境中可用的產品，請對每個環境使用「目錄搜尋」。您也可以針對所選的環境 (主機群組)，預覽 Recommendations 集合和排除項目的內容。

>[!NOTE]
>在變更選取的環境後，您必須按一下「搜尋」來更新傳回的結果。

The [!UICONTROL Environment] filter is available from the following places in the Target UI:

* 「目錄搜尋」([!UICONTROL 「建議 > 目錄搜尋」])
* 「建立集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 新建」])
* 「更新集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 編輯」])
* 「建立排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 新建」])
* 「更新排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 編輯」])
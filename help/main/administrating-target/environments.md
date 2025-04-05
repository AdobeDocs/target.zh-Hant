---
keywords: 環境；疑難排解；最佳實務；ubox；重新導向；重新導向；白名單；黑名單；封鎖清單；允許清單
description: 瞭解如何使用Adobe [!DNL Target] 中的環境來組織您的網站和生產前環境，以便輕鬆管理和分隔報表。
title: 什麼是環境？如何使用環境？
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 47%

---

# 環境

組織您的網站和生產前環境，適用於簡易管理和分開的報表。

主機會整合至環境以便輕鬆管理。例如，您可能有許多主機聚集在兩個或三個環境中。預設環境包括[!UICONTROL Production]、[!UICONTROL Staging]和[!UICONTROL Development]。 您可以新增環境並重新命名環境 (如需要)。

一個環境（預設環境）已預先命名為[!UICONTROL Production]。 即使重新命名此預設環境，亦無法刪除此環境。[!DNL Target] 假設這是您提供最終批准活動與測試的地方。

從新網站或網域收到[!DNL Target]要求時，這些新網域一律會出現在[!UICONTROL Production]環境中。 [!UICONTROL Production]環境無法變更其設定，因此可保證未知或新網站只會看到作用中且準備就緒的內容。 主機管理亦可讓您在啟動活動之前，輕鬆針對測試、預備和開發環境確保新活動和內容的品質。

{{permissions-update}}

若要管理環境，請按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Environments]**。

## 新增環境 {#section_32097D0993724DF3A202D164D3F18674}

1. 從[!UICONTROL Environments]清單，按一下&#x200B;**[!UICONTROL Add Environment]**。
1. 為環境指定描述性名稱。
1. 指定環境所需的作用中模式： [!UICONTROL Active Activities]或[!UICONTROL Active and Inactive Activities]。

   如果您指定[!UICONTROL Active and Inactive Activities]，則來自此環境的主機也會顯示非使用中活動。

1. 按一下 **[!UICONTROL Save]**。

## 設定報告的預設環境 {#section_4F8539B07C0C45E886E8525C344D5FB0}

您可以選取想要的環境作為所有活動報表的預設環境。

如果您使用[!UICONTROL Production]作為預設值，所有未知主機會自動新增在這裡，而來自那裡的報告資料會包含在預設的報告檢視中。 反之，建立「全新」環境可確保只包含您的核心網站/網域。

若要設定報表的預設環境:

1. 從[!UICONTROL Environments]清單中，按一下星形圖示

>[!NOTE]
>
>[!DNL Recommendations]如果主機會切換主機群組， 的使用者必須重建其行為資料庫和產品資料庫。
>
>如果您在 [!DNL Adobe Experience Platform] 資料流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#target){target=_blank}中指定[預設環境，此設定會覆寫[!DNL Target]中的設定。

## 變更環境的名稱 {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. 從[!UICONTROL Environment]清單中，按一下&#x200B;**[!UICONTROL Edit]**&#x200B;圖示。
1. 變更環境名稱。
1. 按一下 **[!UICONTROL Save]**。

## 刪除環境 {#section_737F8869612047868D03FC755B1223D3}

您可以刪除不再需要的環境。

1. 從[!UICONTROL Environment]清單中，按一下&#x200B;**[!UICONTROL Delete]**&#x200B;圖示。
1. 按一下&#x200B;**[!UICONTROL Delete]**&#x200B;以確認刪除。

>[!NOTE]
>
>您無法刪除[!UICONTROL Production]環境，但您可以重新命名。

## [!BADGE 進階版]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="檢視Target Premium包含的內容。"}

您可以預覽所選環境 (主機群組) 的建議集合和排除項目。

{{premium-note}}

環境可用來將目錄中可用專案區分為不同用途。 例如，您可以將主機群組用於[!UICONTROL Development]和[!UICONTROL Production]環境、不同品牌或不同地理位置。 依照預設，「目錄搜尋」、「集合」和「排除項目」中的預覽結果是根據預設主機群組所產生。(您也可以使用「環境」(Environment)篩選條件，選取不同的主機群組來預覽結果。) 依預設，除非在建立或更新專案時指定環境ID，否則新加入的專案可在所有主機群組中使用。

>[!NOTE]
>
>提供的建議取決於要求中指定的主機群組或環境ID。


如果沒有看見您的產品，請確定您使用正確的主機群組。例如，假設您將建議設定為使用測試環境，並將主機群組設為「測試」，則可能需要在測試環境中重建集合，才會顯示產品。若要查看每個環境中可用的產品，請對每個環境使用「目錄搜尋」。您也可以針對所選的環境 (主機群組)，預覽推薦集合和排除項目的內容。

>[!NOTE]
>在變更選取的環境後，您必須按一下「搜尋」來更新傳回的結果。

[!UICONTROL Environment]篩選器可從Target UI中的下列位置取得：

* 目錄搜尋([!UICONTROL Recommendations > Catalog Search])
* 建立集合對話方塊([!UICONTROL Recommendations > Collections > Create New])
* 更新集合對話方塊([!UICONTROL Recommendations > Collections > Edit])
* 建立排除專案對話方塊([!UICONTROL Recommendations > Exclusions > Create New])
* 更新排除專案對話方塊([!UICONTROL Recommendations > Exclusions > Edit])

---
keywords: environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist;blacklist;blocklist;allowlist
description: 在Adobe Target中組織您的網站和前制環境，以方便管理和分開報告。
title: 環境
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 9b57d5554884b06d278c3baef3b2c1d5f37bdeb5
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 65%

---


# 環境

組織您的網站和生產前環境，適用於簡易管理和分開的報表。

主機會整合至環境以便輕鬆管理。例如，您可能有許多主機聚集在兩個或三個環境中。預設環境包括[!UICONTROL Production]、[!UICONTROL Staging]和[!UICONTROL Development]。 您可以新增環境並重新命名環境 (如需要)。

一個環境（預設環境）預命名為[!UICONTROL Production]。 即使重新命名此預設環境，亦無法刪除此環境。[!DNL Target] 假設這是您提供最終批准活動與測試的地方。

當從新網站或網域收到[!DNL Target]請求時，這些新網域一律會出現在[!UICONTROL Production]環境中。 [!UICONTROL Production]環境無法更改其設定，因此，未知或新站點保證只看到活動且就緒的內容。 主機管理亦可讓您在啟動活動之前，輕鬆針對測試、預備和開發環境確保新活動和內容的品質。

要管理環境，請按一下「**[!UICONTROL 管理]** > **[!UICONTROL 環境]**」。

![環境清單](/help/administrating-target/assets/environments.png)

## 添加環境{#section_32097D0993724DF3A202D164D3F18674}

1. 在[!UICONTROL Environments]清單中，按一下&#x200B;**[!UICONTROL Add Environment]**。
1. 為環境指定描述性名稱。
1. 為環境指定所需的使用中模式: [!UICONTROL 使用中的活動]或[!UICONTROL 使用中或非使用中的活動]。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 設定報告{#section_4F8539B07C0C45E886E8525C344D5FB0}的預設環境

您可以選取想要的環境作為所有活動報表的預設環境。

如果您使用[!UICONTROL Production]做為預設值，則此處會自動新增所有未知主機，而預設報表檢視中會包含來自該處的報表資料。 反之，建立「全新」環境可確保只包含您的核心網站/網域。

若要設定報表的預設環境:

1. 在[!UICONTROL Environments]清單中，按一下「星形」圖示

>[!NOTE]
>
>[!DNL Recommendations]如果主機會切換主機群組， 的使用者必須重建其行為資料庫和產品資料庫。

## 更改環境{#section_9F5F94285F8E495E9CE69810CE94CA08}的名稱

1. 在[!UICONTROL Environment]清單中，按一下&#x200B;**[!UICONTROL Edit]**&#x200B;表徵圖。
1. 變更環境名稱。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 刪除環境{#section_737F8869612047868D03FC755B1223D3}

您可以刪除不再需要的環境。

1. 在[!UICONTROL Environment]清單中，按一下&#x200B;**[!UICONTROL Delete]**&#x200B;表徵圖。
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>您無法刪除[!UICONTROL Production]環境，但可以對其進行更名。

## 建議: 按環境 (主機群組) 篩選集合和排除項目

![Premium 徽章](/help/assets/premium.png)

您可以預覽所選環境 (主機群組) 的建議集合和排除項目。

>[!NOTE]
>
>Recommendations活動是[!DNL Target] Premium解決方案的一部分。 在沒有 [!DNL Target] Premium 授權的 [!DNL Target] Standard 中無法使用。

您可以使用環境來區隔目錄中的可用項目，以供不同用途使用。 例如，您可以針對[!UICONTROL Development]和[!UICONTROL Production]環境、不同品牌或不同地區使用主機群組。 依照預設，「目錄搜尋」、「集合」和「排除項目」中的預覽結果是根據預設主機群組所產生。(您也可以使用「環境」篩選器，選取不同的主機群組來預覽結果。)依照預設，除非在建立或更新項目時指定環境 ID，否則新增的項目可在所有主機群組中使用。提供的建議取決於要求中指定的主機群組。

如果沒有看見您的產品，請確定您使用正確的主機群組。例如，假設您將建議設定為使用測試環境，並將主機群組設為「測試」，則可能需要在測試環境中重建集合，才會顯示產品。若要查看每個環境中可用的產品，請對每個環境使用「目錄搜尋」。您也可以針對所選的環境 (主機群組)，預覽 Recommendations 集合和排除項目的內容。

>[!NOTE]
>在變更選取的環境後，您必須按一下「搜尋」來更新傳回的結果。

[!UICONTROL Environment]篩選器可從Target UI的下列位置使用：

* 「目錄搜尋」([!UICONTROL 「建議 > 目錄搜尋」])
* 「建立集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 新建」])
* 「更新集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 編輯」])
* 「建立排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 新建」])
* 「更新排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 編輯」])
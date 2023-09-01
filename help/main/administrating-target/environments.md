---
keywords: 環境；疑難排解；最佳實務；ubox；重新導向；重新導向；白名單；黑名單；封鎖清單；允許清單
description: 瞭解如何在Adobe中使用環境 [!DNL Target] 組織您的網站和生產前環境，以方便管理和分隔報表。
title: 什麼是環境？如何使用環境？
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
source-git-commit: 43291a102dee4cf03a3a427a4f29fe75d2c11221
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 56%

---

# 環境

組織您的網站和生產前環境，適用於簡易管理和分開的報表。

主機會整合至環境以便輕鬆管理。例如，您可能有許多主機聚集在兩個或三個環境中。預設環境包括 [!UICONTROL 生產]， [!UICONTROL 分段]、和 [!UICONTROL 開發]. 您可以新增環境並重新命名環境 (如需要)。

預設環境已預先命名 [!UICONTROL 生產]. 即使重新命名此預設環境，亦無法刪除此環境。[!DNL Target] 假設這是您提供最終批准活動與測試的地方。

當 [!DNL Target] 從新網站或網域收到要求，這些新網域一律會出現在 [!UICONTROL 生產] 環境。 此 [!UICONTROL 生產] 環境無法變更其設定，因此未知或新網站保證只會看到作用中且準備就緒的內容。 主機管理亦可讓您在啟動活動之前，輕鬆針對測試、預備和開發環境確保新活動和內容的品質。

若要管理環境，請按一下 **[!UICONTROL 管理]** > **[!UICONTROL 環境]**.

![環境清單](/help/main/administrating-target/assets/environments.png)

## 新增環境 {#section_32097D0993724DF3A202D164D3F18674}

1. 從 [!UICONTROL 環境] 清單，按一下 **[!UICONTROL 新增環境]**.
1. 為環境指定描述性名稱。
1. 為環境指定所需的使用中模式: [!UICONTROL 使用中的活動]或[!UICONTROL 使用中或非使用中的活動]。

   如果您指定 [!UICONTROL 使用中或非使用中的活動]，此環境中的主機也會顯示非使用中活動。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 設定報告的預設環境 {#section_4F8539B07C0C45E886E8525C344D5FB0}

您可以選取想要的環境作為所有活動報表的預設環境。

如果您使用 [!UICONTROL 生產] 所有未知主機都會自動新增至此處，且報表資料會從此處納入預設報表檢視中（預設）。 反之，建立「全新」環境可確保只包含您的核心網站/網域。

若要設定報表的預設環境:

1. 從 [!UICONTROL 環境] 清單，按一下星號圖示

>[!NOTE]
>
>[!DNL Recommendations]如果主機會切換主機群組， 的使用者必須重建其行為資料庫和產品資料庫。
>
>如果您指定 [Adobe Experience Platform資料流中的預設環境](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#target){target=_blank}，此環境會覆寫中的設定 [!DNL Target Recommendations].

## 變更環境的名稱 {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. 從 [!UICONTROL 環境] 清單中，按一下 **[!UICONTROL 編輯]** 圖示。
1. 變更環境名稱。
1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 刪除環境 {#section_737F8869612047868D03FC755B1223D3}

您可以刪除不再需要的環境。

1. 從 [!UICONTROL 環境] 清單中，按一下 **[!UICONTROL 刪除]** 圖示。
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>您無法刪除 [!UICONTROL 生產] 環境，但您可以重新命名。

## [!BADGE Premium]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="檢視Target Premium包含的內容。"}

您可以預覽所選環境 (主機群組) 的建議集合和排除項目。

{{premium-note}}

環境可用來將目錄中可用專案區分為不同用途。 例如，您可以將主機群組用於 [!UICONTROL 開發] 和 [!UICONTROL 生產] 環境、不同品牌或不同地理位置。 依照預設，「目錄搜尋」、「集合」和「排除項目」中的預覽結果是根據預設主機群組所產生。(您也可以使用「環境」篩選器，選取不同的主機群組來預覽結果。)依照預設，除非在建立或更新項目時指定環境 ID，否則新增的項目可在所有主機群組中使用。

>[!NOTE]
>
>提供的建議取決於要求中指定的主機群組或環境ID。


如果沒有看見您的產品，請確定您使用正確的主機群組。例如，假設您將建議設定為使用測試環境，並將主機群組設為「測試」，則可能需要在測試環境中重建集合，才會顯示產品。若要查看每個環境中可用的產品，請對每個環境使用「目錄搜尋」。您也可以針對所選的環境 (主機群組)，預覽 Recommendations 集合和排除項目的內容。

>[!NOTE]
>在變更選取的環境後，您必須按一下「搜尋」來更新傳回的結果。

此 [!UICONTROL 環境] 篩選器可在Target UI中的以下位置使用：

* 「目錄搜尋」([!UICONTROL 「建議 > 目錄搜尋」])
* 「建立集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 新建」])
* 「更新集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 編輯」])
* 「建立排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 新建」])
* 「更新排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 編輯」])

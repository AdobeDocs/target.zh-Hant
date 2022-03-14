---
keywords: 環境；故障排除；最佳實踐；ubox;redirects;whitelist；黑名單；黑名單；黑名單；允許清單
description: 瞭解如何在Adobe中使用環境 [!DNL Target] 組織您的站點和生產前環境，以便於管理和分開報告。
title: 什麼是環境以及如何使用它們？
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 60%

---

# 環境

組織您的網站和生產前環境，適用於簡易管理和分開的報表。

主機會整合至環境以便輕鬆管理。例如，您可能有許多主機聚集在兩個或三個環境中。預設環境包括 [!UICONTROL 生產]。 [!UICONTROL 暫存], [!UICONTROL 開發]。 您可以新增環境並重新命名環境 (如需要)。

一個環境（預設環境）是預命名的 [!UICONTROL 生產]。 即使重新命名此預設環境，亦無法刪除此環境。[!DNL Target] 假設這是您提供最終批准活動與測試的地方。

當 [!DNL Target] 從新網站或域接收請求，這些新域始終顯示在 [!UICONTROL 生產] 環境。 的 [!UICONTROL 生產] 環境不能更改其設定，因此，確保未知或新站點只能查看活動且準備就緒的內容。 主機管理亦可讓您在啟動活動之前，輕鬆針對測試、預備和開發環境確保新活動和內容的品質。

要管理環境，請按一下 **[!UICONTROL 管理]** > **[!UICONTROL 環境]**。

![環境清單](/help/main/administrating-target/assets/environments.png)

## 添加環境 {#section_32097D0993724DF3A202D164D3F18674}

1. 從 [!UICONTROL 環境] 清單，按一下 **[!UICONTROL 添加環境]**。
1. 為環境指定描述性名稱。
1. 為環境指定所需的使用中模式: [!UICONTROL 使用中的活動]或[!UICONTROL 使用中或非使用中的活動]。

   如果指定 [!UICONTROL 活動和非活動活動]，此環境中的主機也顯示非活動活動。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 設定報告的預設環境 {#section_4F8539B07C0C45E886E8525C344D5FB0}

您可以選取想要的環境作為所有活動報表的預設環境。

如果您使用 [!UICONTROL 生產] 預設情況下，所有未知主機將自動添加到此處，並且來自此處的報告資料包含在預設報告視圖中。 反之，建立「全新」環境可確保只包含您的核心網站/網域。

若要設定報表的預設環境:

1. 從 [!UICONTROL 環境] 清單中，按一下「星號」表徵圖

>[!NOTE]
>
>[!DNL Recommendations]如果主機會切換主機群組， 的使用者必須重建其行為資料庫和產品資料庫。

## 更改環境的名稱 {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. 從 [!UICONTROL 環境] 清單，按一下 **[!UICONTROL 編輯]** 表徵圖
1. 變更環境名稱。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 刪除環境 {#section_737F8869612047868D03FC755B1223D3}

您可以刪除不再需要的環境。

1. 從 [!UICONTROL 環境] 清單，按一下 **[!UICONTROL 刪除]** 表徵圖
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>無法刪除 [!UICONTROL 生產] 環境，但可以更名它。

## 建議: 按環境 (主機群組) 篩選集合和排除項目

![Premium 徽章](/help/main/assets/premium.png)

您可以預覽所選環境 (主機群組) 的建議集合和排除項目。

{{premium-note}}

環境可用於將目錄中的可用項目分開，以供不同用途。 例如，您可以使用 [!UICONTROL 開發] 和 [!UICONTROL 生產] 環境、不同品牌或不同的地理區域。 依照預設，「目錄搜尋」、「集合」和「排除項目」中的預覽結果是根據預設主機群組所產生。(您也可以使用「環境」篩選器，選取不同的主機群組來預覽結果。)依照預設，除非在建立或更新項目時指定環境 ID，否則新增的項目可在所有主機群組中使用。

>[!NOTE]
>
>提供的建議取決於請求中指定的主機組或環境ID。


如果沒有看見您的產品，請確定您使用正確的主機群組。例如，假設您將建議設定為使用測試環境，並將主機群組設為「測試」，則可能需要在測試環境中重建集合，才會顯示產品。若要查看每個環境中可用的產品，請對每個環境使用「目錄搜尋」。您也可以針對所選的環境 (主機群組)，預覽 Recommendations 集合和排除項目的內容。

>[!NOTE]
>在變更選取的環境後，您必須按一下「搜尋」來更新傳回的結果。

的 [!UICONTROL 環境] 篩選器可從目標UI中的以下位置獲得：

* 「目錄搜尋」([!UICONTROL 「建議 > 目錄搜尋」])
* 「建立集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 新建」])
* 「更新集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 編輯」])
* 「建立排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 新建」])
* 「更新排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 編輯」])

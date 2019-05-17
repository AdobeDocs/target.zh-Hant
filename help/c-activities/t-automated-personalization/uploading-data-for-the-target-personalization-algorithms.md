---
description: 建置個人化模型時，離線資料 (例如 CRM 資訊或客戶流失傾向分數) 可能具有重大價值。
seo-description: 建置個人化模型時，離線資料 (例如 CRM 資訊或客戶流失傾向分數) 可能具有重大價值。
seo-title: 上傳用於 Target 個人化演算法的資料
solution: Target
title: 上傳用於 Target 個人化演算法的資料
topic: Premium
uuid: eb0938b9-7f35-4bb5-ac4b-260b2144db5b
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 上傳用於 Target 個人化演算法的資料{#upload-data-for-target-s-personalization-algorithms}

建置個人化模型時，離線資料 (例如 CRM 資訊或客戶流失傾向分數) 可能具有重大價值。

有數種方式可以在自動個人化 (AP) 和自動鎖定目標個人化演算法中輸入資料。除了方法中 [要將資料取得Target](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)的方法外，我們的演算法也使用Experience Cloud共用觀眾(Adobe Analytics、觀眾管理)和活動報告對象。

如需自動個人化和自動鎖定目標個人化演算法自動收集和使用之資料的相關資訊，請參閱[自動個人化資料收集](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)。

## 最佳實務 {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

以下清單介紹了為 Target 個人化演算法上傳資料的最佳作法:

* Target 的個人化演算法可得到高品質資料越多，AP 和自動鎖定目標活動中產生的模型品質就越好。
* 限制使用多個提供相同用途的設定檔指令碼或屬性。
* 如果不需要，請勿傳遞唯一的 ID，例如工作階段 ID。
* 複查 Target 自動收集的資料 ([Target 個人化演算法的資料收集](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058))，如此一來，您便不會傳送重複的資訊。例如，Target 會使用 IP 位址來判斷訪客的郵遞區號。不必以單獨的變數傳遞此資訊。
* 請勿在相同屬性/變數中傳遞多個值。如果連接多個變數，Target 的個人化演算法會將每個字串視為唯一值，降低個人化資訊的價值。
* 使用易記且有意義的命名慣例讓您的[個人化前瞻分析報表](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)更清晰易懂。


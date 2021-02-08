---
keywords: 隱私權；ip位址；地域劃分；退出；退出；退出；資料隱私；政府法規；gdpr;cpa
description: 瞭解Adobe Target如何遵守適用的資料隱私法，包括IP位址的收集和處理，以及選擇退出指示。
title: Target如何處理隱私權問題？
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 73%

---


# 隱私權

[!DNL Adobe Target] 已啟用程序和設定，允許您使用 遵守適用的資料隱私權法律。[!DNL Target]

## IP位址集{#section_91BDB8105EBF4B85B7B8B8A14675AC85}

您網站訪客的 IP 位址將傳輸到 Adobe 資料處理中心 (DPC)。視訪客的網路設定而定，此 IP 位址不一定代表訪客電腦的 IP 位址。例如，該 IP 位址可能是網路位址轉譯 (NAT) 防火牆、HTTP Proxy 或內部閘道的外部 IP 位址。Target 不會儲存使用者的任何 IP 位址或任何個人身分識別資訊 (PII)。IP 位址僅在工作階段期間由 Target 使用 (記憶體內部，永不保留)。

## 取代IP位址的最後八位元{#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe 已開發新的「設計隱私權」設定，可由 Adobe 客戶服務為 Adobe Target 啟用。啟用此設定時，當 Adobe 收集到 IP 位址時，就會立即隱藏 IP 位址的最後八位元 (最後一部分)。在對 IP 位址進行任何處理前 (包括選用的 IP 位址地理查閱)，就會執行這種匿名方式。

啟用此功能時，IP 位址的匿名性已足夠，不再能識別為個人資訊。因此，Adobe Target 的使用便能遵守不允許收集個人資訊之國家/地區的資料隱私權法律。IP 位址模糊化可能會顯著影響城市層級資訊的取得。地區和國家層級資訊則只會受到輕微影響。

可使用下列設定:

* 無模糊化：Target不會隱藏IP位址的任何部分。
* 最後八位數字：Target會隱藏IP位址的最後八位元。
* 完整IP:Target會隱藏整個IP位址。

Target會接收完整的IP位址，並依指定將其模糊化（若設為「最後八位數」或「完整的IP」）。 然後，Target會在作業期間將模糊化的IP位址保留在記憶體中。

>[!NOTE]
>
>[請連絡Adobe Client ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) Care，以判斷您目前使用的設定或啟用IP模糊化功能。

## 地域劃分 {#section_BB69F96559BD44BDA4177537C4A5345A}

如果您啟用取代 IP 位址的最後八位元，可使用 Adobe Target 中的報表來分析 IP 位址的其餘值。如果 IP 位址的最後八位元未被模糊化，則可在 Adobe Target 中分析完整 IP 位址。您可以使用 GeoSegmentation 功能，依地理區域來安排訪客位置。地域劃分資料的詳細程度只到城市層級或郵遞區號層級，不到個人層級。

如果 IP 位址完全模糊，則無法使用 GeoSegmentation 和地理位置定位。

## 退出連結{#section_E7A62B7B99C94B3A806CB262D16E27FC}

您可以在您的網站中新增選擇退出連結，讓訪客能夠選擇退出所有 計數及內容傳遞。

1. 將下列連結新增至您的網站:

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`
1. 將 `clientcode` 文字取代為您的用戶端代碼，然後新增要連結至選擇退出 URL 的文字或影像。

訪客只要按一下此連結，就不會包含在任何從該訪客的瀏覽作業呼叫的 mbox 中，直到訪客刪除本身的 Cookie 或事隔滿兩年 (以先發生者為準) 為止。其原理是在 `disableClient` 中為訪客設定一個名稱為 `clientcode.tt.omtrdc.net` 的 Cookie。

即使您使用第一方 Cookie 實作，所提供的選擇退出還是透過第三方 Cookie 來設定。若客戶僅使用第一方 Cookie，Target 會檢查是否有設定選擇退出 Cookie。

## 隱私權與資料保護規範

請參閱[隱私權與資料保護法規](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)，以取得歐盟通用資料保護法規(GDPR)、加州消費者隱私法(CCPA)和其他國際隱私權要求的相關資訊，以及這些規定對您的組織和Adobe Target有何影響。

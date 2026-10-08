---
title: 資料可用性和同步時間
description: 瞭解資料變更在[!DNL Journey Optimizer B2B Edition]歷程中出現的速度，以及哪些時間表正常。
feature: Journeys, Data Management
role: User
autotag-review: '2026-10-08T18:36:33.252Z'
TQID: 'https://experienceleague.adobe.com/PA1IeRHnGWHmBtDpffzveoWIHOn99-Ctt4Y0OQb7CwE'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
  - id: b27e5950-9033-45ac-9f86-eb22e567f615
    internal-label: Marketo Engage
feature_v2:
  - id: 095e8119-1425-57eb-9d8c-9e684f2c9771
    internal-label: Audiences
  - id: 33ca0c14-7e3b-55a1-8fd7-8a61b47da4e1
    internal-label: B2B
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: a50ad69b-1331-40e9-b634-531a085a6a54
    internal-label: Identities
  - id: afadf741-c5fe-42cd-8013-23bb6ff2d1bc
    internal-label: Buying Groups
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: eec185bd-7d60-4193-ba3f-da427569936a
    internal-label: Destinations
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
    internal-label: Data management
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 827c313f032d482ac2b0a5fa8f41d6506e67b9cb
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%
---
# 資料可用性和同步時間 {#data-availability}

使用此主題來瞭解資料變更在您的[!DNL Adobe Journey Optimizer B2B Edition]歷程中出現的速度，以及哪些時間表正常。 瞭解預期的時間有助於您據此設計歷程，並識別延遲何時是預期行為。

## 預期等待時間

| 資料類型 | 一般可用性 |
| --- | --- |
| [對象會籍](#daily-refresh) | 長達24小時（每日週期） |
| [帳戶和人員關係變更](#daily-refresh) | 長達24小時（每日週期） |
| [資料從 [!DNL Experience Platform] 到 [!DNL Journey Optimizer B2B Edition]](#platform-sync) | 長達30分鐘（近乎即時） |
| [資料從 [!DNL Journey Optimizer B2B Edition] 到 [!DNL Experience Platform]](#platform-sync) | 最多四個小時（微批次） |
| [活動事件，例如點按和開啟](#activity-and-actions) | 最多四個小時 |
| [[!DNL Marketo Engage] 清單新增或移除](#activity-and-actions) | 在30分鐘內（近乎即時） |
| 由Journey Optimizer B2B Edition產生的[事件](#activity-and-actions) | 僅可用於批次對象 |
| [LinkedIn對象母體](#linkedin-timing) | 同日到36到40小時（最壞情況） |

## 對象和關係資料 {#daily-refresh}

[!DNL Journey Optimizer B2B Edition]每天會評估一次帳戶和人員對象成員資格，由批次工作排程器觸發。 因此：

* 新符合對象資格的帳戶或人員將有資格在符合資格後的24小時內進入歷程。
* 對象條件的變更會在下一個每日評估週期中生效。
* 如果帳戶今天符合對象資格但尚未進入歷程，請等到下一個每日週期完成再進行調查。
* 當個人的帳戶關聯變更時，例如當連絡人移至不同帳戶時，關係更新會在24小時內透過每日同步週期傳播。 依賴帳戶成員資格的歷程會反映下一個每日週期後更新的關係。 不需要採取任何動作。

>[!TIP]
>
>設計歷程，瞭解對象會籍會每天更新，而非即時更新。 如果您需要近乎即時的回應，請使用[事件型觸發器](../journeys/listen-for-event-nodes.md)，而非對象型專案。

## 資料與[!DNL Experience Platform]同步 {#platform-sync}

[!DNL Experience Platform]是帳戶、人員和機會的主要資料存放區，[!DNL Journey Optimizer B2B Edition]擁有歷程、購買群組和購買群組角色。 [進一步瞭解架構](../about-journey-optimizer-b2b-edition.md#high-level-architecture)。

資料會以不同的速度在兩個系統之間往每個方向移動：

* **[!DNL Experience Platform]到[!DNL Journey Optimizer B2B Edition]** — 近乎即時同步資料，最多可能需要30分鐘。
* **[!DNL Journey Optimizer B2B Edition]到[!DNL Experience Platform]** — 以微批次同步資料，最多可能需要4小時。

## 活動事件和歷程動作 {#activity-and-actions}

活動資料和歷程動作的時間取決於資料在系統之間移動的方式：

* **活動資料** — 個人活動記錄（例如電子郵件開啟、連結點按和表單填寫）大約需要4小時才能在[!DNL Journey Optimizer B2B Edition]中顯示。 此時間適用於批次活動資料；[!DNL Experience Platform]體驗事件觸發器使用串流資料，可以近乎即時地做出反應。
* **[!DNL Marketo Engage]動作** — 呼叫[!DNL Marketo Engage]的歷程動作近乎即時，因為它們是API呼叫。 例如，當歷程步驟從[!DNL Marketo]清單新增或移除人員時，動作通常會在30分鐘內完成。 [進一步瞭解歷程動作](../journeys/action-nodes.md)。
* **執行[!DNL Experience Platform]**&#x200B;的動作 — 任何先傳回[!DNL Experience Platform]的動作都會進行批次處理，因此會受批次計時的限制，而非近乎即時的限制。
* **由[!DNL Journey Optimizer B2B Edition]**&#x200B;產生的事件 — [!DNL Journey Optimizer B2B Edition]在[!DNL Experience Platform]中產生的事件只能用於批次對象。

## [!DNL LinkedIn]個對象目的地 {#linkedin-timing}

如果您的歷程包含[!DNL LinkedIn]目的地動作，請在發佈歷程後預期下列時間表。

| 狀況 | 預期等待 |
| --- | --- |
| 發佈歷程時，帳戶已在受眾中 | 當天，如果處理在當地時間午夜之前完成 |
| 帳戶在歷程發佈後到達 | 長達24小時 |
| 帳戶在第一個每日同步處理期間之後到達 | 長達36-40小時 |

[!DNL LinkedIn]受眾規模可能不會立即更新。 此延遲是[!DNL Experience Platform]處理對象檔案並將對象檔案傳送到[!DNL LinkedIn]時的預期延遲。 如果48小時後受眾規模仍為0，請調查。 [進一步瞭解LinkedIn帳戶相符的對象](./linkedin-account-matched-audiences.md)。

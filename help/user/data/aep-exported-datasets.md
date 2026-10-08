---
title: 已匯出的Experience Platform資料集
description: Adobe Journey Optimizer B2B Edition匯出的Adobe Experience Platform資料集名稱和關鍵欄位路徑的參考。
feature: Setup, Data Management
role: Admin
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
feature_v2:
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
    internal-label: Data management
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
autotag-review: '2026-09-29T00:00:00.000Z'
source-git-commit: 801025ee02617d56fc8ab933b59385bca38f5097
workflow-type: tm+mt
source-wordcount: '4845'
ht-degree: 6%
---

# 已匯出[!DNL Experience Platform]個資料集

[!DNL Adobe Journey Optimizer B2B Edition]在[!DNL Adobe Experience Platform]中提供帳戶、人員、購買群組和歷程資訊。 資料集是相關記錄的集合。 例如，「人員」資料集會描述人員、成員資格資料集會將人員連結至帳戶或歷程，而事件資料集會記錄開啟電子郵件等動作。

使用本指南來瞭解每個資料集包含的內容、其欄位的含義以及相關記錄如何連結。 資料集名稱會遵循以下模式：

**`AJOB2B-<datasetVersion>-<entity>`**

在這裡，`<entity>`說明資訊，例如`person`、`account_relational`或`person_event`。 `<datasetVersion>`會識別資料集欄位定義的版本。 區段標題會顯示記錄的名稱；您的[!DNL Experience Platform]環境可能也包含舊版。

如需支援這些匯出的名稱空間和結構描述設定，請參閱[B2B名稱空間和結構描述](./namespaces-schemas.md)。

>[!NOTE]
>
>Adobe會保留較舊的資料集版本，以避免中斷現有的使用。 因此，您的沙箱中可能會找到相同資料集的多個版本。 如果您不再使用舊版資料集，可以請求Adobe將其移除。 在請求移除之前，請確認該資料集已不再使用。

## 閱讀本指南

- **欄位名稱：**&#x200B;您在[!DNL Experience Platform]中看到的確切名稱。 在欄位中分隔層級的點，例如`consents.marketing.email.val`。
- **記錄識別碼：**&#x200B;會識別該資料集中的記錄。
- **關聯性：**&#x200B;會為識別項相符的資料集和欄位命名。 例如，`Matches AJOB2B-1_5_4-buying_group (_id)`表示欄位參考購買群組的`_id`。 符合完整的識別碼；請勿縮短或嘗試重新建置。
- **標準Adobe格式：**&#x200B;使用Adobe的共用欄位定義。
- **相關記錄格式：**&#x200B;將資訊組織成您可以使用相符的識別碼連線的記錄。

例如，`buying_group_member.buyingGroupID`符合`buying_group._id`，而其`personID`符合`person_relational._id`或人員資料集的`personKey.sourceKey`。 這些連結可協助您瞭解誰屬於購買群組。 [!DNL Experience Platform]不會單獨從連結中自動建立報表或對象。

有些識別碼參考本指南中沒有個別資料集的資訊，例如行銷方案。 「關係」欄會記下這點，而非命名不存在於此的資料集。

當記錄被標籤為已刪除時，`isDeleted`為`true`，而當記錄未標籤為已刪除時，`false`。 請勿將其視為一般主動成員或同意指標。 `lastUpdatedDate`說明記錄的最新資料更新；對於事件，請使用`timestamp`來瞭解活動何時發生。 空白欄位表示資訊無法使用或不適用於該記錄。

相關記錄資料集使用版本`1_5_4`。 如果欄位目前未填入或需要特殊處理，相關區段將說明客戶可見的限制。

對象是符合所選條件的一組人員。 對象建立的可用性取決於您的[!DNL Experience Platform]設定，以將資訊結合至人員設定檔。 資料集在[!DNL Experience Platform]中的存在本身並不表示它可用於分段。

## 選擇資料集

| 您想瞭解的內容 | 要尋找的資料集 |
|---|---|
| 人員及其電子郵件偏好設定 | `person` |
| 帳戶詳細資料和個人聯絡詳細資訊 | `account_relational`, `person_relational` |
| 哪些人員與帳戶相關聯 | `account_member`, `account_person` |
| 購買群組、其成員及狀態變更 | `buying_group`, `buying_group_member`, `buying_group_event` |
| 帳戶歷程與參與帳戶 | `account_journey`, `account_journey_member`, `account_event` |
| 個人歷程與參與人員 | `person_journey`, `person_journey_member` |
| 歷程中的步驟 | `account_journey_node`, `person_journey_node`, `journey_node` |
| 電子郵件、網頁和其他支援的個人活動 | `person_event`, `person_event_relational` |

以下區段提供完整的資料集名稱和欄位詳細資訊。 歷程描述了整體體驗；成員資格將個人或帳戶連線到該歷程；事件描述了所發生的事情。

+++實體關係圖

已匯出至[!DNL Adobe Experience Platform]![&#128279;](./assets/ajo-b2b-data-model.svg)的資料集的實體關係圖

+++

## `AJOB2B-1_5_1-person`

每筆記錄都會描述個人、其識別碼及其電子郵件行銷偏好設定。 將其用於人員層級報表，並在已設定設定設定檔的情況下，協助建立對象。

**格式：**&#x200B;標準Adobe格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `personID` | 記錄ID | 適用於個人的識別碼。 使用完整值來比對相關記錄。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `identityMap` |  | 可協助[!DNL Experience Platform]辨識您連線資料中相同使用者的其他識別碼。 |
| `consents.marketing.email.val` |  | 電子郵件行銷偏好設定： `n`表示選擇退出；`y`表示此欄位中未記錄任何選擇退出。 僅此欄位無法建立傳送行銷電子郵件的許可權。 |
| `consents.marketing.email.time` |  | 電子郵件偏好設定上次更新的日期與時間。 |
| `consents.marketing.email.reason` |  | 提供選擇退出的原因（僅在取消訂閱時設定）。 |
| `isDeleted` |  | 此人員記錄是否標籤為已刪除。 |

>[!NOTE]
>
>您的組織可能會有其他人員欄位，超出此處列出的範圍。

當您的組織使用自己設定的帳戶或人員資料集時，這些記錄也可以包含`isDeleted`。 檢視[客戶擁有的資料集](#customer-owned-datasets)。

## `AJOB2B-1_5_4-account_member`

每筆記錄會將一個帳戶連結至一個人。 使用此資料集來報告與每個帳戶相關聯的人員；它描述關係，而不是其中一個設定檔。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 關係記錄ID。 |
| `accountID` | 符合`AJOB2B-1_5_4-account_relational` (`_id`) | 帳戶識別碼。 |
| `personID` | 符合`AJOB2B-1_5_4-person_relational` (`_id`) | 個人識別碼。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-buying_group`

每筆記錄會說明與帳戶相關的購買群組，包括其名稱、狀態、解決方案興趣，以及參與和完整度分數。 目前未填入購買群組階段。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 購買群組記錄ID （使用完整值）。 |
| `buyingGroupName` |  | 購買團體名稱。 |
| `engagementScore` |  | 參與分數。 |
| `completenessScore` |  | 完整度分數。 |
| `accountID` | 符合`AJOB2B-1_5_4-account_relational` (`_id`) | 相關帳戶識別碼。 |
| `solutionInterest` |  | 解決方案興趣標籤。 |
| `buyingGroupStatus` |  | 狀態。 |
| `buyingGroupStage` |  | 購買群組階段名稱。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

>[!NOTE]
>
>**可用性備註：** `buyingGroupStage`目前為空白。 請勿使用它來依階段篩選或分組購買群組。

## `AJOB2B-1_5_4-buying_group_member`

每筆記錄會將個人連結至購買群組，並記錄該人的角色。 用它來報告購買群組構成和角色涵蓋範圍。

`isDeleted`並不一定表示某人是否已從購買群組中移除。 請勿單獨使用此欄位來判斷目前的成員資格。 沒有可用的角色資訊時，角色名稱可以空白。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 成員資格記錄ID。 |
| `buyingGroupID` | 符合`AJOB2B-1_5_4-buying_group` (`_id`) | 購買群組識別碼。 |
| `personID` | 符合`AJOB2B-1_5_4-person_relational` (`_id`) | 個人識別碼。 |
| `buyingGroupMemberRole` |  | 角色名稱（可用時）。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-account_journey`

每個記錄會說明帳戶歷程，包含其名稱、狀態、開始和結束日期。 用它來報告帳戶的歷程生命週期和狀態。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 歷程記錄ID （使用完整值）。 |
| `accountJourneyName` |  | 歷程名稱。 |
| `accountJourneyStatus` |  | 狀態（例如草稿、即時、已完成）。 |
| `startDate` |  | 開始時間戳記。 |
| `endDate` |  | 結束時間戳記。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-account_journey_member`

每個記錄都會將帳戶與帳戶歷程連線。 用它來識別和報告哪些帳戶參與每個歷程。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 成員資格記錄ID。 |
| `accountID` | 符合`AJOB2B-1_5_4-account_relational` (`_id`) | 帳戶識別碼。 |
| `journeyID` | 符合`AJOB2B-1_5_4-account_journey` (`_id`) | 帳戶歷程識別碼。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-person_journey`

每個記錄描述個人歷程，包含其名稱、狀態以及開始和結束日期。 用它來報告歷程生命週期和以人為中心的歷程狀態。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 歷程記錄ID （使用完整值）。 |
| `personJourneyName` |  | 歷程名稱。 |
| `personJourneyStatus` |  | 狀態（例如草稿、即時、已完成）。 |
| `startDate` |  | 開始時間戳記。 |
| `endDate` |  | 結束時間戳記。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-person_journey_member`

每筆記錄會說明個人在歷程中的成員資格，包括目前的歷程節點、成員資格和進入日期，以及進入計數。 用它來報告註冊、重新進入和歷程進度。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 成員資格記錄ID。 |
| `marketingProgramID` |  | 歷程所屬的行銷方案識別碼。 |
| `personID` | 符合`AJOB2B-1_5_4-person_relational` (`_id`) | 個人識別碼。 |
| `journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程識別碼。 |
| `journeyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 個人目前所在歷程節點的識別碼。 |
| `membershipDate` |  | 此人成為行銷方案成員時。 |
| `lastEntryDate` |  | 此人上次進入歷程的時間。 |
| `reentryOpensAt` |  | 當人員可重新進入歷程時。 |
| `entryCount` |  | 個人已進入歷程的次數。 |
| `createdDate` |  | 建立紀錄的時間。 |
| `updatedDate` |  | 記錄最後一次變更的時間。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-account_journey_node`

每筆記錄都描述歷程中的步驟，包括步驟種類及其所屬的歷程。 歷程節點是開始、等待或決定等步驟。 `person_journey_node`中可能會顯示相同的步驟；先比對`accountJourneyID`與帳戶歷程，再將步驟視為帳戶特定步驟。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 節點記錄ID （使用完整值）。 |
| `accountJourneyID` | 符合`AJOB2B-1_5_4-account_journey` (`_id`) | 上層歷程識別碼。 |
| `uuid` |  | 歷程步驟的其他識別碼。 |
| `journeyNodeTypeID` |  | 識別歷程步驟型別的數字。 |
| `nodeType` |  | 識別歷程步驟種類的標籤。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `createdDate` |  | 建立紀錄的時間。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-person_journey_node`

每筆記錄都描述歷程中的步驟，包括步驟種類及其所屬的歷程。 `account_journey_node`中可能會顯示相同的步驟；先比對`personJourneyID`與個人歷程，再將步驟視為個人專屬步驟。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 節點記錄ID （使用完整值）。 |
| `personJourneyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 上層歷程識別碼。 |
| `uuid` |  | 歷程步驟的其他識別碼。 |
| `journeyNodeTypeID` |  | 識別歷程步驟型別的數字。 |
| `nodeType` |  | 識別歷程步驟種類的標籤。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `createdDate` |  | 建立紀錄的時間。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-account_event`

每個記錄都會擷取帳戶歷程事件：在歷程中新增或移除的帳戶，或在歷程節點之間移動的帳戶。 使用`eventType`和`timestamp`來建置帳戶活動時間表；當事件為購買群組歸因時，`buyingGroupID`可供使用。

**格式：**&#x200B;相關記錄格式

`eventType`提供有關所發生事件的資訊。 下表說明每種活動的欄位。

這些事件目前未填入`lastUpdatedDate`。 使用`timestamp`作為活動日期。

### 帳戶已新增至歷程(`account.addAccountToJourney`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `account.addAccountToJourney`. |
| `timestamp` |  | 活動發生的時間。 |
| `accountID` | 符合`AJOB2B-1_5_4-account_relational` (`_id`) | 帳戶識別碼。 |
| `journeyID` | 符合`AJOB2B-1_5_4-account_journey` (`_id`) | 歷程識別碼。 |
| `journeyNodeID` | 符合`AJOB2B-1_5_4-account_journey_node` (`_id`) | 歷程節點識別碼。 |
| `buyingGroupID` | 符合`AJOB2B-1_5_4-buying_group` (`_id`) | 當歷程新增是購買群組歸因時，購買群組識別碼。 |
| `lastUpdatedDate` |  | 記錄更新時間。 目前空白；使用活動日期的時間戳記。 |

### 已從歷程移除帳戶(`account.removeAccountFromJourney`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `account.removeAccountFromJourney`. |
| `timestamp` |  | 活動發生的時間。 |
| `accountID` | 符合`AJOB2B-1_5_4-account_relational` (`_id`) | 帳戶識別碼。 |
| `journeyID` | 符合`AJOB2B-1_5_4-account_journey` (`_id`) | 歷程識別碼。 |
| `journeyNodeID` | 符合`AJOB2B-1_5_4-account_journey_node` (`_id`) | 歷程節點識別碼。 |
| `buyingGroupID` | 符合`AJOB2B-1_5_4-buying_group` (`_id`) | 購買群組識別碼，當歷程移除是購買 — 群組歸因時。 |
| `lastUpdatedDate` |  | 記錄更新時間。 目前空白；使用活動日期的時間戳記。 |

### 帳戶在歷程步驟之間移動(`account.changeAccountJourneyNode`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `account.changeAccountJourneyNode`. |
| `timestamp` |  | 活動發生的時間。 |
| `accountID` | 符合`AJOB2B-1_5_4-account_relational` (`_id`) | 帳戶識別碼。 |
| `journeyID` | 符合`AJOB2B-1_5_4-account_journey` (`_id`) | 歷程識別碼。 |
| `journeyNodeID` | 符合`AJOB2B-1_5_4-account_journey_node` (`_id`) | 歷程節點識別碼。 |
| `previousJourneyNodeID` | 參考`AJOB2B-1_5_4-account_journey_node` (`_id`)；值可能不相符 | 上一個歷程步驟的識別碼。 此值可能與對應的步驟記錄不符；請勿單獨依賴它來連線記錄。 |
| `buyingGroupID` | 符合`AJOB2B-1_5_4-buying_group` (`_id`) | 當節點變更為購買群組歸因時，購買群組識別碼。 |
| `lastUpdatedDate` |  | 記錄更新時間。 目前空白；使用活動日期的時間戳記。 |

## `AJOB2B-1_5_4-buying_group_event`

每筆記錄會擷取購買群組狀態的變更，包括新狀態及其變更時間。 目前未填入新階段欄位。

**格式：**&#x200B;相關記錄格式

### 購買群組狀態已變更(`buyingGroup.changeStatus`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `buyingGroup.changeStatus`. |
| `timestamp` |  | 活動發生的時間。 |
| `buyingGroupID` | 符合`AJOB2B-1_5_4-buying_group` (`_id`) | 購買群組識別碼。 |
| `newStatus` |  | 新狀態值。 |
| `newStage` |  | 新的購買群組階段。 目前空白。 |
| `lastUpdatedDate` |  | 記錄更新時間。 |

>[!NOTE]
>
>**可用性備註：**&#x200B;使用`newStatus`報告狀態變更。 請勿使用`newStage`來報告階段變更，因為它目前為空白。

## `AJOB2B-1_5-person_event`

每個記錄會說明個人層級的網頁、電子郵件或其他支援的活動事件。 使用`eventType`和`timestamp`來分析一段時間內的行為，僅針對相符的事件型別填入事件特定詳細資料。

**格式：**&#x200B;標準Adobe格式

`eventType`告訴您發生的情況。 下表說明每種活動的欄位。 不適用於事件的詳細資料為空白。

### 電子郵件已傳送(`directMarketing.emailSent`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `directMarketing.emailSent`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `directMarketing.emailSent.mailingKey.sourceID` |  | 郵寄資產ID。 |
| `directMarketing.emailSent.mailingKey.sourceType` |  | 連線產品的名稱。 |
| `directMarketing.emailSent.mailingKey.sourceInstanceID` |  | 執行個體ID。 |
| `directMarketing.emailSent.mailingKey.sourceKey` |  | 完整的電子郵件內容識別碼。 |
| `directMarketing.emailSent.mailingName` |  | 郵寄名稱。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程ID （若已歸因）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點ID （如果已歸因）。 |

### 電子郵件已傳遞(`directMarketing.emailDelivered`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `directMarketing.emailDelivered`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `directMarketing.mailingKey.sourceID` |  | 郵寄資產ID。 |
| `directMarketing.mailingKey.sourceType` |  | 連線產品的名稱。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | 執行個體ID。 |
| `directMarketing.mailingKey.sourceKey` |  | 完整的電子郵件內容識別碼。 |
| `directMarketing.mailingName` |  | 郵寄名稱。 |
| `directMarketing.email` |  | 電子郵件地址。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程ID （若已歸因）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點ID （如果已歸因）。 |

### 電子郵件取消訂閱(`directMarketing.emailUnsubscribed`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `directMarketing.emailUnsubscribed`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `directMarketing.mailingKey.sourceID` |  | 郵寄資產ID。 |
| `directMarketing.mailingKey.sourceType` |  | 連線產品的名稱。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | 執行個體ID。 |
| `directMarketing.mailingKey.sourceKey` |  | 完整的電子郵件內容識別碼。 |
| `directMarketing.mailingName` |  | 郵寄名稱。 |
| `directMarketing.email` |  | 電子郵件地址。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程ID （若已歸因）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點ID （如果已歸因）。 |

### 電子郵件已開啟(`directMarketing.emailOpened`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `directMarketing.emailOpened`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `directMarketing.mailingKey.sourceID` |  | 郵寄資產ID。 |
| `directMarketing.mailingKey.sourceType` |  | 連線產品的名稱。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | 執行個體ID。 |
| `directMarketing.mailingKey.sourceKey` |  | 完整的電子郵件內容識別碼。 |
| `directMarketing.mailingName` |  | 郵寄名稱。 |
| `directMarketing.email` |  | 電子郵件地址。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程ID （若已歸因）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點ID （如果已歸因）。 |
| `device.isMobileDevice` |  | 是否已為活動記錄行動裝置。 |
| `device.model` |  | 裝置或電子郵件使用者端資訊。 |
| `environment.browserDetails.userAgent` |  | 瀏覽器或電子郵件使用者端資訊。 |
| `environment.operatingSystem` |  | 作業系統。 |

### 電子郵件連結已點按(`directMarketing.emailClicked`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `directMarketing.emailClicked`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `directMarketing.mailingKey.sourceID` |  | 郵寄資產ID。 |
| `directMarketing.mailingKey.sourceType` |  | 連線產品的名稱。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | 執行個體ID。 |
| `directMarketing.mailingKey.sourceKey` |  | 完整的電子郵件內容識別碼。 |
| `directMarketing.mailingName` |  | 郵寄名稱。 |
| `directMarketing.email` |  | 電子郵件地址。 |
| `directMarketing.linkURL` |  | 已按一下連結URL。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程ID （若已歸因）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點ID （如果已歸因）。 |
| `device.isMobileDevice` |  | 是否已為活動記錄行動裝置。 |
| `device.model` |  | 裝置或電子郵件使用者端資訊。 |
| `environment.browserDetails.userAgent` |  | 瀏覽器或電子郵件使用者端資訊。 |
| `environment.operatingSystem` |  | 作業系統。 |

### 電子郵件已退回(`directMarketing.emailBounced`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `directMarketing.emailBounced`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `directMarketing.mailingKey.sourceID` |  | 郵寄資產ID。 |
| `directMarketing.mailingKey.sourceType` |  | 連線產品的名稱。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | 執行個體ID。 |
| `directMarketing.mailingKey.sourceKey` |  | 完整的電子郵件內容識別碼。 |
| `directMarketing.mailingName` |  | 郵寄名稱。 |
| `directMarketing.email` |  | 電子郵件地址。 |
| `directMarketing.emailBouncedCode` |  | 退回類別/代碼。 |
| `directMarketing.emailBouncedDetails` |  | 詳細資料文字。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程ID （若已歸因）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點ID （如果已歸因）。 |

### 電子郵件軟退信(`directMarketing.emailBouncedSoft`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `directMarketing.emailBouncedSoft`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `directMarketing.mailingKey.sourceID` |  | 郵寄資產ID。 |
| `directMarketing.mailingKey.sourceType` |  | 連線產品的名稱。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | 執行個體ID。 |
| `directMarketing.mailingKey.sourceKey` |  | 完整的電子郵件內容識別碼。 |
| `directMarketing.mailingName` |  | 郵寄名稱。 |
| `directMarketing.email` |  | 電子郵件地址。 |
| `directMarketing.emailBouncedCode` |  | 退回類別/代碼。 |
| `directMarketing.emailBouncedDetails` |  | 詳細資料文字。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程ID （若已歸因）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點ID （如果已歸因）。 |

### 網頁已檢視(`web.webpagedetails.pageViews`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `web.webpagedetails.pageViews`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `web.webPageDetails.webPageKey.sourceID` |  | 頁面資產ID。 |
| `web.webPageDetails.webPageKey.sourceType` |  | 連線產品的名稱。 |
| `web.webPageDetails.webPageKey.sourceInstanceID` |  | 執行個體ID。 |
| `web.webPageDetails.webPageKey.sourceKey` |  | 完整頁面識別碼。 |
| `web.webPageDetails.name` |  | 頁面名稱。 |
| `web.webPageDetails.URL` |  | 頁面URL。 |
| `web.webPageDetails.queryParameters` |  | 網址中包含的其他資訊。 |
| `web.webPageDetails.webPageID` |  | 頁面ID。 |
| `environment.browserDetails.userAgent` |  | 瀏覽器或電子郵件使用者端資訊。 |
| `web.webReferrer.URL` |  | 反向連結URL。 |

### 已點按Web連結(`web.webinteraction.linkClicks`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `web.webinteraction.linkClicks`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `web.webInteraction.webInteractionKey.sourceID` |  | 互動資產識別碼。 |
| `web.webInteraction.webInteractionKey.sourceType` |  | 連線產品的名稱。 |
| `web.webInteraction.webInteractionKey.sourceInstanceID` |  | 執行個體ID。 |
| `web.webInteraction.webInteractionKey.sourceKey` |  | 完整的互動識別碼。 |
| `web.webInteraction.linkID` |  | 連結ID。 |
| `web.webInteraction.linkURL` |  | 目的地 URL。 |
| `web.webPageDetails.queryParameters` |  | 網址中包含的其他資訊。 |
| `web.webPageDetails.webPageID` |  | 頁面ID。 |
| `environment.browserDetails.userAgent` |  | 瀏覽器或電子郵件使用者端資訊。 |
| `web.webReferrer.URL` |  | 反向連結URL。 |

### 表單已提交(`web.formFilledOut`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `web.formFilledOut`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `web.fillOutForm.webFormKey.sourceID` |  | 表單資產id。 |
| `web.fillOutForm.webFormKey.sourceType` |  | 連線產品的名稱。 |
| `web.fillOutForm.webFormKey.sourceInstanceID` |  | 執行個體ID。 |
| `web.fillOutForm.webFormKey.sourceKey` |  | 完整的表單識別碼。 |
| `web.fillOutForm.webFormID` |  | 表單ID。 |
| `web.fillOutForm.webFormName` |  | 表單名稱。 |
| `web.webPageDetails.queryParameters` |  | 網址中包含的其他資訊。 |
| `web.webPageDetails.webPageID` |  | 頁面ID。 |
| `environment.browserDetails.userAgent` |  | 瀏覽器或電子郵件使用者端資訊。 |
| `web.webReferrer.URL` |  | 反向連結URL。 |

### 已記錄有趣的時刻(`leadOperation.interestingMoment`)

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動識別碼。 |
| `eventType` |  | `leadOperation.interestingMoment`. |
| `timestamp` |  | 活動發生的時間。 |
| `personID` | 符合`AJOB2B-1_5_1-person` (`personID`) | 個人識別碼。 |
| `personKey.sourceID` |  | 連線系統中的個人識別碼。 |
| `personKey.sourceType` |  | 連線產品的名稱。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境或連線帳戶的識別碼。 |
| `personKey.sourceKey` |  | 用於比對相關記錄的完整人員識別碼。 |
| `leadOperation.interestingMoment.date` |  | 時刻日期/時間。 |
| `leadOperation.interestingMoment.description` |  | 說明。 |
| `leadOperation.interestingMoment.source` |  | 相關產品或行銷活動的名稱。 |
| `leadOperation.interestingMoment.type` |  | 輸入標籤。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程ID （若已歸因）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點ID （如果已歸因）。 |

## `AJOB2B-1_5_4-journey_node`

每個記錄都描述歷程步驟、它所屬的歷程以及步驟的型別。 帳戶和人員歷程步驟資料集中可能會顯示相同的步驟。 將`journeyID`與適當的歷程比對；不要將步驟計為超過一次，因為它出現在多個資料集中。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 節點記錄ID （使用完整值）。 |
| `journeyID` | 符合`AJOB2B-1_5_4-account_journey`或`AJOB2B-1_5_4-person_journey` (`_id`) | 上層歷程識別碼。 |
| `nodeType` |  | 某種歷程步驟，例如開始、結束、等待或決定。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-account_relational`

每個記錄都說明一個帳戶，包括其組織詳細資訊、位置、大小、收入和自訂欄位。 使用此資訊將帳戶內容新增至購買群組和歷程報表。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 帳戶記錄ID （使用完整值）。 |
| `accountName` |  | 帳戶名稱。 |
| `industry` |  | 產業分類。 |
| `country` |  | 國家/地區 |
| `sicCode` |  | 標準產業分類代碼。 |
| `domainName` |  | 主要網域。 |
| `primaryEmailDomain` |  | 主要電子郵件網域。 |
| `street` |  | 街道地址。 |
| `city` |  | 城市。 |
| `state` |  | 州或地區。 |
| `postalCode` |  | 郵遞區號。 |
| `region` |  | 地理區域。 |
| `phoneNumber` |  | 電話號碼。 |
| `logoUrl` |  | 帳戶標誌的URL。 |
| `annualRevenue` |  | 年收入。 |
| `numberOfEmployees` |  | 員工人數。 |
| `createdDate` |  | 建立紀錄的時間。 |
| `sourceType` |  | 用來識別帳戶的已連線系統名稱。 |
| `sourceInstanceID` |  | 您在該連線系統中的組織或帳戶的識別碼。 |
| `sourceID` |  | 該連線系統中的帳戶識別碼。 |
| `customAttributes` |  | 自訂欄位名稱和值一起儲存為文字。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-person_relational`

每個記錄都描述了一個人，包括其聯絡資訊、工作詳細資訊、識別碼和自訂欄位。 用它來將個人資訊新增至會籍、歷程和活動報表。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 用於比對相關記錄的完整人員識別碼。 |
| `email` |  | 電子郵件地址。 |
| `firstName` |  | 名字。 |
| `middleName` |  | 中間名。 |
| `lastName` |  | 姓氏。 |
| `jobTitle` |  | 職稱。 |
| `personType` |  | 個人型別：聯絡人、潛在客戶或暫緩銷售機會。 |
| `isLead` |  | 此人是否為潛在客戶。 |
| `isAnonymous` |  | 此人是否為匿名。 |
| `salutation` |  | 致敬或尊敬。 |
| `phone` |  | 主要電話號碼。 |
| `mobile` |  | 行動電話號碼。 |
| `sourceType` |  | 識別人員的連線系統名稱，例如[!DNL Marketo Engage]。 |
| `sourceInstanceID` |  | 您在該連線系統中的組織或帳戶的識別碼。 |
| `sourceID` |  | 該連線系統中的個人識別碼。 |
| `identityNamespace` |  | 識別額外人員識別碼型別的標籤。 |
| `identityValue` |  | 次要身分的值。 |
| `customAttributes` |  | 自訂欄位名稱和值一起儲存為文字。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-account_person`

每個記錄會將帳戶設定檔連結至個人設定檔。 用它來報告帳戶和個人設定檔資料集之間的關係。

**格式：**&#x200B;相關記錄格式

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 帳戶 — 個人關係記錄ID （使用完整值）。 |
| `accountID` | 符合`AJOB2B-1_5_4-account_relational` (`_id`) | 完整的帳戶識別碼（參考`account_relational._id`）。 |
| `personID` | 符合`AJOB2B-1_5_4-person_relational` (`_id`) | 完整的人員識別碼（參考`person_relational._id`）。 |
| `createdDate` |  | 建立帳戶 — 個人關係的時間。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

## `AJOB2B-1_5_4-person_event_relational`

每筆記錄都描述支援的人員活動，例如檢視網頁、與電子郵件互動或移動歷程。 使用`eventType`和`activityTypeID`瞭解所發生的情況。 系統只會填入與該型別活動相關的詳細資料。

**格式：**&#x200B;相關記錄格式

下列欄位清單涵蓋所有支援的活動型別。 個別記錄僅包含適用於其活動的詳細資料。

>[!NOTE]
>
>**可用性：**&#x200B;某些活動可能會有空白的`_id`。 請勿假設每個活動都有可用的記錄識別碼。 資料集並不保證有完整的活動歷史記錄。

歷程活動(`person.journeyAdd`、`person.journeyRemove`、`person.journeyStart`、`person.journeyEnd`、`person.journeyNodeTransition`、`person.journeySplitNode`)以及與「更新人員設定檔」歷程步驟相關的`person.attributeChanged`活動皆已提供歷程詳細資料（`journeyID`、`journeyNodeID`、`journeyStepID`及類似的欄位）。

只為`person.attributeChanged`填入屬性變更欄位(`attributeName`、`attributeID`、`attributeNewValue`、`attributeOldValue`、`attributeChangeReason`)。

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id` | 記錄ID | 活動的識別碼（可用時）。 |
| `timestamp` |  | 活動發生的時間。 |
| `eventType` |  | 活動標籤。 值： `web.webpagedetails.pageViews`、`web.formFilledOut`、`web.webinteraction.linkClicks`、`directMarketing.emailSent`、`directMarketing.emailDelivered`、`directMarketing.emailBounced`、`directMarketing.emailBouncedSoft`、`directMarketing.emailUnsubscribed`、`directMarketing.emailOpened`、`directMarketing.emailClicked`、`leadOperation.interestingMoment`、`person.attributeChanged`、`person.journeyAdd`、`person.journeyRemove`、`person.journeyStart`、`person.journeyEnd`、`person.journeyNodeTransition`、`person.journeySplitNode`。 |
| `activityTypeID` |  | 活動代碼。 將其與`eventType`搭配使用，以區分共用相同事件標籤的活動。 |
| `personID` | 符合`AJOB2B-1_5_4-person_relational` (`_id`) | 用於將活動與個人記錄比對的完整個人識別碼。 |
| `journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 完整歷程識別碼。 與歷程無關的活動為空白。 |
| `journeyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 完整的歷程步驟識別碼。 與歷程無關的活動為空白。 |
| `previousJourneyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 先前的歷程節點（已填入`person.journeyNodeTransition`和`person.journeySplitNode`）。 |
| `newJourneyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 目的地歷程節點識別碼（`person.journeyNodeTransition`和`person.journeySplitNode`）。 通常等於`journeyNodeID`。 |
| `journeyStepID` |  | 與活動相關之歷程步驟的識別碼。 |
| `journeyChoiceNumber` |  | `person.journeySplitNode`的分割選擇號碼。 以整數記錄。 |
| `journeyEntryCount` |  | 此人已進入歷程的次數（在歷程新增/開始事件上填入）。 以整數記錄。 |
| `journeyProgramID` | 本指南中沒有獨立的行銷方案資料集 | 與歷程活動相關聯之行銷方案的識別碼。 |
| `activitySource` |  | 與活動相關聯的產品或動作名稱。 |
| `campaignID` |  | 活動為行銷活動歸因時，為[!DNL Marketo Engage]行銷活動識別碼。 |
| `attributeName` |  | 已變更的欄位名稱（僅限`person.attributeChanged`）。 |
| `attributeID` |  | 已變更之欄位的識別碼（僅限`person.attributeChanged`）。 |
| `attributeNewValue` |  | 新欄位值，記錄為文字（僅限`person.attributeChanged`）。 |
| `attributeOldValue` |  | 上一個欄位值，記錄為文字（僅限`person.attributeChanged`）。 |
| `attributeChangeReason` |  | 變更的原因標籤（僅限`person.attributeChanged`）。 |
| `assetID` |  | 相關電子郵件內容、頁面或表單的識別碼。 |
| `assetName` |  | 相關內容的名稱。 |
| `recipientEmail` |  | 收件者電子郵件地址（可用時）。 僅針對活動代碼&#x200B;**27** （軟退信）和&#x200B;**48** （銷售電子郵件軟退信）填入；其他電子郵件活動則空白。 對於這些活動，請使用`personID`查詢人員記錄。 `assetName`會識別電子郵件內容，而非收件者的地址。 |
| `bouncedCode` |  | 彈回類別代碼（僅限emailBounced / emailBouncedSoft）。 |
| `bouncedDetails` |  | 詳細的跳出原因（僅限emailBounced / emailBouncedSoft）。 |
| `isMobileDevice` |  | 是否已針對開啟或點按的電子郵件記錄行動裝置。 |
| `deviceModel` |  | 裝置型號（僅限emailOpen / emailClicked）。 |
| `operatingSystem` |  | 作業系統（僅限emailOpen / emailClicked）。 |
| `userAgent` |  | 瀏覽器或電子郵件使用者端資訊，適用於電子郵件開啟、電子郵件點按和網頁活動。 |
| `clickedLinkUrl` |  | 已點按電子郵件連結URL （僅限emailClicked）。 |
| `webPageUrl` |  | 網頁URL （僅限`web.webpagedetails.pageViews`）。 |
| `queryParameters` |  | 網址中的其他資訊，適用於頁面檢視、表單提交或網頁連結點按。 |
| `webPageID` |  | [!DNL Marketo Engage]網頁識別碼(pageViews、formFilledOut、linkClicks)。 |
| `referrerUrl` |  | 反向連結URL (pageViews、formFilledOut、linkClicks)。 |
| `formID` |  | [!DNL Marketo Engage]表單識別碼（僅限`web.formFilledOut`）。 |
| `linkID` |  | [!DNL Marketo Engage]連結識別碼（僅限`web.webinteraction.linkClicks`）。 |
| `interestingMomentDate` |  | 時刻日期（僅限`leadOperation.interestingMoment`）。 |
| `interestingMomentDescription` |  | 自由文字說明（僅限interestedMoment）。 |
| `interestingMomentSource` |  | 相關的產品或行銷活動（僅限interestedMoment）。 |
| `interestingMomentType` |  | 類別/型別（僅限interestedMoment）。 |
| `isDeleted` |  | 此記錄是否標籤為已刪除。 |
| `lastUpdatedDate` |  | 上次修改時間。 |

### 依活動型別的欄位參考

下表顯示哪些詳細資料適用於每個活動。 其他詳細資料為空白。 部分活動共用相同的`eventType`標籤：代碼8和48都使用`directMarketing.emailBounced`。 使用`activityTypeID`來區分它們。

#### 網頁已檢視(`web.webpagedetails.pageViews`) （活動型別1）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 頁面ID。 |
| `assetName` |  | 頁面名稱。 |
| `webPageUrl` |  | 頁面URL。 |
| `queryParameters` |  | 網址中包含的其他資訊。 |
| `webPageID` |  | [!DNL Marketo Engage]網頁識別碼。 |
| `referrerUrl` |  | 反向連結URL。 |
| `userAgent` |  | 瀏覽器或電子郵件使用者端資訊。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 已提交表單(`web.formFilledOut`) （活動型別2）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 表單ID。 |
| `assetName` |  | 表單名稱。 |
| `formID` |  | [!DNL Marketo Engage]表單識別碼。 |
| `queryParameters` |  | 網址中包含的其他資訊。 |
| `webPageID` |  | [!DNL Marketo Engage]網頁識別碼。 |
| `referrerUrl` |  | 反向連結URL。 |
| `userAgent` |  | 瀏覽器或電子郵件使用者端資訊。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 網頁連結已點按(`web.webinteraction.linkClicks`) （活動型別3）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 互動/連結ID。 |
| `assetName` |  | 目的地 URL。 |
| `linkID` |  | [!DNL Marketo Engage]連結識別碼。 |
| `queryParameters` |  | 網址中包含的其他資訊。 |
| `webPageID` |  | [!DNL Marketo Engage]網頁識別碼。 |
| `referrerUrl` |  | 反向連結URL。 |
| `userAgent` |  | 瀏覽器或電子郵件使用者端資訊。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 已傳送電子郵件(`directMarketing.emailSent`) （活動型別6、39）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 郵件ID。 |
| `assetName` |  | 郵寄名稱。 |
| `campaignID` |  | 行銷活動歸因時，[!DNL Marketo Engage]行銷活動識別碼。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 電子郵件已傳遞(`directMarketing.emailDelivered`) （活動型別7、45）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 郵件ID。 |
| `assetName` |  | 郵寄名稱。 |
| `campaignID` |  | 行銷活動歸因時，[!DNL Marketo Engage]行銷活動識別碼。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 電子郵件取消訂閱(`directMarketing.emailUnsubscribed`) （活動型別9）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 郵件ID。 |
| `assetName` |  | 郵寄名稱。 |
| `campaignID` |  | 行銷活動歸因時，[!DNL Marketo Engage]行銷活動識別碼。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 電子郵件已開啟(`directMarketing.emailOpened`) （活動型別10、40）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 郵件ID。 |
| `assetName` |  | 郵寄名稱。 |
| `isMobileDevice` |  | 是否已為活動記錄行動裝置。 |
| `deviceModel` |  | 裝置型號。 |
| `operatingSystem` |  | 作業系統。 |
| `userAgent` |  | 瀏覽器或電子郵件使用者端資訊。 |
| `campaignID` |  | 行銷活動歸因時，[!DNL Marketo Engage]行銷活動識別碼。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 電子郵件連結已點按(`directMarketing.emailClicked`) （活動型別11、41）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 郵件ID。 |
| `assetName` |  | 郵寄名稱。 |
| `clickedLinkUrl` |  | 已按一下連結URL。 |
| `isMobileDevice` |  | 是否已為活動記錄行動裝置。 |
| `deviceModel` |  | 裝置型號。 |
| `operatingSystem` |  | 作業系統。 |
| `userAgent` |  | 瀏覽器或電子郵件使用者端資訊。 |
| `campaignID` |  | 行銷活動歸因時，[!DNL Marketo Engage]行銷活動識別碼。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 電子郵件已退回(`directMarketing.emailBounced`)：硬退回（活動型別8）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 郵件ID。 |
| `assetName` |  | 郵寄名稱。 |
| `bouncedCode` |  | 退回類別代碼。 |
| `bouncedDetails` |  | 詳細的退回原因。 |
| `campaignID` |  | 行銷活動歸因時，[!DNL Marketo Engage]行銷活動識別碼。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

此活動與活動代碼48共用`directMarketing.emailBounced`標籤，但代碼8的`recipientEmail`為空白。 使用`activityTypeID`來區分兩者。

#### 電子郵件退回(`directMarketing.emailBounced`)：銷售電子郵件軟退回（活動型別48）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 郵件ID。 |
| `assetName` |  | 郵寄名稱。 |
| `recipientEmail` |  | 收件者電子郵件地址。 |
| `bouncedCode` |  | 退回類別代碼。 |
| `bouncedDetails` |  | 詳細的退回原因。 |
| `campaignID` |  | 行銷活動歸因時，[!DNL Marketo Engage]行銷活動識別碼。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 電子郵件軟退信(`directMarketing.emailBouncedSoft`) （活動型別27）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `assetID` |  | 郵件ID。 |
| `assetName` |  | 郵寄名稱。 |
| `recipientEmail` |  | 收件者電子郵件地址。 |
| `bouncedCode` |  | 退回類別代碼。 |
| `bouncedDetails` |  | 詳細的退回原因。 |
| `campaignID` |  | 行銷活動歸因時，[!DNL Marketo Engage]行銷活動識別碼。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 已記錄有趣的時刻(`leadOperation.interestingMoment`) （活動型別46）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `interestingMomentDate` |  | 時刻日期/時間。 |
| `interestingMomentDescription` |  | 任意文字說明。 |
| `interestingMomentSource` |  | 相關產品或行銷活動的名稱。 |
| `interestingMomentType` |  | 輸入標籤。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

未針對此活動型別填入`assetID`和`assetName`。

#### 人員欄位已變更(`person.attributeChanged`) （活動型別13）

僅當變更與歷程相關聯時包含，例如「更新人員設定檔」步驟。 不包含歷程以外的變更。

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `attributeName` |  | 已變更的欄位名稱。 |
| `attributeID` |  | 已變更之欄位的識別碼。 |
| `attributeNewValue` |  | 新欄位值，記錄為文字。 |
| `attributeOldValue` |  | 上一個欄位值，記錄為文字。 |
| `attributeChangeReason` |  | 變更的原因標籤。 |
| `journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程識別碼。 |
| `journeyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點識別碼。 |
| `journeyStepID` |  | 歷程步驟的識別碼。 |
| `journeyProgramID` | 本指南中沒有獨立的行銷方案資料集 | 歷程方案ID。 |
| `activitySource` |  | 與活動相關聯的產品或動作。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 新增或開始歷程的人(`person.journeyAdd`， `person.journeyStart`) （活動型別182， 184）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程識別碼。 |
| `journeyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點識別碼。 |
| `journeyStepID` |  | 歷程步驟的識別碼。 |
| `journeyEntryCount` |  | 此人已進入歷程的次數。 |
| `journeyProgramID` | 本指南中沒有獨立的行銷方案資料集 | 歷程方案ID。 |
| `activitySource` |  | 與活動相關聯的產品或動作。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 從歷程移除或結束歷程的人(`person.journeyRemove`， `person.journeyEnd`) （活動型別183， 185）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程識別碼。 |
| `journeyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點識別碼。 |
| `journeyStepID` |  | 歷程步驟的識別碼。 |
| `journeyProgramID` | 本指南中沒有獨立的行銷方案資料集 | 歷程方案ID。 |
| `activitySource` |  | 與活動相關聯的產品或動作。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 個人已追蹤歷程分支(`person.journeySplitNode`) （活動型別186）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程識別碼。 |
| `journeyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 歷程節點識別碼（分割節點）。 |
| `previousJourneyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 分割前人員所在的節點。 |
| `newJourneyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 人員移動到的節點（通常等於`journeyNodeID`）。 |
| `journeyStepID` |  | 歷程步驟的識別碼。 |
| `journeyChoiceNumber` |  | 執行分割的分支。 |
| `journeyProgramID` | 本指南中沒有獨立的行銷方案資料集 | 歷程方案ID。 |
| `activitySource` |  | 與活動相關聯的產品或動作。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

#### 人員在歷程步驟之間移動(`person.journeyNodeTransition`) （活動型別600）

| 欄位名稱 | 關係 | 它告訴您的內容 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | 記錄識別碼： `_id`； `personID`符合`AJOB2B-1_5_4-person_relational` (`_id`) | 通用欄位。 |
| `journeyID` | 符合`AJOB2B-1_5_4-person_journey` (`_id`) | 歷程識別碼。 |
| `journeyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 目前歷程節點識別碼。 |
| `previousJourneyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 人員轉換的來源節點。 |
| `newJourneyNodeID` | 符合`AJOB2B-1_5_4-person_journey_node` (`_id`) | 人員轉換為的節點（通常等於`journeyNodeID`）。 |
| `journeyStepID` |  | 歷程步驟的識別碼。 |
| `journeyProgramID` | 本指南中沒有獨立的行銷方案資料集 | 歷程方案ID。 |
| `activitySource` |  | 與活動相關聯的產品或動作。 |
| `isDeleted`, `lastUpdatedDate` |  | 通用欄位。 |

## 客戶擁有的資料集 {#customer-owned-datasets}

您的組織可能會針對帳戶或人員使用自己的[!DNL Experience Platform]資料集。 完成設定後，[!DNL Adobe Journey Optimizer B2B Edition]可以新增資訊至這些資料集，而不需要建立其他帳戶或人員資料集。

其名稱和可用欄位取決於貴組織的設定。 使用設定的帳戶或個人識別碼來識別相符記錄。 在這些資料集中擁有記錄不會自動讓對象可以使用；可用性取決於您的[!DNL Experience Platform]設定。

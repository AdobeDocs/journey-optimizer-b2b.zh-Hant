---
title: 資料集查詢
description: 瞭解如何在查詢服務中使用SQL查詢範例來分析Adobe Journey Optimizer B2B Edition匯出的帳戶、購買群組、人員和歷程資料。
feature: Reporting, Data Management
role: Admin, Developer
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
feature_v2:
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
    internal-label: Data management
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: 6db81a0b993f450a3ff448dcb4c417e3e81ec70a
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 1%
---

# 資料集查詢

尋找現成的SQL查詢範例，以分析[!DNL Adobe Journey Optimizer B2B Edition]匯出至[!DNL Adobe Experience Platform]的帳戶、人員、購買群組和歷程資料。 若要報告帳戶、購買群組、電子郵件參與和歷程活動，請在[!DNL Query Service]中執行查詢。

如需這些查詢中所使用資料集和欄位的說明，請參閱[匯出的資料集](./aep-exported-datasets.md)。

## 先決條件 {#prerequisites}

在此頁面上執行任何查詢之前，請確定您有下列專案：

* **存取[!DNL Query Service]：**&#x200B;您必須擁有[!DNL Experience Platform]沙箱中[查詢服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/home){target="_blank"}的存取權。
* **可用的資料集：**&#x200B;查詢的目標為匯出的[!DNL Journey Optimizer B2B Edition]個資料集。 在您的沙箱中，前往&#x200B;**[!UICONTROL 資料集]**&#x200B;並確認資料集存在且包含資料。
* **結構描述欄位值：**&#x200B;請確定查詢中的欄位在對應結構描述中有值。 空白欄位不會傳回任何結果，也不會產生錯誤。

>[!NOTE]
>
>範例使用簡短資料表名稱，例如`account_table`和`person_activity_table`。 以沙箱中對應資料集的名稱取代每個表格名稱。 如果資料集名稱包含連字型大小，請以雙引號括住該資料集。 將預留位置值（例如`Example Company`和`PASTE_COMPLETE_JOURNEY_ID_HERE`）取代為您環境中的值。

## 執行查詢 {#run}

若要在此頁面上執行任何範例：

1. 在[!DNL Experience Platform]中，選取&#x200B;**[!UICONTROL 查詢服務]** > **[!UICONTROL 查詢]**。
1. 將範例貼到查詢編輯器中，然後取代表格名稱和預留位置值。
1. 選取&#x200B;**[!UICONTROL 執行]**。

依日期篩選的範例使用過去30天。 若要變更時間範圍，請編輯`INTERVAL '30' DAY`值。

## 選擇查詢

使用下表為您的報告任務選擇查詢。

| 我想 | 前往 |
|---|---|
| 檢閱帳戶名稱、產業和位置 | [檢閱帳戶詳細資料](#account-details) |
| 依參與度比較購買群組 | [比較購買團體參與度](#buying-group-engagement) |
| 尋找與帳戶相關聯的人員 | [尋找帳戶中的人員](#account-people) |
| 追蹤購買群組狀態的變更 | [檢閱購買群組狀態變更](#buying-group-status-changes) |
| 尋找已按一下電子郵件的使用者 | [尋找按一下電子郵件的使用者](#email-clicks) |
| 依型別比較最近活動 | [比較最近的人員活動](#person-activity) |
| 依大小比較帳戶歷程 | [依據歷程比較帳戶計數](#account-journey-counts) |
| 列出歷程中的帳戶 | [列出歷程中的帳戶](#journey-accounts) |
| 追蹤每日帳戶歷程活動 | [追蹤每日帳戶活動](#account-daily-activity) |
| 調查歷程中的帳戶歷史記錄 | [檢閱帳戶歷程時間表](#account-timeline) |
| 依人數和狀態比較個人歷程 | [依據歷程比較人員計數](#person-journey-counts) |
| 列出歷程中的人員 | [列出歷程中的人員](#journey-people) |
| 檢視歷程中的人員 | [依步驟](#person-step-counts)比較人員計數 |
| 追蹤最近的人員歷程活動 | [追蹤最近的歷程活動](#person-journey-activity) |
| 調查歷程中個人的歷史記錄 | [檢閱人員歷程時間表](#person-timeline) |

## 帳戶和購買團體查詢

使用這些查詢來檢閱帳戶、購買群組和可用於報表的人員。

### 檢閱帳戶詳細資料 {#account-details}

請檢閱帳戶名稱、產業、位置和公司大小，以瞭解可用於報告的帳戶。

```sql
SELECT
a._id AS accountID,
a.accountName,
a.industry,
a.country,
a.numberOfEmployees
FROM account_table a
WHERE a.isDeleted = FALSE
ORDER BY a.accountName
LIMIT 100;
```

### 比較購買群組參與度 {#buying-group-engagement}

依據記錄的參與度分數，連同完整度和解決方案興趣，比較購買群組。

```sql
SELECT
bg._id AS buyingGroupID,
bg.buyingGroupName,
bg.engagementScore,
bg.completenessScore,
bg.solutionInterest,
bg.buyingGroupStatus
FROM buying_group_table bg
WHERE bg.isDeleted = FALSE
ORDER BY bg.engagementScore DESC NULLS LAST, bg.buyingGroupName
LIMIT 100;
```

### 尋找帳戶中的人員 {#account-people}

尋找與帳戶相關聯的人員和職稱，以瞭解其連絡人。 以您沙箱中的帳戶名稱取代`Example Company`。

```sql
SELECT DISTINCT
a._id AS accountID,
a.accountName,
p._id AS personID,
p.firstName,
p.lastName,
p.email,
p.jobTitle
FROM account_member_table m
JOIN account_table a ON m.accountID = a._id
JOIN person_table p ON m.personID = p._id
WHERE m.isDeleted = FALSE
AND a.isDeleted = FALSE
AND p.isDeleted = FALSE
AND a.accountName = 'Example Company'
ORDER BY p.lastName, p.firstName
LIMIT 100;
```

### 檢閱購買群組狀態變更 {#buying-group-status-changes}

請檢閱過去30天內購買群組的狀態變更，以瞭解群組在一段時間內的變化。

```sql
SELECT
bg._id AS buyingGroupID,
bg.buyingGroupName,
e.timestamp AS changedAt,
e.newStatus
FROM buying_group_event_table e
JOIN buying_group_table bg ON e.buyingGroupID = bg._id
WHERE bg.isDeleted = FALSE
AND e.eventType = 'buyingGroup.changeStatus'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY e.timestamp DESC
LIMIT 100;
```

## 個人參與查詢

使用這些查詢來檢視電子郵件參與和其他記錄的人員活動。

### 尋找已按一下電子郵件的使用者 {#email-clicks}

若要檢閱最近的電子郵件參與，請識別在過去30天內有記錄電子郵件點按的人員。

```sql
SELECT DISTINCT
p._id AS personID,
p.firstName,
p.lastName,
p.email
FROM person_activity_table e
JOIN person_table p ON e.personID = p._id
WHERE e.isDeleted = FALSE
AND p.isDeleted = FALSE
AND e.eventType = 'directMarketing.emailClicked'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY p.lastName, p.firstName
LIMIT 100;
```

### 比較最近的人員活動 {#person-activity}

比較記錄的活動型別和參與人數，以瞭解最近的參與情形。

```sql
SELECT
e.eventType,
COUNT(*) AS recordedRows,
COUNT(DISTINCT e.personID) AS distinctPeople
FROM person_activity_table e
WHERE e.isDeleted = FALSE
AND e.personID IS NOT NULL
AND e.personID <> ''
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
GROUP BY e.eventType
ORDER BY recordedRows DESC
LIMIT 100;
```

## 帳戶歷程查詢

使用這些查詢來分析帳戶歷程。 將`PASTE_COMPLETE_JOURNEY_ID_HERE`取代為帳戶歷程的`_id`值，並將`PASTE_COMPLETE_ACCOUNT_ID_HERE`取代為帳戶的`_id`值。

### 依歷程比較帳戶計數 {#account-journey-counts}

依狀態和記錄的成員資格計數比較帳戶歷程，以檢視哪些歷程擁有最大的帳戶人口。

```sql
SELECT
j._id AS journeyID,
j.accountJourneyName,
j.accountJourneyStatus,
COUNT(DISTINCT m.accountID) AS accountsWithRecordedMembership
FROM account_journey_table j
LEFT JOIN account_journey_member_table m
ON m.journeyID = j._id
AND m.isDeleted = FALSE
AND m.accountID <> ''
WHERE j.isDeleted = FALSE
GROUP BY j._id, j.accountJourneyName, j.accountJourneyStatus
ORDER BY accountsWithRecordedMembership DESC, j.accountJourneyName
LIMIT 100;
```

### 列出歷程中的帳戶 {#journey-accounts}

檢閱與特定歷程相關聯的帳戶，包括其產業和國家/地區。

```sql
SELECT DISTINCT
a._id AS accountID,
a.accountName,
a.industry,
a.country
FROM account_journey_member_table m
JOIN account_table a ON m.accountID = a._id
WHERE m.isDeleted = FALSE
AND a.isDeleted = FALSE
AND m.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
ORDER BY a.accountName, accountID
LIMIT 100;
```

### 追蹤每日帳戶活動 {#account-daily-activity}

追蹤每日帳戶新增、移除和步驟變更，以瞭解過去30天歷程中的活動。

```sql
SELECT
CAST(e.timestamp AS DATE) AS activityDate,
e.eventType,
COUNT(*) AS recordedRows,
COUNT(DISTINCT e.accountID) AS distinctAccounts
FROM account_activity_table e
WHERE e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.accountID IS NOT NULL
AND e.accountID <> ''
AND e.eventType IN (
'account.addAccountToJourney',
'account.removeAccountFromJourney',
'account.changeAccountJourneyNode'
)
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
GROUP BY CAST(e.timestamp AS DATE), e.eventType
ORDER BY activityDate DESC, e.eventType
LIMIT 100;
```

### 檢閱帳戶歷程時間表 {#account-timeline}

檢閱帳戶記錄的事件和歷程步驟，以調查帳戶最近的歷程記錄。

```sql
SELECT
e.timestamp AS activityAt,
e.eventType,
e.journeyNodeID,
n.nodeType,
e.previousJourneyNodeID,
e.buyingGroupID
FROM account_activity_table e
LEFT JOIN account_journey_node_table n
ON e.journeyNodeID = n._id
AND e.journeyID = n.accountJourneyID
AND n.isDeleted = FALSE
WHERE e.accountID = 'PASTE_COMPLETE_ACCOUNT_ID_HERE'
AND e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY e.timestamp DESC
LIMIT 100;
```

## 個人歷程查詢

使用這些查詢來分析個人歷程。 將`PASTE_COMPLETE_JOURNEY_ID_HERE`取代為人員歷程的`_id`值，並將`PASTE_COMPLETE_PERSON_ID_HERE`取代為人員的`_id`值。

### 依歷程比較人員計數 {#person-journey-counts}

透過記錄的會員計數、狀態和日期來比較個人歷程，以瞭解其規模和生命週期。

```sql
SELECT
j._id AS journeyID,
j.personJourneyName,
j.personJourneyStatus,
j.startDate,
j.endDate,
COUNT(DISTINCT m.personID) AS peopleWithRecordedMembership
FROM person_journey_table j
LEFT JOIN person_journey_member_table m
ON m.journeyID = j._id
AND m.isDeleted = FALSE
AND m.personID <> ''
WHERE j.isDeleted = FALSE
GROUP BY
j._id,
j.personJourneyName,
j.personJourneyStatus,
j.startDate,
j.endDate
ORDER BY peopleWithRecordedMembership DESC, j.personJourneyName
LIMIT 100;
```

### 列出歷程中的人員 {#journey-people}

檢閱和歷程相關聯的對象、上次輸入時間及輸入頻率。

```sql
SELECT DISTINCT
m.personID,
p.firstName,
p.lastName,
p.email,
m.membershipDate,
m.lastEntryDate,
m.entryCount,
m.reentryOpensAt,
m.journeyNodeID
FROM person_journey_member_table m
LEFT JOIN person_table p
ON m.personID = p._id
AND p.isDeleted = FALSE
WHERE m.isDeleted = FALSE
AND m.personID IS NOT NULL
AND m.personID <> ''
AND m.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
ORDER BY m.lastEntryDate DESC NULLS LAST, m.personID
LIMIT 100;
```

### 依步驟比較人員計數 {#person-step-counts}

瞭解如何在歷程成員資格中記錄的步驟間分配人員。

```sql
SELECT
m.journeyNodeID,
n.nodeType,
COUNT(DISTINCT m.personID) AS peopleWithRecordedStep
FROM person_journey_member_table m
LEFT JOIN person_journey_node_table n
ON m.journeyNodeID = n._id
AND m.journeyID = n.personJourneyID
AND n.isDeleted = FALSE
WHERE m.isDeleted = FALSE
AND m.personID IS NOT NULL
AND m.personID <> ''
AND m.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
GROUP BY m.journeyNodeID, n.nodeType
ORDER BY peopleWithRecordedStep DESC, m.journeyNodeID
LIMIT 100;
```

### 追蹤最近的歷程活動 {#person-journey-activity}

比較錄製的歷程開始、結束和轉變，以瞭解過去30天歷程中的個人活動。

```sql
SELECT
e.eventType,
COUNT(*) AS recordedRows,
COUNT(DISTINCT e.personID) AS distinctPeople
FROM person_activity_table e
WHERE e.isDeleted = FALSE
AND e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.personID IS NOT NULL
AND e.personID <> ''
AND e.eventType IN (
'person.journeyAdd',
'person.journeyRemove',
'person.journeyStart',
'person.journeyEnd',
'person.journeyNodeTransition',
'person.journeySplitNode'
)
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
GROUP BY e.eventType
ORDER BY recordedRows DESC, e.eventType
LIMIT 100;
```

### 檢閱人員歷程時間表 {#person-timeline}

調查個人最近的歷程記錄，包括步驟轉變、分割選擇和歷程歸因設定檔更新。

```sql
SELECT
e.timestamp AS activityAt,
e.eventType,
e.journeyNodeID,
e.previousJourneyNodeID,
e.newJourneyNodeID,
e.journeyChoiceNumber,
e.journeyEntryCount,
e.attributeName,
e.attributeOldValue,
e.attributeNewValue
FROM person_activity_table e
WHERE e.isDeleted = FALSE
AND e.personID = 'PASTE_COMPLETE_PERSON_ID_HERE'
AND e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY e.timestamp DESC
LIMIT 100;
```

---
title: 購買群組的完整性分數
description: 使用Journey Optimizer B2B edition中的角色型臨界值、可自訂的成員要求及完整性設定，來計算購買群組完整性分數。
feature: Buying Groups
role: User
source-git-commit: 1ebc27a709e1b82029c22950897505f3945a507f
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 3%

---


# 完整性分數 {#completeness-scores}

>[!CONTEXTUALHELP]
>id="ajo-b2b_buying_group_completeness_score"
>title="完整性分數"
>abstract="完整度分數反映購買群組成員資格對隨時可購買的購買群組的符合程度。"

完整度分數是一個百分比，可指出購買群組在其定義的角色中填入所需成員的程度。 這些分數是根據您在角色範本中設定的角色成員臨界值，以及指定給購買群組中每個角色的實際成員數目。 由此產生的分數可協助行銷人員評估銷售整備，並找出購買群組組合中的差距。 評分計算會在購買群組成員資格變更時自動進行。

![購買群組完整度分數](./assets/buying-group-details-page-completeness-scores.png){width="800" zoomable="yes"}

完整性分數有兩種型別：

* **購買群組完整度分數** — 購買群組完整度分數是介於0%到100%之間的百分比，代表購買群組的整體完整度（根據角色層級的完整度計算）。

  購買群組完整度分數會顯示在[購買群組詳細資料](./buying-group-details.md)頁面中。 此分數可讓您一目瞭然地檢視購買群組是否有銷售參與所需的利害關係人。

* **角色完整度分數** — 角色完整度分數是購買群組中每個個別角色的百分比，根據指派給該角色的成員數目而定。

  當您編輯角色並調整完整度設定時，每個角色的角色完整度分數會顯示在購買群組詳細資訊頁面中。 這些分數可協助您識別哪些特定角色需要額外的成員，才能達到銷售就緒臨界值。

  詳細資訊頁面會顯示前兩個角色完整度分數，以及任何其他角色的n_+連結。 按一下連結，即可檢視其他角色完整度分數。

完整性分數反映購買群組成員資格的目前狀態，並會在新增或移除成員時自動更新。 顯示的分數會以全數百分比顯示（例如，66.67%的分數會顯示為67%）。

## 評估銷售整備

Adobe Journey Optimizer B2B edition提供行銷人員各種工具，確保購買群組符合真正的決策流程。 您可以使用可自訂的角色成員臨界值來定義完整的購買群組，以反映貴組織的銷售方法。 藉由設定每個角色的最低與最高成員需求，您可為構成銷售就緒採購群組的專案建立明確的條件。

購買群組完整度分數可準確衡量群組的銷售整備程度。 例如，若要完成特定解決方案的商機，您可能需要至少兩位決策者、一位影響者和至少一位從業人員。 完整度分數計算會說明每個角色特定需求，提供整體購買群組整備程度的檢視。

## 測量歷程有效性

購買群組完整性可做為歷程有效性的關鍵績效指標(KPI)。 特定歷程的目標可能是將購買群組的完整性提高一定百分比，或在觸發銷售就緒警示之前達到最低臨界值。

在大型企業中，您可以為每個角色識別一個人員。 不過，該人員可能不是銷售的最佳聯絡人，或者您可能需要多個重要角色的聯絡人。 例如，大型組織可能會有數位資訊技術(IT)決策者分散在部門或業務單位之間。 識別一位決策者可能不足以應付複雜的企業銷售。

分析目前購買群組完整性之後，您可以調整角色範本中每個角色的所需聯絡人數量。 這些調整可讓您根據真實世界的模式和銷售結果調整購買群組策略。

<!-- ## Analyze audiences for journey optimization

Marketers can view the starting buying group completeness score of target account audiences to find the best performance indicators for a solution. This visibility enables marketers to:

* Determine if they need to adjust the completeness score requirements for each role to make journeys more effective.
* Identify which buying groups are closest to sales-ready status and prioritize them for acceleration campaigns.
* Segment buying groups by completeness score ranges and create tailored nurture strategies for different maturity levels.

>[!BEGINSHADEBOX]

The buying group completeness score is available to use for filtering in [journey split-path-by-account nodes](../journeys/split-merge-paths-nodes.md#account-path-filters) and for audience segmentation. Role completeness can be used to create personalized content that addresses specific gaps in buying group composition.

>[!ENDSHADEBOX] -->

## 角色完整度計算 {#role-completeness-calculation}

>[!CONTEXTUALHELP]
>id="ajo-b2b_buying_group_role_completeness_calculation"
>title="角色完整度計算"
>abstract="角色完整性分數會根據指派給角色的成員數量以百分比計算。"

Journey Optimizer B2B edition會以百分比計算每個個別購買群組角色的完整度分數。 此分數是以指派給角色的成員數目為基礎，而角色範本[中完成所需的數目則為](./buying-groups-role-templates.md#change-the-completeness-score-settings)。

角色完整度計算是介於零和指定臨界值（需要成員）之間的線性百分比：

* 如果指派的成員數目為&#x200B;**零**，則角色完整度為&#x200B;**0%**。
* 如果指派的成員數目為&#x200B;**等於或超過臨界值**，則角色完整度為&#x200B;**100%**。
* 如果指派的成員數目介於1和臨界值&#x200B;**之間**，則會依比例計算完整性。

### 角色完整性公式

角色完整度百分比的計算公式如下：

```text
Role Completeness % = ((Assigned Members - Threshold) / (Threshold)) × 100
```

其中：

* `Assigned Members` =角色中目前的成員數目
* `Threshold` =角色範本中設定的成員必要值

### 角色完整性範例

下列範例說明不同臨界值設定的角色完整度計算：

| 角色 | 需要成員 | 指派的成員 | 計算 | 角色完整性 |
|------|------------------|------------------|-------------|-------------------|
| 決策者 | 3 | 0 | None | 0% |
|  |  | 1 | 1/3 × 100 | 33% |
|  |  | 2 | 2/3 × 100 | 66% |
|  |  | 3 | 在臨界值 | 100% |
|  |  | 4 | 高於臨界值 | 100% |
| 影響者 | 5 | 0 | None | 0% |
|  |   | 1 | 1/5 × 100 | 20% |
|  |   | 2 | 2/5 × 100 | 40% |
|  |   | 3 | 3/5 × 100 | 60% |
|  |   | 4 | 4/5 × 100 | 80% |
|  |   | 5 | 在臨界值 | 100% |
|  |   | 6 | 高於臨界值 | 100% |

## 購買群組完整性計算 {#buying-group-completeness-calculation}

購買群組完整性分數會彙總個別角色完整性分數。 此計算提供所有已定義角色之購買群組整備程度的整體檢視。

### 購買群組完整性公式

使用下列公式計算購買群組完整性百分比：

```text
Buying Group Completeness % = Σ(Role Completeness %) / Number of defined roles
```

其中：

* `Role Completeness %` =個別角色完整度百分比(0-100%)
* `Σ` =購買群組中所有角色的總和

<!--

## Use completeness scores in journeys

Use buying group completeness scores and role-level completeness scores to optimize your account journeys and personalize engagement strategies.

### Split paths by completeness

Use completeness thresholds in [journey split-path-by-account nodes](../journeys/split-merge-paths-nodes.md#account-path-filters) to route buying groups through different journey paths based on their readiness. For example:

* **High completeness path** (≥70%) - Buying groups that are nearly sales-ready can be routed to sales teams or receive call-to-action campaigns
* **Medium completeness path** (40-69%) - Buying groups in active development receive nurture campaigns focused on filling specific role gaps
* **Low completeness path** (<40%) - Newly formed buying groups receive awareness and education content to build initial engagement

### Trigger actions based on completeness milestones

Set up journey events that trigger specific actions when buying groups reach completeness milestones. FOr example:

* Alert sales teams when a buying group reaches 70% completeness.
* Send a _stakeholder alignment_ campaign when completeness increases by 20% or more within a defined timeframe.
* Trigger an automated assessment when a buying group stalls at the same completeness level for an extended period.

By leveraging completeness scores throughout the journey, you create more targeted, efficient campaigns that align with the actual composition and maturity of your buying groups.

-->
---
title: 購買組的完整性分數
description: 使用基於角色的閾值、可自定義的成員要求和Journey OptimizerB2B版中的完整性設定計算購買組完整性分數。
feature: Buying Groups
role: User
exl-id: 6f54d4ac-9d1a-4009-b9bf-8bc80e4cc63c
source-git-commit: b369ef39715f327fcff7237e827bebf4e82c27f6
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 9%

---

# 完整性分數 {#completeness-scores}

>[!CONTEXTUALHELP]
>id="ajo-b2b_buying_group_completeness_score"
>title="完整性分數"
>abstract="完整度分數反映購買群組成員資格針對立即可購買之購買群組的符合程度。"

完整性分數是一個百分比，它指示採購組在其定義的角色中使用所需成員填充的情況。 這些分數基於您在角色模板中配置的角色成員閾值以及分配給購買組中每個角色的實際成員數。 由此得出的分數有助於營銷人員評估銷售就緒性，並找出採購組構成中的差距。 在購買組成員身份更改時自動進行分數計算。

![正在購買群完整性分數](./assets/buying-group-details-page-completeness-scores.png){width="800" zoomable="yes"}

完整性分數有兩種類型：

* **購買組完整性分數** — 購買組完整性分數是0%到100%之間的百分比，它表示基於角色級別完整性計算的購買組的整體完整性。

  購買群完整性分數顯示在[購買群詳細資訊](./buying-group-details.md)頁中。 此分數提供了購買組是否具有銷售參與所需的利益相關方的概覽視圖。

* **角色完整性得分** — 根據分配給該角色的成員數，角色完整性得分是購買組中每個角色的百分比。

  編輯角色和調整完整性設定時，每個角色的角色完整性分數將顯示在購買組詳細資訊頁面中。 這些分數可幫助您確定哪些特定角色需要額外成員才能達到銷售就緒閾值。

  詳細資訊頁面顯示前兩個角色完整性分數，並帶有n_+連結，用於任何其他角色。 按一下連結查看其他角色完整性得分。

完整性分數反映購買組成員資格的當前狀態，並在添加或刪除成員時自動更新。 顯示的分數顯示為整個百分比（例如，66.67%的分數顯示為67%）。

## 評估銷售就緒性

Adobe Journey OptimizerB2B版為營銷商提供了工具，確保採購小組與真正的決策過程保持一致。 您可以使用反映組織銷售方法的可自定義角色成員閾值來定義完整的採購組。 通過為每個職責設定最低和最高成員要求，您可以為什麼構成銷售就緒型購買組建立明確的標準。

採購組完整性分數提供了組銷售準備情況的準確度量。 例如，要完成特定解決方案的機會，您可能至少需要兩名決策者、一名影響者和至少一名從業人員。 完整性分數計算可計算這些特定於角色的每個要求，從而提供購買組整體就緒性的視圖。

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

Journey Optimizer B2B edition會以百分比計算每個個別購買群組角色的完整度分數。 此分數是以指派給角色的成員數目為基礎，而角色範本](./buying-groups-role-templates.md#change-the-completeness-score-settings)中完成所需的數目則為[。

角色完整度計算是介於零和指定臨界值（需要成員）之間的線性百分比：

* 如果指派的成員數目為&#x200B;**零**，則角色完整度為&#x200B;**0%**。
* 如果指派的成員數目為&#x200B;**等於或超過臨界值**，則角色完整度為&#x200B;**100%**。
* 如果指派的成員數目介於1和臨界值&#x200B;**之間**，則會依比例計算完整性。

### 角色完整性公式

角色完整度百分比的計算公式如下：

```text
Role Completeness % = ((Assigned Members - Threshold) / (Threshold)) × 100
```

其中:

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

其中:

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

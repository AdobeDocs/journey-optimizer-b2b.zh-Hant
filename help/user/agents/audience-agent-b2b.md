---
title: Audience Agent B2B
description: Journey OptimizerB2B Edition中的Audience Agent B2B使用意圖分析和角色對應來建立購買群組，並加速B2B行銷工作流程。
feature: Audiences, AI Assistant
role: User
hidefromtoc: true
source-git-commit: 9cb77da73778c313392af1c42632d6b9e7e92f3b
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# Audience Agent B2B

Audience Agent B2B由[Adobe Experience Platform Agent Orchestrator](https://experienceleague.adobe.com/zh-hant/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-orchestrator)提供技術支援，可在Journey Optimizer B2B edition中使用。 使用此代理程式可提高探索和擴展受眾的效率和成效，加速建立購買群組和順暢的工作流程以進行歷程啟動：

* **_依意圖排列目標對象的優先順序_** — 根據不同對象的產品意圖推斷角色，並簡化行銷活動規劃，減少在對象驗證上所花費的時間。

* **_利用AI偵測購買群組_** — 使用AI、結構化、非結構化資料以及統一的第一方資料，以簡化購買群組探索與建立。

![Audience Agent B2B處於全頁模式](./assets/audience-agent-full.png){width="700" zoomable="yes"}

## Audience Agent功能

| 區域圖 | 作用 | 商業價值 |
| ---- | ------------ | -------------- |
| 意圖分析 | <li> 測量特定產品的帳戶意圖強度（例如低、中和高）。 <li>比較一段時間內的產品興趣趨勢（例如過去&#x200B;_n_&#x200B;天排名最前的產品）。 <li>識別主動顯示對特定產品感興趣的帳戶。 <li>結合帳戶活動與角色涵蓋範圍的表面參與模式。 | <li>協助團隊在適當的時間聚焦於適當的帳戶。 <li>透過使用真正的購買訊號來排定帳戶的優先順序，以改善管道品質。 <li>在競爭者採取行動之前啟用主動參與。 |
| 角色對應 | <li>依產品意向偵測並排名最前角色。 <li>識別購買一或多個產品所涉及的角色。 <li>合理地將角色對應至功能角色（擁護者、決策者、影響者等）。 <li>驗證為何將指定人員視為冠軍。 | <li>確保銷售能夠吸引真正的決策者和影響者。 <li>減少低影響力聯絡人的浪費工作。 <li>根據購買者的力量動態調整外展活動，提高成功率。 |
| 購買群組評估 | <li>評估購買群組的大小（例如，擁有n個以上成員的群組）。 <li>衡量各帳戶的角色涵蓋範圍（例如，x%以下）。 <li>追蹤購買群組內的角色分配和涵蓋範圍差距。 <li>強調最近交易中有冠軍的客戶。 | <li>顯示可能阻礙交易的涵蓋範圍差距。 <li>確保完整的角色表示，強化多執行緒策略。 <li>透過群組層級的參與深入分析改善交易健康追蹤。 |

## 提示範例

這些提示範例示範您可以使用代理程式的一些方式：

* 顯示趨勢視窗：每個產品的最早和最新帳戶產品意向更新。
* 針對`<product>`，列出具有產品意向和評分的購買群組。
* 針對`<product>`，列出角色及其機會量度（獲勝率、會籍率、計數）。
* 對於`<industry>`中的帳戶，`<product>`的平均帳戶角色涵蓋範圍是多少？
* 哪些客戶對任何產品的意圖較低，但仍擁有開放機會（值得培育）？
* 哪些帳戶本週新增了`<account_name>`的新意圖訊號？

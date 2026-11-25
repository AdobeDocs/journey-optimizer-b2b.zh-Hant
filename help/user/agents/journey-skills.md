---
title: B2B的歷程技能
description: 瞭解如何透過同事聊天來準備歷程簡報、檢閱驗證的草稿圖形、設定已儲存的草稿，以及檢查帳戶和個人歷程。
feature: Account Journeys, Person Journeys, Agentic AI
role: User
exl-id: 5d2945ab-4f6c-4d9c-b0a1-1a93dc1849f3
autotag-review: '2026-06-05T16:42:46.785Z'
TQID: 'https://experienceleague.adobe.com/SgjavYf2Tp5yO8s3f0DQexRCUILQRsD5bM6UwmbcgyE'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
subfeature_v2:
  - id: ff10f619-348f-47e3-99bf-3ce4c817cf2c
    internal-label: Agentic AI
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 876251dd1b69fc768c790daf0b9b1482015d69af
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 0%
---
# B2B的歷程技能

使用[!DNL Adobe CX Enterprise Coworker]聊天在[!DNL Adobe Journey Optimizer B2B Edition]中尋找、建立及設定歷程。 從簡短的草稿建立已驗證的草稿，變更已儲存的草稿圖形和重新進入設定，以及設定未設定的節點。 歷程變更會套用至已儲存的草稿，而非作用中的歷程。

如需查詢、建立和規則技能識別碼及其支援的動作，請參閱[同事歷程技能參考](./coworker-overview.md#skills)。 本文提供簡單的準備指南和歷程可觀察性範例：

* [歷程建立指引](#journey-creation-skills)：建立之前請先準備簡報並檢閱草稿。
* [歷程可觀察性指引](#journey-observability-skills)：詢問有關帳戶和人員如何移動使用中歷程的問題。

如需開啟應用程式和開始交談的指示，請使用[同事介面指南](https://experienceleague.adobe.com/zh-hant/docs/coworker/content/chat/ui-guide){target="_blank"}。

## 歷程建立技能 {#journey-creation-skills}

歷程建立技能將簡短轉換為經驗證的帳戶或人員歷程圖表。 它會將具名對象解析為[!DNL Adobe Experience Platform]對象ID，並在建立草稿之前預覽圖形。

在[!DNL Coworker]建立草稿之前，您必須明確核准預覽。 建立技能不會探索對象、設定節點規則、製作訊息副本、發佈或刪除歷程。

### 準備簡報 {#basic-usage}

以自然語言描述您想要的草稿歷程。 包含下列詳細資料：

* 歷程型別：帳戶或人員。
* 現有對象：要使用的對象名稱或ID。
* 歷程流程：要包含的動作、等待和分支。
* 重新輸入設定：帳戶或人員是否可以重新輸入，以及何時可以重新輸入。

包含促銷活動簡介中的相關詳細資料，以便[!DNL Coworker]可以解讀目標。 如果預覽不符合您預期的流程，請調整請求。

![同事聊天中的歷程建立提示。](./assets/coworker-chat-b2b-journey-prompt.png){width="800" zoomable="yes"}

### 檢閱並建立草稿 {#end-to-end-b2b-journey-creation}

在驗證的預覽中檢閱歷程型別、已解析的對象、節點和路徑。 只有在圖表符合您的摘要時，才核准建立。

核准後，[!DNL Coworker]會建立草稿並傳回其連結。 使用後續追蹤請求，透過規則技能設定其未設定的節點。 在應用程式中新增訊息復本，然後完成[歷程檢閱和發佈步驟](../journeys/create-publish-journey.md)。

如需完整的範例，請參閱[建立帳戶歷程](./coworker-overview.md#build-account-journey)。

### 多階段歷程

對於具有多個階段的歷程，請在摘要中說明每個階段的動作、等待和分支。 將圖表結構與您在建立草稿後設定的規則和訊息副本加以區分。

若要修訂已儲存的草稿，請透過建立技能請求圖形或重新輸入變更。 針對未設定節點上的分割條件、動作、事件和動態清單對象，使用規則技能。

## 歷程可觀察性技能 {#journey-observability-skills}

歷程可觀察性技能可讓您詢問關於帳戶和人員如何瀏覽您的B2B歷程的自然語言問題，而不需挖掘歷程地圖、記錄或儀表板。 它們涵蓋兩個主要區域：歷程進展和資料同步可觀察性。

![在[!DNL CX Coworker]](./assets/journey-observability-prompt-response.png){width="800" zoomable="yes"}中的歷程可觀察性提示和回應

### 帳戶層級歷程insight

透過提出以下問題來追蹤特定帳戶在歷程中的流動方式：

* 「給我有關Bodea Cloud帳戶的基本資訊。」
* 「告訴我客戶Northstar Services如何完成ABM Nurture Strategy歷程。」
* 「帳戶Contoso LLC何時開始此歷程？」

### 分割路徑推理和計數

瞭解採用分支的原因，以及每個路徑依循多少人或帳戶：

* 「為什麼帳戶QiDemoAccount24會前往位於分割節點c764a9的美國加州小型技術路徑？」
* 「告訴我分割節點節點459c7c中每個路徑的人數。」
* 「向我展示Account8在聖荷西路徑的人。」

歷程可觀察性技能會分析分割邏輯、帳戶屬性和活動，以說明路由決策和每個路徑的回訪計數或人員清單。

### 人員層級的歷程結果

分析帳戶內或整個歷程的個別結果，這尤其適合用於購買群組分析和追蹤決策者與影響者的行為：

* 「告訴我每個分割路徑的人數，以進行Bodea下一次網路參與歷程。」
* 「列出隱藏略過路徑中的人員。」
* 「讓我看看此帳戶在聖地亞哥位置路徑的人員。」

### 歷程生命週期和時間

擷取歷程或特定帳戶的關鍵時間戳記：

* 「此歷程何時上線？」
* 「第一個帳戶何時進入此歷程？」
* 「帳戶QiDemoAccount50何時開始此歷程？」

### 外部對象和啟用可見性

對於推送至外部管道（例如LinkedIn）的歷程，您可以檢查啟用狀態：

* 「bsmith@acme.com是否位在外部受眾中？」
* 「列出透過ObservabilityExtAudience01啟用至LinkedIn的所有人員。」

### 資料同步和管道可觀察性

歷程可觀察性技能還可以顯示資料同步健康資訊，以協助疑難排解為何帳戶或潛在客戶未包含在歷程中：

* 外部對象匯出工作量度和狀態
* 批次細分排程和完成時間
* 購買群組維護排程
* 工作管理員統計資料（已完成/失敗）
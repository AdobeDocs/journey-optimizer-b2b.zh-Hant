---
title: Journey Optimizer B2B Edition中的AI功能
description: 利用AI功能加速工作流程 — 取得Journey Optimizer B2B Edition的產品知識、疑難排解說明和營運深入分析。
feature: AI Assistant
role: User, Admin
level: Beginner
exl-id: 52ff66d2-1969-4e2c-985a-c75e613368de
autotag-review: '2026-06-05T16:05:30.499Z'
TQID: 'https://experienceleague.adobe.com/4bXkOzwadjZVzhedVO6oQEEV1biaWMZFHEuqey74qek'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
subfeature_v2:
  - id: eb7448d0-50e6-41cc-83e2-a84cd2413491
    internal-label: Operational Insights
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: c2d3ba94927361f7695e901ef9071bdd4ded8f7d
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 7%
---
# Journey Optimizer B2B Edition中的AI功能

使用[!DNL Adobe Journey Optimizer B2B Edition]中的AI功能來產生內容、探索產品知識並取得營運見解。

>[!IMPORTANT]
>
>您必須先與[使用者准則](https://www.adobe.com/tw/legal/licenses-terms/adobe-gen-ai-user-guidelines.html){target="_blank"}達成協定，才能在[!DNL Journey Optimizer B2B Edition]中使用AI功能。 此合約也包含公開測試版合約，以便於您可在推出時使用其他啟用AI的功能。

+++檢視使用者合約介面

![使用者合約的第一頁。](./assets/user-agreement-1.png)

![使用者合約的最後一頁。](./assets/user-agreement-2.png)

+++

## 使用[!DNL Coworker]應用程式 {#coworker-app}

將[!DNL CX Enterprise Coworker]應用程式介面用於產生內容以外的所有聊天工作流程。 提出產品問題、探索營運見解，並針對B2B帳戶和人員使用[歷程技能](../agents/journey-agent.md)和[對象技能](../agents/audience-agent-b2b.md)。 在[!DNL Journey Optimizer B2B Edition]內仍可產生內容。

如需開啟應用程式、開始交談及使用聊天功能的說明，請參閱[CX Coworker介面指南](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}。

在提交[!DNL Coworker]聊天查詢之前，先考慮您需要的查詢型別。

### 產品知識

產品知識是指以[!DNL Adobe Experience League]上的[!DNL Journey Optimizer B2B Edition]檔案為基礎的概念和主題。 產品知識問題可進一步指定到下列子群組中：

| 產品知識 | 範例 |
| --- | --- |
| 點式學習 | <li>什麼是購買群組？ <li> 是否要顯示購買群組角色範本的範例？ |
| 開放式探索 | <li>建立購買群組的步驟為何？ <li>如何在購買群組角色範本中使用自訂欄位？ |
| 疑難排解 | <li>為什麼沒有為我的歷程建立購買群組？ <li>為什麼我在歷程中找不到要聆聽的體驗事件？ |

### 運作洞察

_營運深入分析_&#x200B;是指[!DNL Coworker]針對您的中繼資料物件（屬性、帳戶對象、資料流程、資料集、目的地、帳戶歷程、結構描述、來源、購買群組範本和解決方案興趣）產生的答案。 這些見解包括計數、查閱和歷程影響。 他們不會檢視沙箱中的任何資料。

* 哪個帳戶對象的對象人數最多，該人數為何？
* 有多少帳戶對象從未在任何歷程中使用過？
* 哪些作用中歷程使用方案興趣&#x200B;_x_？

您可以在下列網域中提出有關營運見解的[!DNL Coworker]問題：

| 網域 | 支援的中繼資料 | 不支援的中繼資料 |
| --- | --- | --- |
| 屬性/欄位 | <li>屬性名稱搜尋 <li>屬性 — 結構描述關係 <li>屬性 — 資料集關係 <li>屬性 — 對象關係 <li>屬性 — 目的地關係 | <li>屬性類別 <li>稽核 <li>淘汰狀態 <li>標籤 <li>儲存在屬性中的值 |
| 帳戶對象&#x200B;<br><br>**_附註:_**&#x200B;在[!DNL Journey Optimizer B2B Edition]內容中，[!DNL Coworker]聊天只能回答帳戶對象的對象問題。 在[!DNL Adobe Experience Platform]內容中，[!DNL Coworker]聊天只能回答個人對象的問題。 | <li>客群計數 <li>對象型別（串流或批次） <li>建立/修改日期 <li>啟用狀態 <li>成員計數 <li>複製對象 <li>名稱和ID搜尋 | <li>客群重疊 <li>客群啟用 <li>稽核 <li>建立/修改 <li>標籤 <li>成員資格趨勢 |
| 資料流 | <li>資料流計數 <li>資料流程狀態 <li>資料流 — 資料集關係 <li>資料流 — 來源關係 | <li>建立/修改 <li>資料流 — 批次關係 <li>擷取設定檔計數 |
| 資料集 | <li>資料集計數 <li>設定檔啟用狀態 <li>建立/修改日期 <li>資料集 — 結構描述關係 <li>資料集 — 對象關係 <li>資料集 — 屬性關係 <li>資料集 — 資料流關係 <li>名稱搜尋 <li>名稱和ID搜尋 | <li>稽核 <li>建立者 <li>資料集 — 批次關係 <li>資料集建立/修改 <li>資料集大小 <li>設定檔數 <li>列數 <li>值搜尋 |
| 目的地 | <li>設定的目的地計數 <li>目的地 — 對象關係 <li>目的地屬性關係 | <li>帳戶設定 <li>帳戶認證資訊 <li>啟用的不重複設定檔 |
| 歷程（帳戶歷程） | <li>計數 <li>名稱和ID搜尋 <li>歷程狀態 <li>建立/修改日期 | <li>屬性 — 歷程關係 <li>稽核 <li>建立/修改 <li>建立者 |
| 結構描述 | <li>結構描述計數 <li>建立/修改日期 <li>結構描述 — 屬性關係 <li>結構描述 — 資料集關係 <li>結構描述 — 對象關係 <li>設定檔啟用狀態 <li>名稱搜尋 <li>名稱和ID搜尋 | <li>稽核 <li>建立/修改 <li>建立者 <li>欄位群組 <li>身分識別 <li>身分識別命名空間 <li>標籤 <li>設定檔數 |
| 來源 | <li>帳戶計數 <li>帳戶狀態 <li>每個帳戶的作用中/非作用中資料流 <li>Source聯結器 — 資料流關係 <li>Source帳戶 — 資料流關係 | <li>帳戶認證資訊 <li>帳戶設定資料擷取量度 <li>設定檔數來源 — 批次關係 |
| 購買群組範本 | <li>計數 <li>狀態 <li>角色 <li>名稱和ID搜尋 | <li>角色規則 |
| 解決方案興趣 | <li>計數 <li>狀態 <li>解決方案興趣 — 購買群組範本關係 <li>名稱和ID搜尋 | <li>解決方案興趣 — 購買群組關係 |

{style="table-layout:fixed"}

若是操作見解問題，答案可能不會反映UI的目前狀態。 支援這些問題的資料每24小時更新一次。 例如，使用者在白天在[!DNL Adobe Real-Time Customer Data Platform]中所做的變更會在夜間與資料存放區同步，然後可在早上讓使用者提問。 若要查詢與物件相關的特定資料，請登入沙箱。

### 隱私權、安全性和治理

在[!DNL Journey Optimizer B2B Edition]中的[!DNL Coworker]聊天會優先處理隱私權、安全性和治理。 檢閱下列資訊，瞭解您可在[!DNL Coworker]聊天中期望的以客戶信任為中心的功能：

* [!DNL Coworker]目前未使用個人資料，即使用於訓練目的。

* 您可以檢視您先前與[!DNL Coworker]聊天互動的30天記錄。

* [!DNL Coworker]在回應提示時以沙箱特定的資料和公共Adobe檔案為基礎。 資料不會跨沙箱共用。

* 您提供給[!DNL Coworker]聊天室的提示未分享給其他客戶。

## 後續步驟

大致瞭解[!DNL Coworker]聊天後，繼續啟用並在工作流程期間使用。 如需詳細資訊，請參閱下列檔案：

* [啟用AI功能存取](./enable-ai-access.md)
* [問題指引](./question-guidance.md)
* [CX Coworker介面指南](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}

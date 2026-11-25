---
title: Adobe Journey Optimizer B2B Edition中的同事
description: 瞭解如何使用CX Enterprise Coworker來尋找、建立及設定帳戶和個人歷程、檢閱草稿預覽以及核准歷程建立。
feature: Account Journeys, Person Journeys, Agentic AI
role: User
level: Beginner
autotag-review: '2026-11-24T23:47:29.469Z'
TQID: 'https://experienceleague.adobe.com/gkizS-MB6qEMoG1pMqD3tSCBtcEuv-m-GMD5H6Z4JsY'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: 9b63d357-750f-5558-9208-62fc8a356785
    internal-label: Approval
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: c2f21a5c-bae4-56c6-97e3-2fc9a0e6c120
    internal-label: Use Cases
subfeature_v2:
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 81b4844bc7b333baaa2218639a542fefd512102f
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 1%
---

# [!DNL Adobe Journey Optimizer B2B Edition]中的[!DNL CX Enterprise Coworker] {#coworker-overview}

使用[!DNL Adobe CX Enterprise Coworker]聊天完成[!DNL Adobe Journey Optimizer B2B Edition]中的工作。 以簡單的語言描述目標。 [!DNL Coworker]計畫工作、執行工作、驗證結果，並提交工作供您核准。

尋找現有帳戶和個人歷程、建立新的草稿歷程或更新已儲存的草稿。 [!DNL Coworker]將您的簡報轉換為已驗證的歷程圖，並在建立草稿之前加以預覽。 在[!DNL Coworker]建立歷程之前，您必須明確核准預覽。

[!DNL Coworker]尊重您組織的現有[產品許可權](../admin/user-management.md#b2b-product-permissions)。 您只能執行已允許您執行的動作。 管理員可控制您何時擁有寫入許可權。 如需存取需求，請參閱[啟用AI存取](../ai-coworker/enable-ai-access.md)。

[!DNL Coworker]在Adobe生態系統中運作，不只在[!DNL Journey Optimizer B2B Edition]中運作。 如需更廣泛的功能，請參閱[Adobe CX Enterprise Coworker聊天總覽](https://experienceleague.adobe.com/en/docs/coworker/content/chat/overview){target="_blank"}。 如需開啟應用程式和開始交談的指示，請使用[同事介面指南](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}。

## 歷程技能 {#skills}

使用這三種技能來檢查歷程、建置歷程圖表並設定節點。 技能識別碼是準確的技術名稱。

| 技能 | 協助您完成的工作 | 超出技能範圍 |
| --- | --- | --- |
| `journey-lookup-ajob2b` | 列出、計數、尋找及說明帳戶和個人歷程。 檢查節點、重新進入設定，以及歷程使用的活動、屬性或事件對象。 此技能不會改變歷程。 | 建立或變更歷程、設定規則、製作訊息副本、管理購買群組範本、發佈或刪除。 |
| `journey-creation-ajob2b` | 將簡報轉換為歷程。 Select歷程型別、將對象解析為[!DNL Adobe Experience Platform]對象ID、驗證圖形，以及進行預覽。 在明確核准後建立草稿。 編輯已儲存草稿的圖形及重新進入設定。 | 查詢現有歷程、設定規則、製作訊息副本、管理購買群組範本、探索對象、發佈或刪除。 |
| `journey-rules-ajob2b` | 在儲存之歷程的未設定節點上，設定分割條件、動作、事件和動態清單對象。 | 變更圖表、查詢歷程、製作電子郵件或簡訊副本、探索對象或發佈。 |

如需其他提示指引，請參閱[B2B的歷程技能](./journey-skills.md)。 若要使用帳戶和人員對象，請參閱[B2B帳戶和人員的對象技能](./audience-skills-b2b.md)。

## 使用案例範例 {#use-cases}

使用不同的請求來建立草稿、設定其節點及檢查現有歷程。

### 建立帳戶歷程 {#build-account-journey}

從簡介建立帳戶培養歷程，然後設定其節點。

範例提示： _為Enterprise Target帳戶對象建立帳戶歷程，傳送歡迎電子郵件、等待三天，然後傳送案例研究電子郵件。_

1. 說明[!DNL Coworker]聊天中的對象和歷程流程。
1. 檢閱驗證的歷程圖表和預覽。 [!DNL Coworker]將具名對象解析為[!DNL Experience Platform]對象ID。
1. 明確核准預覽。 [!DNL Coworker]建立草稿並傳回其連結。
1. 要求[!DNL Coworker]設定草稿的未設定節點。
1. 在[!DNL Journey Optimizer B2B Edition]中開啟草稿以新增訊息復本並檢閱歷程。

結果是一個草稿歷程，而不是發佈的歷程。 完成應用程式中的[歷程檢閱和發佈步驟](../journeys/create-publish-journey.md)。

### 檢查並更新歷程 {#inspect-update-journeys}

檢閱您的歷程詳細目錄，然後調整已儲存草稿的分割條件和重新進入設定。

查詢提示範例： _目前有多少帳戶歷程？ 顯示journey 14251帳戶正在等候的位置。_

1. 請依狀態詢問[!DNL Coworker]歷程計數，或依名稱或ID尋找歷程。
1. 檢閱每個節點的歷程詳細資料和帳戶計數。
1. 識別要更新的已儲存草稿。
1. 要求[!DNL Coworker]設定其分割條件。 例如： _若為草稿歷程14252，請讓高意圖分支需要造訪定價頁面。_
1. 要求重新輸入變更。 例如： _對於草稿歷程14252，請在30天內防止帳戶重新進入。_

變更會套用至儲存的草稿。 發佈是獨立的步驟。 如需設定詳細資訊，請參閱[分割及合併路徑](../journeys/split-merge-paths-nodes.md)和[歷程重新進入](../journeys/journey-re-entry.md)。

## MCP工具 {#mcp-tools}

[!DNL Coworker]使用下列模型內容通訊協定(MCP)工具處理歷程工作。 讀取工具檢查現有資訊，檢查工具驗證圖形，以及寫入工具變更歷程設定或草稿。

| 工具 | 支援的動作 | 類型 |
| --- | --- | --- |
| `list_account_journeys` | 傳回帳戶歷程的分頁清單。 | 讀取 |
| `list_person_journeys` | 傳回人員歷程的分頁清單。 | 讀取 |
| `count_account_journeys` | 依州別計算帳戶歷程次數。 | 讀取 |
| `count_person_journeys` | 依州別計算個人歷程次數。 | 讀取 |
| `get_journey` | 讀取歷程節點及重新進入設定。 | 讀取 |
| `get_journey_rules` | 讀取歷程未設定節點的設定目標。 | 讀取 |
| `get_journey_node_catalog` | 傳回`ruleset_types`，這是規則資料的有效輸入。 | 讀取 |
| `validate_journey_graph` | 驗證已編寫的草稿圖形。 | 檢查 |
| `create_journey` | 使用`confirm=false`預覽歷程。 在明確核准後，建立草稿並傳回其連結。 | 寫入 |
| `update_journey` | 變更已儲存草稿歷程的圖形。 | 寫入 |
| `set_journey_reentry` | 變更重新進入設定。 | 寫入 |
| `set_journey_split_conditions` | 設定分割分支條件。 | 寫入 |
| `apply_journey_rules` | 針對條件、動作、事件和動態清單對象套用`rule_data`至歷程。 | 寫入 |

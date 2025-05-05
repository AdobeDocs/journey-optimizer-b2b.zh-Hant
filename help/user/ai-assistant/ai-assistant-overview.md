---
title: Journey Optimizer B2B edition中的AI助理
description: 預留位置
feature: AI Assistant
level: Beginner
exl-id: 52ff66d2-1969-4e2c-985a-c75e613368de
source-git-commit: f09f3f5b7d4419ead5308e4c5be3b518b4e16ff5
workflow-type: tm+mt
source-wordcount: '1243'
ht-degree: 4%

---

# Journey Optimizer B2B edition中的AI助理

Journey Optimizer B2B edition中的AI助理是從Adobe Experience Platform[&#128279;](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ai-assistant/home)中AI助理的相同技術基礎建立的。 這是一種對話式體驗，可用來加速Adobe Journey Optimizer B2B edition的工作流程。 您可以使用 AI 助手更深入地了解產品功能、排查問題或搜尋資訊，並查找旅程優化版的運營見解B2B。

>[!IMPORTANT]
>
>您需要同意用戶指南[&#128279;](https://www.adobe.com/tw/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html)，才能在 Journey Optimizer B2B 版中使用 AI 助手。此協定還包含公開測試版協定，以便你可以在其他 AI 助手功能以測試版功能推出時使用這些功能。

+++檢視用戶協議介面

![用戶協定的第一頁面。](./assets/user-agreement-1.png)

![使用者合約的最後一頁。](./assets/user-agreement-2.png)

+++

## Journey Optimizer B2B Edition 的 AI Assistant 功能

為了對您提交的問題做出回應，AI 助手會查詢資料庫並將資料庫中的數據轉換為人類可讀的答案。 此回應是基礎數據的內部表示，也稱為&#x200B;_&#x200B;**_知識圖譜_**&#x200B;_ - 給定答案的概念，數據和中繼資料的綜合網路。 知識圖譜由子圖組成，每當提交查詢時都會引用這些子圖：

* Experience League 檔。
* 作工件，例如架構、欄位、受眾和旅程。

在提交 AI 助手查詢之前，請考慮您需要哪種類型的查詢：

### 產品知識

產品知識是指以Adobe Experience League上的Journey Optimizer B2B edition檔案為根據的概念和主題。 產品知識問題可進一步指定到下列子群組中：

| 產品知識 | 範例 |
| --- | --- |
| 點式學習 | <li>什麼是購買群組？ <li> 是否要顯示購買群組角色範本的範例？ |
| 開啟探索 | <li>建立購買群組的步驟為何？ <li>如何在購買群組角色範本中使用自訂欄位？ |
| 疑難排解 | <li>為什麼沒有為我的歷程建立購買群組？ <li>為什麼我在歷程中找不到要聆聽的體驗事件？ |

### 營運分析

_營運深入分析_&#x200B;參考由AI助理產生的中繼資料物件（屬性、帳戶對象、資料流、資料集、目的地、帳戶歷程、結構描述、來源、購買群組範本和解決方案興趣）相關答案。 這些見解包括計數、查閱和歷程影響。 他們不會檢視沙箱中的任何資料。

* 哪個帳戶對象的對象人數最多，該人數為何？
* 有多少帳戶對象從未在任何歷程中使用過？
* 哪些作用中歷程使用方案興趣&#x200B;_x_？

您可以在下列網域中向AI Assistant詢問有關您的營運見解的問題：

| 網域 | 支援的中繼資料 | 不支持的中繼資料 |
| --- | --- | --- |
| 屬性/欄位 | <li>属性名稱搜尋 <li>屬性 - 綱要關係 <li>屬性 - 資料集關係 <li>屬性 — 對象關係 <li>屬性 — 目的地關係 | <li>屬性類別 <li>稽核 <li>淘汰狀態 <li>標記 <li>儲存在屬性中的值 |
| 帳戶對象&#x200B;<br><br>**_注意：_**&#x200B;AJO B2B AI助理只能回答帳戶對象的對象問題，而Experience Platform AI助理只能回答個人對象的問題 | <li>客群計數 <li>對象型別（串流或批次） <li>建立/修改日期 <li>啟用狀態 <li>會員計數 <li>重複的物件 <li>名稱和 ID 搜尋 | <li>客群重疊 <li>客群啟用 <li>稽核 <li>建立/修改 <li>標記 <li>成員資格趨勢 |
| 資料流 | <li>數據流計數 <li>資料流程狀態 <li>數據流 - 資料集關係 <li>數據流 - 源關係 | <li>建立/修改 <li>數據流-批處理關係 <li>引入設定檔計数 |
| 資料集 | <li>數據集計數 <li>配置檔啟用狀態 <li>創建/修改日期 <li>資料集 — 結構描述關係 <li>資料集 — 對象關係 <li>資料集 — 屬性關係 <li>資料集 — 資料流關係 <li>名稱搜尋 <li>名稱和ID搜尋 | <li>稽核 <li>建立者 <li>資料集 — 批次關係 <li>資料集建立/修改 <li>資料集大小 <li>設定檔數 <li>列數 <li>值搜尋 |
| 目的地 | <li>設定的目的地計數 <li>目的地 — 對象關係 <li>目的地屬性關係 | <li>帳戶設定 <li>帳戶認證資訊 <li>啟用的不重複設定檔 |
| 歷程（帳戶歷程） | <li>計數 <li>名稱和ID搜尋 <li>歷程狀態 <li>建立/修改日期 | <li>屬性 — 歷程關係稽核 <li>建立/修改 <li>建立者 |
| 結構描述 | <li>結構描述計數 <li>建立/修改日期 <li>結構描述 — 屬性關係 <li>結構描述 — 資料集關係 <li>結構描述 — 對象關係 <li>設定檔啟用狀態 <li>名稱搜尋 <li>名稱和ID搜尋 | <li>稽核 <li>建立/修改 <li>建立者 <li>欄位群組 <li>身分識別 <li>身分識別命名空間 <li>標記 <li>設定檔數 |
| 來源 | <li>帳戶計數 <li>帳戶狀態 <li>每個帳戶的活動/非活動数据流 <li>來源連接器 - 數據流關係 <li>來源帳戶 - 數據流關係 | <li>帳戶憑證資訊 <li>帳戶設定數據擷取量度 <li>設定檔數來源 — 批次關係 |
| 購買群組範本 | <li>計數 <li>狀態 <li>角色 <li>名稱和 ID 搜尋 | <li>角色規則 |
| 解決方案興趣 | <li>計數 <li>狀態 <li>解決方案興趣 — 購買群組範本關係 <li>名稱和ID搜尋 | <li>解決方案興趣 — 購買群組關係 |

{style="table-layout:fixed"}

對於運營見解問題，答案可能無法反映UI的當前狀態。 支援這些問題的數據每 24 小時更新一次。 例如，使用者在白天在即時 CDP 中所做的更改在晚上與數據存儲同步，然後在早上可用於用戶問題。 登錄沙箱查詢與對象相關的特定數據。

### 功能範圍

目前，AI 助手範圍如下：

* [產品知識](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/home#product-knowledge)：AI助手可以回答即時客戶數據Platform和Adobe Systems旅程優化B2B版的產品知識問題。

* [運營見解](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/home#operational-insights)：可以向 AI Assistant 提問，以獲取以下數據物件的作見解：屬性、帳戶受眾、數據流、數據集、目標、帳戶旅程、架構、源、購買群組範本和解決方案興趣。

### 隱私、安全和治理

Journey Optimizer B2B Edition 中的 AI Assistant 在構建時將隱私、安全性和治理放在首位。 查看以下信息，了解可以從 AI 助手獲得的客戶以信任為中心的功能：

* 目前，AI Assistant 不使用任何個人數據，平均用於培訓目的。

* AI Assistant不知道客戶資料，例如人員、帳戶、機會和購買群組。

* 您必須有明確的許可權才能與AI助理互動。

   * 管理員可以使用[許可權UI](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions)和[Admin Console](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/browse)來設定許可權。

   * 許可權很細微，您的沙箱管理員可以設定哪些使用者可以提出不同的問題類別（使用AI Assistant的產品知識型問題或操作深入分析的問題）。

* 您可以透過30天保留原則檢視您先前與AI助理互動的記錄。

* AI助理在回應使用者提示時是以沙箱特定的資料和公共Adobe檔案為基礎。 資料不會跨沙箱共用。

* 您提供給AI助理的提示不會分享給其他客戶。

### 常見問題

以下是有關Journey Optimizer B2B edition中AI Assistant常見問題的回答清單。

**是否即時提供AI助理的資訊？**

AI助理回應中顯示的資料每天都會更新。 此週期表示回應中包含的資料可能會比使用者介面中回應時顯示的資料晚24小時。

**AI助理有哪些功能？**

AI Assistant可以解決Adobe產品知識查詢，並可回答與您的營運成品營運見解相關的問題。

**AI助理可以提供客戶資料的相關資訊嗎？**

不可以。 AI助理無法存取客戶資料，因此AI助理不會檢視或使用這些資料。

**我的個人資訊是否用於AI助理的訓練資料？**

AI助理不會將個人資訊用於訓練目的。 請勿向AI助理提供任何關於您自己（包括您的姓名或聯絡資訊）或任何其他方的個人資訊。

## 後續步驟

大致瞭解AI助理後，請繼續在工作流程中啟用並使用AI助理。 如需詳細資訊，請參閱下列檔案：

* [啟用AI助理存取](./enable-ai-assistant-access.md)
* [問題指導](./question-guidance.md)
* [使用 AI 助理](./use-ai-assistant.md)

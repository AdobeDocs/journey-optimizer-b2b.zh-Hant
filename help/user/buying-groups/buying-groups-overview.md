---
title: 購買群組
description: 瞭解在Journey Optimizer B2B edition中購買群組如何透過識別及鎖定帳戶清單中的成員來提高行銷效率。
feature: Buying Groups
exl-id: ddcd7b62-6a76-4f5e-b6d3-a20944ca8332
source-git-commit: 8b2cfac4785e95e4fb994ac87068f59add40171d
workflow-type: tm+mt
source-wordcount: '1788'
ht-degree: 9%

---


# 購買群組

針對B2B銷售和行銷活動，帳戶是任何策略的關鍵。 每個帳戶都有一組與之相關聯的人員，這些人員可能是帳戶的員工或與帳戶合作的承包商。 帳戶是階層式的，不同的產品可能會在階層中的不同層級出售。 例如，Adobe Experience Platform可能會在公司層級銷售給頂層帳戶，而Adobe Photoshop可能會銷售給代表組織內某個部門或部門的帳戶，例如較大公司內的設計部門。

![帳戶角色圖表](assets/account-roles-diagram.png){width="800"}

在帳戶內，可能有一部分人組成&#x200B;_購買群組_。 這些是最終做出購買決策的人，因此需要行銷人員特別關注，並且可能需要傳送給他們的不同資訊，不同於與帳戶相關聯的其他人。 購買群組可能包含不同產品線或方案的不同群組。 例如，網路安全產品通常需要首席資訊官或首席安全官，以及法律部門的代表來核准購買，但錯誤追蹤產品通常會有工程部副總和IT主管作為購買群組的成員。

![影片](../../assets/do-not-localize/icon-video.svg){width="30"} [觀看影片概述](#overview-video)

## 主要元件

您可以在Journey Optimizer B2B edition中建立購買群組，根據您的銷售團隊負責銷售的解決方案，找出目標帳戶清單中缺少的成員，藉此提高行銷效率。 在您和您的行銷團隊開始建立購買群組之前，請確定您已定義關鍵元件。 這些元件對於達成您的業務目標至關重要。

| 元件 | 用途 |
| --------- | ------- |
| 解決方案興趣 | 此元件提供下列問題的答案： <ul><li>身為行銷組織，您銷售什麼？</li><li>您打算銷售什麼產品或產品系列？</li></ul>  **_範例：_**&#x200B;交叉銷售新產品X給現有客戶 |
| 帳戶客群 | 此元件提供下列問題的答案： <ul><li>您銷售給誰？</li><li>您正在定位的帳戶清單為何？</li></ul> **_範例：_**&#x200B;由收入超過100萬的產品Y帳戶定義的帳戶區段 |
| 購買群組角色範本 | 此元件提供下列問題的答案： <ul><li>您鎖定哪些角色？</li><li>哪一組規則可用於決定指派給購買群組角色的人員？</li></ul>  **_範例：_**&#x200B;將具有CMO職稱的人員指派給決策者角色 |
| 購買群組階段 | （選用）此元件提供下列問題的答案：購買群組如何追蹤成功或失敗？ |

## 購買群組工作流程

1. 建立購買群組。

   選項：
   * 使用[方案興趣](./solution-interests.md)和[角色範本](./buying-groups-role-templates.md)
   * 使用協力廠商匯入
   * 從AI/ML產生

1. 識別失蹤人員。

   使用篩選器分析購買群組。

   **_範例：_**&#x200B;決策者角色遺失，完整度分數&lt; 50

1. 完成購買群組定義。
<!--
   * Acquire missing people
   * Send to LinkedIn Destination
   * Enrich with Zoominfo -->

1. 在帳戶歷程中，透過關聯的解決方案興趣使用。

## 檢視購買群組和元件

在左側導覽列中，展開&#x200B;**[!UICONTROL 帳戶]**&#x200B;並按一下&#x200B;**[!UICONTROL 購買群組]**。

「_[!UICONTROL 購買群組]_」頁面會整理為索引標籤：

| 標記 | 說明 |
| --- | ----------- |
| [!UICONTROL 概觀] | 此標籤是預設標籤，會顯示[購買群組儀表板](../dashboards/buying-groups-dashboard.md)。 |
| [!UICONTROL 瀏覽] | 此索引標籤支援下列活動： <ul><li>檢視現有購買群組的清單。 </li><li>依購買群組名稱搜尋。 </li><li>依解決方案興趣篩選。 </li><li>深入到購買群組詳細資訊。 </li><li>建立購買群組。 刪除購買群組。</li></ul> |
| [!UICONTROL 方案興趣] | 此索引標籤支援下列活動： <ul><li>檢視現有購買群組的清單。 </li><li>依購買群組名稱搜尋。 </li><li>存取及編輯解決方案興趣屬性。 </li><li>建立解決方案的興趣。 </li><li>刪除解決方案興趣。 </li><li>檢視並刪除購買群組工作。 </li></ul> |
| [!UICONTROL 角色範本] | 此索引標籤支援下列活動： <ul><li>檢視現有角色範本的清單。 </li><li>依角色範本名稱搜尋。 </li><li>存取及編輯角色範本屬性和條件。 </li><li>建立角色範本。 </li><li>刪除角色範本。 </li></ul> |
| [!UICONTROL 階段] | 此索引標籤支援下列活動： <ul><li>檢視現有的購買群組階段模型。 </li><li>存取及編輯草稿購買群組階段模型。 </li><li>建立購買群組階段模型。 </li></ul> |

## 購買群組搜尋和篩選

使用&#x200B;_[!UICONTROL 瀏覽]_&#x200B;標籤檢視購買群組清單。 您可以依名稱搜尋，並依解決方案興趣篩選清單。

![購買群組瀏覽頁面](assets/buying-groups-browse.png){width="800" zoomable="yes"}

## 購買群組詳細資料

若要存取購買群組的詳細資料，請從&#x200B;_[!UICONTROL 瀏覽]_&#x200B;標籤按一下購買群組名稱。 [了解更多](./buying-group-details.md)

![購買群組詳細資料](assets/buying-group-details.png){width="600" zoomable="yes"}

### 購買群組完整性分數

完整性分數是用來判斷購買群組是否完整，這表示它擁有指派給角色的正確成員，並準備好用於帳戶歷程中。 此分數是購買群組內角色數量的百分比，以及有多少角色至少指派給一個銷售機會。

例如，如果購買群組中有四個角色，且四個角色中的三個至少指派給一個潛在客戶，則購買群組的完成度為75%。

每次建立或更新購買群組時，都會重新計算購買群組完整度分數。

### 購買群組參與分數

購買群組參與分數是一個數字，可根據購買群組成員執行的活動來決定其參與度。

* 當產生購買群組時，即會開始計算參與分數。
* 購買群組成員在過去30天內執行的任何傳入活動都會用來計算分數。
* 若為30天期間，當活動到期時，分數可能會下降。
* 每個活動的每日頻率上限為20。 如果購買群組的成員每天執行相同活動超過20次，則活動的計數上限為20次，但數字不會更高。
* 顯示的分數會四捨五入。 例如，分數75.89999會顯示為76。

+++用於評分的活動

| 活動名稱 | 說明 | 參與類型 | 最大每日頻率計數 | 活動權重 |
| --- | --- | --- | --- | --- |
| 報名活動 | 註冊與行銷活動相關聯的事件 | 活動 | 20 | 60 |
| 出席活動 | 出席行銷活動活動 | 活動 | 20 | 90 |
| 開啟電子郵件 | 開啟電子郵件 | 電子郵件 | 20 | 30 |
| 按一下電子郵件 | 按一下電子郵件中的連結 | 電子郵件 | 20 | 30 |
| 開啟銷售電子郵件 | 開啟銷售郵件 | 電子郵件 | 20 | 30 |
| 按一下銷售電子郵件 | 按一下銷售電子郵件中的連結 | 電子郵件 | 20 | 30 |
| 有趣的時刻 | 有一個有趣的時刻 | 已監管 | 20 | 60 |
| 點選推播通知 | 接收推播通知 | 行動 | 20 | 30 |
| 行動應用程式活動 | 在行動應用程式上執行活動 | 行動 | 20 | 30 |
| 行動應用程式工作階段 | 在行動應用程式工作階段中處於作用中 | 行動 | 20 | 30 |
| 填寫Facebook潛在客戶廣告表單 | 在Facebook頁面上填寫並提交潛在客戶廣告表單 | 社交 | 20 | 30 |
| 按一下RTP呼叫動作 | 按一下個人化呼叫動作 | Web | 20 | 60 |
| 檢視應用程式內訊息 | 檢視應用程式內訊息 | 行動 | 20 | 30 |
| 點選應用程式內訊息 | 點選應用程式內訊息 | 行動 | 20 | 30 |
| 訂閱簡訊 | 訂閱簡訊通訊 | 簡訊 | 20 | 90 |
| 回覆銷售電子郵件 | 回覆銷售電子郵件 | 電子郵件 | 20 | 30 |
| 與對話方塊互動 | 使用Dynamic Chat對話方塊 | 聊天 | 20 | 90 |
| 在對話方塊中與檔案互動 | 在Dynamic Chat對話方塊中與檔案互動 | 聊天 | 20 | 90 |
| 對話方塊中已排程的會議 | 在Dynamic Chat對話方塊中排程約會 | 聊天 | 20 | 90 |
| 已達到對話方塊目標 | 在Dynamic Chat對話方塊中達到目標 |  | 20 | 90 |
| 已回覆網路研討會中的投票 | 回應網路研討會事件中的輪詢 | 聊天 | 20 | 90 |
| 網路研討會中點選的呼叫動作 | 按一下網路研討會事件中的行動號召連結 | 呼叫 | 20 | 30 |
| 網路研討會中的資產下載 | 下載網路研討會活動中的檔案/資產 | 活動 | 20 | 60 |
| 於網路研討會中提出問題 | 在網路研討會活動中提出問題 | 活動 | 20 | 60 |
| 已出席活動 | 已出席一個活動 | 活動 | 20 | 60 |
| 與對話方塊中的代理程式互動 | 在Dynamic Chat對話方塊中與代理程式互動 | 聊天 | 20 | 90 |
| 對話方塊中聊天中的點按連結 | 在Dynamic Chat對話方塊中按一下連結 | 聊天 | 20 | 90 |
| 參與對話流程 | 使用Dynamic Chat對話流程 | 聊天 | 20 | 90 |
| 已排程的會議對話流程 | 在Dynamic Chat對話流程中排程約會 | 聊天 | 20 | 90 |
| 已達到對話流量目標 | 在Dynamic Chat對話流程中達到目標 | 聊天 | 20 | 90 |
| 在交談流程中與檔案互動 | 在Dynamic Chat對話流程中與檔案互動 | 聊天 | 20 | 90 |
| 在交談流程中與代理程式互動 | 在Dynamic Chat對話流程中與代理程式互動 | 聊天 | 20 | 90 |
| 交談流程中的交談點按連結 | 按一下Dynamic Chat對話流程中的連結 | 聊天 | 20 | 90 |
| 按一下SMS V2中的連結 | 按一下SMS訊息中的連結 | 簡訊 | 20 | 90 |

>[!NOTE]
>
>參與分數活動會記錄在人員](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-lists-and-static-lists/managing-people-in-smart-lists/locate-the-activity-log-for-a-person){target="_blank"}的Marketo Engage [活動記錄中。

+++

#### 加權

使用者可以指派&#x200B;_加權_&#x200B;給角色範本中的每個角色，為角色配置不同的權重，以計算參與分數。

![設定角色範本中每個角色的權重](./assets/roles-templates-weighting.png){width="700" zoomable="yes"}

每個加權層級都會轉換為值，用於計算參與分數：

* [!UICONTROL 一般] = 20
* [!UICONTROL 次要] = 40
* [!UICONTROL 一般] = 60
* [!UICONTROL 重要] = 80
* [!UICONTROL 重要] = 100

具有三個加權為&#x200B;_[!UICONTROL Vital]_、_[!UICONTROL Important]_&#x200B;和&#x200B;_[!UICONTROL Normal]_&#x200B;之角色的角色範本轉換為下列加權百分比：

| 角色 | 加權 | 系統值 | 值計算 | 百分比 |
|-------------- |--------- |------------- |------------------ |---------- |
|               |          |              |                   |           |
| 決策者 | 重要 | 100 | 100/240 | 41.67% |
| 影響者 | 重要 | 80 | 80/240 | 33.33% |
| 從業人員 | 正常 | 60 | 60/240 | 25% |
|               | 總計 | 240 |                   |           |

#### 計算範例

下列範例說明使用概述的職責權重百分比、採購群組各成員之入埠活動計數，以及每個事件（若已發生多次）的每日上限20計數的參與分數計算。

| 角色 | 會員 | 活動型別 | 昨天的計數 | 今天的計數 | 計算 | 總分 |
|-------------- |--------- |-------------|-----------------|-------------|------|-----------|
|               |          |             |                 |             |      |           |
| 決策者 | Adam | 造訪的網站 | 37 | 15 | 20 + 15 | 35 |
|               |          | 已點按的電子郵件 | 1 | 1 | 1 + 1 | 2 |
|               |          |             |                 |             |      |           |
|               | 標籤 | 造訪的網站 | 5 | 3 | 5 + 3 | 8 |
|               |          | 已點按的電子郵件 | 1 | 1 | 1 + 1 | 2 |
|               |          | 下載的公共 | 3 | 2 | 3 + 2 | 5 |
| **決策者總分** |         |             |                 |             |      | **52** |
|               |          |             |                 |             |      |           |
| 影響者 | John | 造訪的網站 | 19 | 9 | 19 + 9 | 28 |
| **影響者總分** |         |             |                 |             |      | **28** |
|               |          |             |                 |             |      |           |
| 從業人員 | 鮑伯 | 已點按的電子郵件 | 1 | 1 | 1 + 1 | 2 |
|               |          |             |                 |             |      |           |
|               | 保羅 | 已點按的電子郵件 | 1 | 1 | 1 + 1 | 2 |
|               |          |             |                 |             |      |           |
|               | Calvin | 已點按的電子郵件 | 1 | 1 | 1 + 1 | 2 |
|               |          | 造訪的網站 | 1 | 7 | 1 + 7 | 8 |
|               |          | 下載的公共 | 1 | 2 | 1 + 2 | 3 |
| **從業人員總分** |         |             |                 |             |      | **17** |

最終參與分數是透過套用每個角色分數的加權來計算：

| 角色 | 角色總分 | 角色權重% | 分數X權重% |
|-------------- |---------------- |------------- |---------------- |
| 決策者 | 52 | 41.67% | 21.67 |
| 影響者 | 28 | 33.33% | 9.33 |
| 從業者 | 17 | 25% | 4.25 |
| **最終參與分數** |                |             | **35.25** |

## 概述影片

>[!VIDEO](https://video.tv.adobe.com/v/3433078/?learn=on)

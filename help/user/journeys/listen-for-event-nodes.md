---
title: 接聽事件
description: 瞭解在Journey Optimizer B2B edition中可用於協調帳戶歷程的事件節點型別。
feature: Account Journeys
source-git-commit: a1247b0cdab586f2bca1c0e495d5db2069d2645b
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 3%

---

# 接聽事件

新增&#x200B;_接聽事件_&#x200B;節點，在事件發生時，將您的對象移至帳戶歷程中的下一個步驟。

>[!NOTE]
>
>您無法依人員於分割路徑上新增此節點型別。

## 帳戶事件

當您想要根據帳戶活動所觸發的事件，在歷程中向前移動帳戶時，根據帳戶監聽事件。

### 事件和限制

| 活動 | 限制 |
| ----- | ----------- |
| 帳戶有一個有趣的時刻 | 型別（電子郵件、里程碑或Web）<br/>其他限制（選擇性）： <li>說明</li><li>來源</li><li>活動日期</li> <br/>逾時（選擇性） |
| 帳戶資料值的變更 | 屬性<br/>其他限制（選擇性）： <li>新值</li><li>上一個值</li><li>活動日期</li> <br/>逾時（選擇性） |
| 購買群組階段的變更 | 方案興趣<br/>其他限制（選擇性）： <li>新階段</li><li>上一個階段</li><li>活動日期</li><br/>逾時（選擇性） |
| 購買群組狀態的變更 | 方案興趣<br/>其他限制（選擇性）： <li>新狀態</li><li>先前的狀態</li><li>活動日期</li><br/>逾時（選擇性） |
| 完整度分數的變更 | 方案興趣<br/>其他限制（選擇性）： <li>新分數</li><li>前一個分數</li><li>活動日期</li><br/>逾時（選擇性） |
| 參與分數的變更 | 方案興趣<br/>其他限制（選擇性）： <li>新分數</li><li>前一個分數</li><li>活動日期</li><br/>逾時（選擇性） |

### 新增帳戶事件

1. 導覽至歷程編輯器。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 接聽事件]**。

1. 在右側的節點屬性中，為事件型別選擇&#x200B;**[!UICONTROL 帳戶]**。

   ![歷程節點 — 接聽帳戶](./assets/node-listen-events-account.png){width="700" zoomable="yes"}上的事件

1. 從清單中選取事件。

1. 按一下&#x200B;**[!UICONTROL 編輯事件]**&#x200B;並定義事件的詳細資料。

## 人物活動

根據您想要在歷程中根據人員活動所觸發的事件向前移動帳戶的人來監聽事件。

### 事件和限制

| 輸入型別 | 活動 | 限制 |
| ---------- | ----- | ----------- |
| Journey Optimizer B2B | 已指派給購買群組 | 方案興趣<br/><br/>其他限制（選擇性）： <li>角色</li><li>活動日期</li><br/>逾時（選擇性） |
| | 電子郵件中的點按連結 | 電子郵件<br/><br/>其他限制（選擇性）： <li>連結</li><li>連結識別碼</li><li>是行動裝置</li><li>裝置</li><li>平台</li><li>瀏覽器</li><li>為預測性內容</li><li>是機器人活動</li><li>機器人活動模式</li><li>瀏覽器</li><li>活動日期</li><li>最低 次數</li><br/>逾時（選擇性） |
| | 簡訊中的點按連結 | 電子郵件<br/><br/>其他限制（選擇性）： <li>連結</li><li>裝置</li><li>平台</li><li>活動日期</li><li>最低 次數</li><br/>逾時（選擇性） |
| | 資料值變更 | 個人屬性<br/><br/>其他限制（選擇性）： <li>新值</li><li>上一個值</li><li>原因</li><li>來源</li><li>活動日期</li><li>最低 次數</li><br/>逾時（選擇性） |
| | 開啟電子郵件 | 電子郵件<br/><br/>其他限制（選擇性）： <li>連結</li><li>連結識別碼</li><li>是行動裝置</li><li>裝置</li><li>平台</li><li>瀏覽器</li><li>為預測性內容</li><li>是機器人活動</li><li>機器人活動模式</li><li>瀏覽器</li><li>活動日期</li><li>最低 次數</li><br/>逾時（選擇性） |
| | 已從購買群組移除 | 方案興趣<br/>活動日期（選擇性）<br/>逾時（選擇性） |
| | 分數已變更 | 分數名稱<br/><br/>其他限制（選擇性）：<li>變更</li><li>新分數</li><li>急迫性</li><li>優先順序</li><li>相對分數</li><li>相對急迫性</li><li>活動日期</li><li>最低 次數</li><br/>逾時（選擇性） |
| | 簡訊退信 | SMS訊息<br/><br/>其他限制（選擇性）： <li>活動日期</li><li>最小次數</li><br/>逾時（選擇性） |
| Marketo Engage | 造訪網頁 | 網頁<br/>選取一或多個相符的Marketo Engage頁面。 <br/><br/>其他限制（選擇性）： <li>Querystring</li><li>使用者端IP位址</li><li>反向連結</li><li>使用者代理</li><li>搜尋引擎</li><li>搜尋查詢</li><li>Token</li><li>瀏覽器</li><li>平台</li><li>裝置</li><li>活動日期</li> |
| | 填寫表單 | 表單<br/>選取一或多個相符的Marketo Engage表單。  <br/><br/>其他限制（選擇性）： <li>活動日期</li><li>Querystring</li><li>使用者端IP位址</li><li>反向連結</li><li>使用者代理</li><li>平台</li><li>裝置</li><br/>逾時（選擇性） |
| Adobe Experience Platform | 事件定義 | 事件型別<br/><br/>其他限制（選擇性）： <li>欄位</li> <br/>其他限制（不支援）： <li>活動日期</li><li>最低 次數</li><br/>逾時（選擇性） |

### 新增人員事件

1. 導覽至歷程編輯器。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 接聽事件]**。

1. 在右側的節點屬性中，選擇事件型別的&#x200B;**[!UICONTROL 人員]**。

   ![歷程節點 — 接聽人員上的事件](./assets/node-listen-events-people.png){width="700" zoomable="yes"}

1. 從清單中選取事件。

1. 按一下&#x200B;**[!UICONTROL 編輯事件]**&#x200B;並定義事件的詳細資料。

### 接聽Marketo Engage事件

如果您在連線的Marketo Engage執行個體中建立了網頁，則可以根據造訪/未造訪Marketo Engage網頁以及未填入Marketo Engage表單來觸發事件。

1. 在歷程編輯器中選取&#x200B;**[!UICONTROL 接聽事件]**&#x200B;節點。

1. 在右側的節點屬性中，選擇事件型別的&#x200B;**[!UICONTROL 人員]**。

1. 按一下&#x200B;**[!UICONTROL 選取人員事件]**&#x200B;選擇器的箭頭，然後捲動功能表至&#x200B;**[!UICONTROL Marketo Engage]**&#x200B;區段。

1. 選取Market Engage活動型別：

   * **[!UICONTROL 瀏覽網頁]**。
   * **[!UICONTROL 填寫表單]**

   ![聆聽體驗活動](./assets/node-listen-events-people-me-event.png){width="700" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 編輯事件]**&#x200B;並定義一個或多個要比對的網頁，以及事件的任何其他限制。

   * （必要）在&#x200B;_[!UICONTROL 編輯事件]_&#x200B;對話方塊中，定義&#x200B;**[!UICONTROL 網頁]**&#x200B;或填寫表單條件約束。 使用&#x200B;**[!UICONTROL 是]** （預設）在一或多個選取的頁面或表單上比對。 使用&#x200B;**[!UICONTROL 不是]**&#x200B;在所有頁面瀏覽/表單上相符，並排除一或多個選取的頁面/表單。 或者，使用&#x200B;**[!UICONTROL 為任何]**&#x200B;以符合任何Marketo Engage網頁造訪或填寫的表單。

   * （選擇性）按一下&#x200B;**[!UICONTROL 新增限制]**，然後選擇您要用於限制的欄位。 設定欄位的運運算元和值。

     ![聆聽體驗活動](./assets/node-listen-events-people-me-event-edit-dialog.png){width="700" zoomable="yes"}

     您可以視需要重複此動作以包含其他欄位限制。

   * 定義限制時，按一下&#x200B;**[!UICONTROL 完成]**。

1. 如有需要，請設定&#x200B;**[!UICONTROL 逾時]**&#x200B;選項，以限制接聽事件的時段（請參閱[將逾時新增至事件節點](#add-a-timeout-to-an-event-node)）。

1. 在歷程編輯器中，新增下一個節點，以在事件發生時執行。

### 聆聽體驗事件

管理員可以設定Adobe Experience Platform (AEP)型事件定義，讓行銷人員建立會對[AEP體驗事件](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent)做出反應的帳戶歷程。 在帳戶歷程中使用AEP體驗事件有兩個步驟：

1. [建立並發佈AEP事件定義](../admin/configure-aep-events.md)。

2. 在帳戶歷程中，新增&#x200B;_接聽事件_&#x200B;節點，並為以人物為基礎的事件選取Experience Platform事件定義。

_若要在歷程中加入體驗事件：_

1. 在歷程編輯器中選取&#x200B;**[!UICONTROL 接聽事件]**&#x200B;節點。

1. 在右側的節點屬性中，選擇事件型別的&#x200B;**[!UICONTROL 人員]**。

1. 按一下&#x200B;**[!UICONTROL 選取人員事件]**&#x200B;選取器的箭頭，然後捲動功能表至&#x200B;**[!UICONTROL Adobe Experience Platform]**&#x200B;區段。

   ![聆聽體驗活動](./assets/node-listen-events-people-aep-events.png){width="700" zoomable="yes"}

1. 選取事件。

   事件型別在節點詳細資料中顯示為空白。

   ![編輯事件](./assets/node-listen-events-people-aep-events-edit.png){width="400" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 編輯事件]**&#x200B;並定義事件的事件型別和任何其他限制。

   * （必要）在&#x200B;_[!UICONTROL 編輯事件]_&#x200B;對話方塊中，定義事件型別。 您可以使用預設的&#x200B;**[!UICONTROL 是]**&#x200B;運運算元，在一或多個選取的事件型別上比對。 或者，您可以使用&#x200B;**[!UICONTROL is not]**&#x200B;運運算元來比對所有事件型別，並排除一或多個選取的事件型別。

   * （選擇性）按一下&#x200B;**[!UICONTROL 新增限制]**，然後選擇您要用於限制的欄位。 設定欄位的運運算元和值。

     ![聆聽體驗活動](./assets/node-listen-events-people-aep-events-edit-dialog.png){width="700" zoomable="yes"}

     >[!NOTE]
     >
     >不支援&#x200B;_活動日期_&#x200B;和&#x200B;_最小次數_&#x200B;的限制。

     您可以視需要重複此動作以包含其他欄位限制。

   * 定義限制時，按一下&#x200B;**[!UICONTROL 完成]**。

1. 如有需要，請設定&#x200B;**[!UICONTROL 逾時]**&#x200B;選項，以限制接聽事件的時段（請參閱[將逾時新增至事件節點](#add-a-timeout-to-an-event-node)）。

1. 在歷程編輯器中，新增下一個節點，以在事件發生時執行。

1. 完成您歷程的其餘節點，並[發佈它](./journey-overview.md)。

   當歷程為即時（已發佈）並到達&#x200B;_接聽事件_&#x200B;節點時，它會開始接聽AEP體驗事件。

## 將逾時新增至事件節點

如有需要，請定義歷程等待事件的時間長度。 歷程會在逾時後結束，除非您定義逾時路徑，在其中新增其他節點。

1. 啟用&#x200B;**[!UICONTROL 逾時]**&#x200B;選項。

1. 選取歷程在逾時前等待事件發生的持續時間。

   您可以選擇在此結束路徑，或透過設定其他路徑採取不同的動作。

1. 若要在歷程中建立新路徑，以便在事件未發生時新增適用於帳戶的動作和事件，請選取&#x200B;**[!UICONTROL 設定逾時路徑]**&#x200B;核取方塊。

   ![歷程事件節點 — 設定逾時路徑](./assets/node-event-timeout-set-path.png){width="700" zoomable="yes"}




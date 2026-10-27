---
title: B2B帳戶和人員的對象技能
description: 瞭解B2B帳戶和人員的對象技能。 探索產品意圖、識別角色、評估角色涵蓋範圍，並建立購買群組範本。
feature: Agentic AI, Audiences
role: User
exl-id: c1210912-66ba-4b5f-8f3b-96eb6280c926
autotag-review: '2026-06-05T16:43:42.459Z'
TQID: 'https://experienceleague.adobe.com/d7KMYbH0NpoYGnBdTCmCpzLgpGIYfNP-YIFCQUjZpIg'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: afadf741-c5fe-42cd-8013-23bb6ff2d1bc
    internal-label: Buying Groups
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
subfeature_v2:
  - id: ff10f619-348f-47e3-99bf-3ce4c817cf2c
    internal-label: Agentic AI
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
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
source-git-commit: ce5504e7a539c38b489fddc103358029edf1cfba
workflow-type: tm+mt
source-wordcount: '1692'
ht-degree: 1%
---
# B2B帳戶和人員的對象技能

在[!DNL CX Coworker]介面中使用B2B的對象技能。 探索跨帳戶和人員的產品意圖。 識別相關角色、評估購買群組涵蓋範圍，並建立購買群組角色範本。

* 評估帳戶對特定產品的興趣，並比較意圖趨勢。
* 識別與產品興趣相關的人員和角色。
* 檢閱購買群組角色並找出涵蓋範圍差距。
* 產生並調整購買群組角色範本。

>[!PREREQUISITES]
>
>對B2B帳戶和人員使用對象技能之前，請設定以下資料定義和對應：
>
>* [意圖資料分類和對應](../admin/intent-data.md)
>* [XDM欄位對應](#xdm-data-prerequisites)

按一下應用程式頂端的&#x200B;_詢問[!DNL Coworker]_ （ ![詢問[!DNL Coworker]](../assets/do-not-localize/icon-ask-coworker.svg) ）圖示以開啟[!DNL Coworker]應用程式。 在聊天介面中輸入您的自然語言提示。

[!DNL CX Coworker]](./assets/audience-skills-prompt.png){width="800" zoomable="yes"}中的![對象提示

## 對象技能焦點領域

使用對象技能焦點區域來探索帳戶意圖、瞭解人員和角色，以及準備購買群組範本。

| 聚焦 | 工作 |
| ----- | ----- |
| 帳戶目的 | 使用低、中、高意圖層級評估特定產品的帳戶意圖。 比較一段時間內產品的興趣趨勢，並識別對特定產品感興趣的帳戶。 連同角色涵蓋範圍一起檢閱參與模式。 |
| 人員與角色 | 依產品意向識別一或多個產品中的角色並排名。 檢閱機會量度，包括獲勝率、會籍率和計數。 將角色對應至&#x200B;_Champion_、_決策者_&#x200B;和&#x200B;_影響者_&#x200B;等角色，並檢閱角色指派的說明。 |
| 購買群組涵蓋範圍 | 評估跨帳戶的購買群組大小和角色涵蓋範圍。 檢閱角色分配並識別缺少的角色。 尋找在最近交易中擁有冠軍的客戶。 |
| 購買群組範本 | 產生特定產品的購買群組角色範本，並檢閱建議的角色對應。 包含或排除角色和角色以縮小範本範圍。 在建立購買群組之前驗證所需的角色。 |

## 限制

對象深入分析取決於設定的意圖分類法、XDM欄位對應和體驗事件資料。 商機資料不完整、遺失或過時的分類法，或遺失設定檔和帳戶識別碼，可能會降低insight的可靠性。

意圖計算僅使用下列體驗事件： `directMarketing.emailClicked`、`directMarketing.emailOpened`、`directMarketing.emailUnsubscribed`和`web.webpagedetails.pageViews`。

## 提示範例

在[!DNL CX Coworker]介面中輸入以下提示，以探索帳戶意圖、瞭解人員和角色，以及準備購買群組範本。

### 帳戶目的

探索帳戶對產品的興趣，並檢閱意圖中的變更。

* 顯示趨勢視窗：每個產品帳戶產品意向的最早和最新更新。
* 哪些客戶對任何產品的意圖較低，但仍擁有開放機會（值得培育）？
* 本週已針對`<account_name>`錄製哪些新的意圖訊號？

### 人員與角色

識別與產品興趣相關的角色，並檢閱建議的購買群組角色。

* 顯示與`<product>`關聯的角色。
* 為我顯示`<product>`的角色與角色對應建議。
* 針對`<product>`，列出角色及其機會量度（獲勝率、會籍率、計數）。

### 購買群組和範本

檢閱購買群組意圖和涵蓋範圍，然後產生或調整範本。

* 針對`<product>`，列出具有產品意向和評分的購買群組。
* 對於`<industry>`中的帳戶，`<product>`的平均帳戶角色涵蓋範圍是多少？
* 建立`<product>`的購買群組範本。
* 為不含`<persona>`角色的`<product>`建立購買群組範本，並移除`<role>`角色。

## 概念

使用這些概念來解讀帳戶意圖、角色排名和購買群組推薦。

| 概念 | 說明 |
| ------- | ----------- |
| 對象偵測 | 分析帳戶中各個人員的第一方參與訊號，以識別產品興趣和相關角色。 分析會考量之前18個月的活動，包括商機結束前的活動。 參與模式可以在機會資料不完整時指出產品意圖，但缺少資料可能會降低insight的可靠性。 |
| 人物誌 | 人物會依正規化的職稱、職能和資歷將人員分組。 使用角色來瞭解客戶中的參與者，包括決策者、影響者和支援角色。 |
| 對應購買群組角色 | 根據職稱、職能、資歷和設定的屬性，將角色對應到產品特定的購買群組角色。 這些角色代表帳戶中影響或決定購買的人員。 檢閱涵蓋範圍以識別缺少的角色。 |
| 角色排名的機會資料 | 機會階段、結束日期及機會對產品的對應支援每個產品的角色排名。 當商機資料不完整時，排名會使用活動數量和時間衰減，為最近的活動提供更大的權重。<br/><br/>產品連結使用已提供或產生的機會與產品對應表（如果可用）。 否則，模糊比對會將機會連結至產品。 如果沒有可用的連結，則會從商機關閉日期之前的最近活動推斷產品意圖。 這些遞補方法無法消除不完整資料的可靠性限制。 |
| 機會分析 | 歷史機會分析使用三個維度來識別與購買結果相關的角色模式：<ul><li>成功率：測量當特定角色參與時，成功獲利的頻率。 與較高獲勝率相關聯的角色模式會獲得較重的權重。</li><li>會籍率：測量角色出現在特定產品機會中的頻率。</li><li>角色影響：衡量角色參與度或活動與贏取的相關性，除了角色是否存在。</li></ul>這些訊號會通知帳戶意圖、角色對應和購買群組推薦。 |
| 意圖 | 意圖會透過參與表示產品興趣，例如網頁瀏覽或電子郵件連結點選。 產品分類會將參與活動連結到關鍵字、產品和產品類別。 參與深度和頻率會決定每個關鍵字、產品或產品類別的個別意圖分數。<br/><br/>分數表示興趣強度：低意圖： `<=0.2`，Medium意圖： `0.2 < score <= 0.6`，高意圖： `0.6 < score <= 1`。<br/><br/>會彙總相同帳戶中不同人員的個人意圖分數，以判斷帳戶意圖。 |
| 影響購買群組的角色 | 購買群組角色代表對購買決策的不同貢獻。 _決策者_&#x200B;通常會控制預算核准。 _影響者_&#x200B;圖形評估與建議。 _Champions_&#x200B;建立內部共識。 _一般使用者_&#x200B;驗證產品適合度。<br/><br/>檢閱角色指派和涵蓋範圍，以瞭解影響決定的人員以及參與差距持續存在的位置。 |
| 角色或角色涵蓋範圍 | 涵蓋範圍會衡量一個帳戶中多少預期角色至少有一名代表。 對於具有&#x200B;_N_&#x200B;個預期角色或角色的產品，完整涵蓋範圍表示所有&#x200B;_N_&#x200B;都會呈現。 部分涵蓋範圍表示遺漏部分內容。 使用涵蓋範圍來評估購買群組的完整度並找出差距。 |

## XDM資料必要條件

設定下列XDM欄位對應以支援帳戶意圖分析、角色識別及購買群組角色對應。

### xdm欄位對應

<table>
  <tbody>
    <tr>
      <th>XDM欄位</th>
      <th>實體</th>
      <th>業務定義</th>
      <th>其他詳細資料</th>
    </tr>
    <tr>
      <td>
        <p>
          <span>b2b.accountKey.sourceKey</span>
        </p>
      </td>
      <td>
        <p>
          <span>輪廓</span>
        </p>
      </td>
      <td>帳戶識別碼，用於加入商機、事件和意圖資料</td>
      <td rowspan="2">機會分析<br/>帳戶探索<br/>
        <br/>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>b2b.personKey.sourceKey</span>
        </p>
      </td>
      <td>
        <p>
          <span>輪廓</span>
        </p>
      </td>
      <td>個人識別碼，用於涉及事件資料至設定檔資料的加入</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>extendedWorkDetails.departments</span>
        </p>
      </td>
      <td>
        <p>
          <span>個設定檔</span>
        </p>
      </td>
      <td>設定檔/個人的工作部門</td>
      <td rowspan="5">
        <p>
          <br/>
        </p>
        <p>角色對應</p>
      </td>
    </tr>
    <tr class="">
      <td>
        <p>
          <span>extendedWorkDetails.jobTitle</span>
        </p>
      </td>
      <td>
        <p>
          <span>個設定檔</span>
        </p>
      </td>
      <td>用於角色計算的設定檔/人員職稱</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>person.name.firstName</span>
        </p>
      </td>
      <td>
        <p>
          <span >輪廓</span>
        </p>
      </td>
      <td>在符合您查詢的結果中顯示人員的名字。</td>
    </tr>
    <tr class="">
      <td>
        <p>
          <span>person.name.fullName</span>
        </p>
      </td>
      <td>
        <p>
          <span>個設定檔</span>
        </p>
      </td>
      <td>在符合您查詢的結果中顯示個人的全名。</td>
    </tr>
    <tr class="">
      <td>
        <p>
          <span>person.name.lastName</span>
        </p>
      </td>
      <td>
        <p>
          <span>個設定檔</span>
        </p>
      </td>
      <td>在符合您查詢的結果中顯示人員的姓氏。</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountKey.sourceKey</span>
        </p>
      </td>
      <td>
        <p>
          <span>帳戶</span>
        </p>
      </td>
      <td>帳戶識別碼，用於加入商機、事件和意圖資料</td>
      <td>機會分析<br/>帳戶探索</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>帳戶名稱</span>
        </p>
      </td>
      <td>
        <p>
          <span>帳戶</span>
        </p>
      </td>
      <td>在符合查詢的結果中顯示帳戶名稱。</td>
      <td rowspan="4">
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>帳戶探索</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountDescription</span>
        </p>
      </td>
      <td>
        <p>
          <span>帳戶</span>
        </p>
      </td>
      <td>支援根據您的查詢依帳戶說明進行帳戶篩選。</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountOrganization.industry</span>
        </p>
      </td>
      <td>
        <p>
          <span>帳戶</span>
        </p>
      </td>
      <td>支援根據您的查詢依產業進行帳戶篩選。</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountBillingAddress.region</span>
        </p>
      </td>
      <td>
        <p>
          <span>帳戶</span>
        </p>
      </td>
      <td>根據您的查詢，支援依帳單地址區域進行帳戶篩選。</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>accountKey.sourceKey</span>
        </p>
      </td>
      <td>
        <p>
          <span>商機</span>
        </p>
      </td>
      <td>帳戶識別碼，用於加入商機、事件和意圖資料</td>
      <td rowspan="2">
        <p>機會分析<br/>帳戶探索</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>opportunityKey.sourceKey</span>
        </p>
      </td>
      <td>
        <p>
          <span>商機</span>
        </p>
      </td>
      <td>機會識別碼，用於加入帳戶資料</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>opportunityName</span>
        </p>
      </td>
      <td>
        <p>
          <span>個機會</span>
        </p>
      </td>
      <td>機會分析中使用的機會名稱。</td>
      <td rowspan="5">
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>機會分析</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>isWon</span>
        </p>
      </td>
      <td>
        <p>
          <span>商機</span>
        </p>
      </td>
      <td>是否贏得機會（二進位）</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>opportunityDescription</span>
        </p>
      </td>
      <td>
        <p>
          <span>商機</span>
        </p>
      </td>
      <td>機會分析中使用的機會說明。</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>opportunityAmount</span>
        </p>
      </td>
      <td>
        <p>
          <span>商機</span>
        </p>
      </td>
      <td>機會中涉及的金額$</td>
    </tr>
    <tr class="">
      <td>
        <p>
          <span>opportunityType</span>
        </p>
      </td>
      <td>
        <p>
          <span>商機</span>
        </p>
      </td>
      <td>機會型別</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>商機階段</span>
        </p>
      </td>
      <td>
        <p>
          <span>個機會</span>
        </p>
      </td>
      <td>機會階段（已結束的贏家或已結束的輸家，或任何中間階段） </td>
      <td rowspan="4">
        <p>機會分析<br/>帳戶探索</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>actualCloseDate</span>
        </p>
      </td>
      <td>
        <p>
          <span>商機</span>
        </p>
      </td>
      <td>機會的實際結束日期</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>expectedCloseDate</span>
        </p>
      </td>
      <td>
        <p>
          <span>個機會</span>
        </p>
      </td>
      <td>商機的預期結束日期</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>extSourceSystemAudit.createdDate</span>
        </p>
      </td>
      <td>
        <p>
          <span>商機</span>
        </p>
      </td>
      <td>建立此機會的日期</td>
    </tr>
  </tbody>
</table>

### 分類資料

對象技能使用來自[!DNL Adobe Journey Optimizer B2B Edition]的第一方意圖資料。 意圖計算將產品分類與參與活動連線起來，並彙總帳戶層級的個別分數。

1. 意圖計算需要來自客戶>分類的分類資料（客戶產品和對應的關鍵字）
1. 分類資料用於標示事件資料（資產標籤）。 此資料會根據訪客的事件資料>資產標籤，提供訪客感興趣的關鍵字和產品深入分析 
1. 標籤資產（事件資料）會與訪客行為（造訪的頁面數）結合，以在意向計算中判斷關鍵字、產品和產品類別層級的訪客意→
1. 訪客設定檔層級的意圖分數會在帳戶層級彙總，以判斷指定關鍵字、產品和產品類別>意圖帳戶彙總中的帳戶意圖

除了[設定意圖分類](../admin/intent-data.md)外，還需要下列欄位：

<table>
  <tbody>
    <tr>
      <th>XDM欄位</th>
      <th>實體</th>
      <th>業務定義</th>
    </tr>
    <tr>
      <th>
        <br/>
      </th>
      <th>
        <br/>
      </th>
      <td>個人設定檔</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>_acp_system_metadata.primaryIdentity.namespace.code<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>輪廓</span>
        </p>
      </td>
      <td>協助識別人員（電子郵件或b2b_person）識別碼</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>_acp_system_metadata.primaryIdentity.id
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>輪廓</span>
        </p>
      </td>
      <td>namespace_id</td>
    </tr>
    <tr>
      <td>
        <ul>
          <li>keyword_id</li>
          <li>keyword_name</li>
          <li>product_id</li>
          <li>product_name</li>
          <li>product_category_id</li>
          <li>product_category_name</li>
        </ul>
      </td>
      <td>
        <p>
          <br/>
        </p>
      </td>
      <td>做為標籤資產（體驗事件，例如點選的電子郵件、造訪的網頁）的分類法</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>時間戳記</span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>用於取得回填和增量執行的時間</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>eventType</span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>識別事件型別。 意圖計算僅使用<code>directMarketing.emailClicked</code>、<code>directMarketing.emailOpened</code>、<code>directMarketing.emailUnsubscribed</code>和<code>web.webpagedetails.pageViews</code>。
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>directMarketing.mailingName</span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>僅供參考/簿記；關於行銷活動名稱的資訊</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>directMarketing.mailingKey.sourceID</span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>僅供參考/簿記；電子郵件目標來源ID的相關資訊</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>directMarketing.mailingKey.sourceInstanceID<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>僅供參考/簿記；電子郵件目標來源執行個體的資訊</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>directMarketing.mailingKey.sourceKey<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>用於從[!DNL Adobe Marketo Engage]資料中心擷取電子郵件內容。 它包含(SourceID@SourceInstanceID.SourceType)。</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>directMarketing.mailingKey.sourceType<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>僅供參考/記帳；來源型別或來源來源來源來源來源位置的資訊 </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>有關網頁造訪來源來源的資訊</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.name<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>用來取得內容的實際URL</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.queryParameters</span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>用於擷取目標內容的URL的其他查詢引數 </td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.isPersonalizedURL</span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>僅供參考/簿記</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.webPageKey.sourceID<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>僅供參考/簿記；電子郵件目標來源ID的相關資訊</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.webPageKey.sourceInstanceID<br/>
          </span>
        </p>
      </td>
      <td>
        <p>
          <span>體驗活動</span>
        </p>
      </td>
      <td>僅供參考/簿記；電子郵件目標來源執行個體的相關資訊</td>
    </tr>
    <tr class="">
      <td>
        <p>
          <span>web.webPageDetails.webPageKey.sourceKey<br/>
          </span>
        </p>
      </td>
      <td>
        <span>體驗活動</span>
      </td>
      <td>僅供參考/記帳；由(SourceID@SourceInstanceID.SourceType)組成</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.webPageKey.sourceType</span>
        </p>
      </td>
      <td>
        <span>體驗活動</span>
      </td>
      <td>僅供參考/記帳；來源型別或來源來源來源的資訊</td>
    </tr>
    <tr>
      <td>
        <p>
          <span>web.webPageDetails.webPageKey.URL</span>
        </p>
      </td>
      <td>
        <span>體驗活動</span>
      </td>
      <td>用於擷取web.webPageDetails.name沒有的實際url。</td>
    </tr>
  </tbody>
</table>

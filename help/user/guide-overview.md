---
title: Adobe Journey Optimizer B2B Edition 文件
description: Journey Optimizer B2B Edition 的完整文件：探索用於上線、建立購買群組、建置帳戶歷程，以及管理內容的可用資源。
exl-id: 3d7b6c82-95c3-4d89-b3dc-7fd5b0aef615
autotag-review: 2026-03-27T22:18:45.397Z
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: f467931a-9b22-4ca8-869f-adfbd64061ce
    internal-label: Onboarding
TQID: https://experienceleague.adobe.com/BK-uFYGIZyqRNy4Gx-vJB-oy3q8zpjERIoJwBvgofUY
source-git-commit: ce5504e7a539c38b489fddc103358029edf1cfba
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 26%
---
# Adobe Journey Optimizer B2B Edition 文件

[!DNL Adobe Journey Optimizer B2B Edition]是首創的應用程式，可讓行銷和銷售團隊在整個客戶生命週期中協調以帳戶為基礎的體驗，並讓購買群組符合特定產品的資格。 它使用AI來與目標帳戶中的購買群組互動並取得資格，協助您的團隊產生更高品質的管道，並設計更好的贏取、擴充和保留策略。 它也會啟用銷售和行銷團隊之間的共用深入分析。

本檔案提供熟悉應用程式的資訊。 它是專為行銷人員、業務開發代表、資料分析師和營運管理員所設計。

## 新增功能

檢閱[!DNL Journey Optimizer B2B Edition]應用程式和檔案的最新新增和增強功能抽樣。

>[!BEGINTABS]

>[!TAB 個人歷程]

透過個人歷程協調銷售機會型行銷，使用[!DNL Adobe Experience Platform]對象和資料與個人互動。 個人歷程現在支援&#x200B;_接聽事件_、外部動作和外部分割路徑節點，以及歷程重新進入。 將它們與帳戶歷程和購買群組搭配使用，以協調完整的購買歷程。

[!BADGE 了解更多]{type=Informative url="/help/user/journeys/journeys-overview.md" tooltip="瞭解個人歷程"}

>[!TAB 變體分割路徑]

根據您定義的百分比，將帳戶或人員指派至不同歷程路徑，以測試帳戶或人員歷程中的變數。 在個人歷程中，指派是決定性的，因此每個人都永遠遵循相同的路徑，這支援受控實驗。

[!BADGE 了解更多]{type=Informative url="/help/user/journeys/variant-split-paths-nodes.md" tooltip="瞭解變體分割路徑"}

>[!TAB WhatsApp頻道]

當開發人員和產品管理員設定與Meta Business Manager帳戶的整合時，行銷人員可以使用Meta Cloud API在帳戶歷程中將WhatsApp訊息作為內容管道納入。 WhatsApp加入電子郵件和簡訊，作為直接傳送歷程內容給帳戶成員的可用管道。

[!BADGE 了解更多]{type=Informative url="/help/user/admin/configure-channels-whatsapp.md" tooltip="瞭解WhatsApp頻道"}

>[!TAB 產生AI模型]

為電子郵件內容產生影像時，電子郵件設計人員現在可以從標準[!DNL Firefly]模型、根據品牌特定資產訓練的自訂[!DNL Firefly]模型和核准的第三方影像模型中選擇。 從一般內容需求到品牌或專業化的使用案例，此選擇可讓團隊控制哪些型號適合其特定設計案例。

[!BADGE 了解更多]{type=Informative url="/help/user/content/generative-ai-models.md" tooltip="瞭解產生AI模型選擇"}

>[!TAB 傳送時間最佳化]

針對個人歷程中的&#x200B;_傳送電子郵件_&#x200B;動作節點，您現在可以使用傳送時間最佳化來個人化電子郵件傳送時間。 此系統會預測每個人最有可能參與的時間並據此排程傳送，而非同時傳送給所有收件者。

[!BADGE 了解更多]{type=Informative url="/help/user/content/email-send-time-optimization.md" tooltip="瞭解傳送時間最佳化"}

>[!TAB 歷程重新進入]

您現在可以透過帳戶或個人歷程多次傳送帳戶或人員。 重新進入可處理多種情境，例如重新評估資格條件和可重複使用的培養工作流程。 使用重新進入設定來設定條件、限制和等待時間，以便帳戶或人員以可控方式重新符合歷程的資格。

[!BADGE 了解更多]{type=Informative url="/help/user/journeys/journey-re-entry.md" tooltip="瞭解重新進入歷程"}

>[!ENDTABS]

## 開始探索 {#section-explore}

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg)

最新發行說明

透過[!DNL Adobe Journey Optimizer B2B Edition]的最新發行說明、新功能和改進專案隨時掌握最新消息。

[檢視發行說明](./release-notes/release-notes.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

快速入門

檢閱管理員和行銷人員的[!DNL Journey Optimizer B2B Edition]入門指南。

[管理員](./setup-ultimate.md)
[位使用者](./start/get-started.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

管理您的資料

啟用您想要在[!DNL Adobe Journey Optimizer B2B Edition]中使用的XDM結構描述和欄位，並瞭解其資料在[!DNL Adobe Experience Platform]中的運作方式。

[檢視XDM欄位管理](./admin/xdm-field-management.md)
[匯出的資料集](./data/aep-exported-datasets.md)
[資料集查詢](./data/aep-query-examples.md)
[資料可用性與同步時間](./data/data-availability-timing.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

通訊管道

設定並管理電子郵件、簡訊、WhatsApp和其他管道，以進行個人化的客戶互動。

[設定電子郵件頻道](./admin/configure-channels-emails.md)
[設定簡訊頻道](./admin/configure-channels-sms.md)
[設定WhatsApp頻道](./admin/configure-channels-whatsapp.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

建立歷程

設計、協調、管理和最佳化個人化帳戶與個人歷程。

[探索歷程](./journeys/journeys-overview.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/users.svg)

瞭解購買群組

針對有效鎖定目標而建立、管理和最佳化購買群組的詳細指引。

[瞭解購買群組](./buying-groups/buying-groups-overview.md)
:::

::::

<!--
:::
![icon](https://cdn.experienceleague.adobe.com/icons/image.svg)

Design Content

Learn how to author and manage content for personalized customer experiences orchestrated through journeys.

[Explore Content Components](./content/content-components.md)
::: 
-->

## 概觀示範

探索購買群組的元件，以及了解建立帳戶歷程的基礎知識。

>[!VIDEO](https://video.tv.adobe.com/v/3432054?quality=12)

## 探索檔案

<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="../assets/do-not-localize/icon-quick-start.svg" width="35px" alt="開始使用"><br/>
      <strong>開始使用</strong><br/><a href="home-page.md">登入和首頁</a><br/><a href="./start/get-started.md">入門指南</a> <br/><a href="./ai-coworker/ai-overview.md">AI功能</a>
    </td>
    <td>
      <img src="../assets/do-not-localize/icon_audience.svg" width="35px" alt="購買群組"><br/>
      <strong>購買群組</strong><br/><a href="./buying-groups/buying-groups-overview.md">購買群組概觀</a><br/><a href="./buying-groups/buying-groups-role-templates.md">角色範本</a><br/><a href="./buying-groups/solution-interests.md">解決方案興趣</a><br/><a href="./buying-groups/buying-groups-create.md">建立購買群組</a>
    </td>
    <td>
      <img src="../assets/do-not-localize/icon-paths.svg" width="35px" alt="帳戶歷程"><br/>
      <strong>帳戶歷程</strong><br/><a href="./journeys/journeys-overview.md">歷程概觀</a><br/><a href="./journeys/create-publish-journey.md#create-a-journey">建立帳戶歷程</a><br/><a href="./journeys/journey-nodes.md">歷程節點</a>
    </td>
  </tr>
  <tr style="border: 0;">
    <td>
      <img src="../assets/do-not-localize/icon-campaign.svg" width="35px" alt="歷程內容"><br/>
      <strong>歷程內容</strong><br/><a href="./content/add-email.md">電子郵件頻道</a><br/><a href="./content/generate-content-emails.md">產生電子郵件內容</a><br/><a href="./content/genstudio-email-workflow.md">GenStudio電子郵件體驗</a><br/><a href="./content/sms-authoring.md">簡訊頻道</a>
    </td>
        <td>
      <img src="../assets/do-not-localize/icon_assets.svg" width="35px" alt="內容管理"><br/>
      <strong>內容管理</strong><br/><a href="./content/assets-overview.md">Assets概觀</a><br/><a href="./content/email-templates.md">電子郵件範本</a><br/><a href="./content/fragments.md">視覺片段</a><br/><a href="./content/conditional-content.md">條件式內容</a><br/><a href="./content/brand-themes.md">品牌主題</a>
    </td>
    <td>
      <img src="../assets/do-not-localize/icon-offer.svg" width="35px" alt="洞察和儀表板"><br/>
      <strong>分析</strong><br/><a href="./dashboards/intelligent-dashboard.md">智慧型儀表板</a><br/><a href="./dashboards/engagement-dashboard.md">參與儀表板</a><br/><a href="./dashboards/buying-groups-dashboard.md">購買群組儀表板</a><br/><a href="./dashboards/journeys-dashboard.md">歷程儀表板</a><br/><a href="./buying-groups/incrm-insights.md">In-CRM Insights</a>
    </td>

</tr>
</table>

>[!BEGINSHADEBOX]

## [!DNL Marketo Qualifier]

[!DNL Adobe Marketo Qualifier]是AI驅動的應用程式，您可以搭配[!DNL Journey Optimizer B2B Edition]使用。 它會實作帳戶資格技能，並旨在簡化業務開發代表(BDR)的工作流程。 [!DNL Marketo Qualifier]可跨管道自動化潛在客戶資格、外聯和買家參與工作流程。 它減少了手動BDR負載，並加快了企業B2B公司的管道速度。

如需詳細資訊，請參閱[Marketo Qualifier檔案](https://experienceleague.adobe.com/en/docs/marketo-qualifier/using/home){target="_blank"}。

>[!ENDSHADEBOX]

## 其他資源

<table style="table-layout:fixed">
<tr><td><strong>Adobe Journey Optimizer B2B Edition</strong><br/>
<a href="https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer-b2b-learn/tutorials/overview" target="_blank">影片和教學課程</a> - <a href="https://helpx.adobe.com/tw/legal/product-descriptions/adobe-journey-optimizer-b2b.html" target="_blank">產品說明</a> <!-- - <a href="https://www.adobe.com/content/dam/cc/en/security/pdfs/AJO_SecurityOverview.pdf" target="_blank">Security overview (PDF)</a> - <a href="https://developer.adobe.com/journey-optimizer-apis/" target="_blank">APIs reference</a> - <a href="https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html" target="_blank">Journey Optimizer Schema Dictionary</a> -->
</td>
<td><strong>Adobe Experience Platform</strong><br/>
<a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/home" target="_blank">檔案</a> - <a href="https://business.adobe.com/products/experience-platform/documentation-and-developer-resources.html" target="_blank">開發人員資源</a>
</td></tr>
<tr><td><strong>Adobe Real-Time Customer Data Platform</strong><br/>
<a href="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/rtcdp/home" target="_blank">檔案</a> - <a href="https://experienceleague.adobe.com/zh-hant/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/overview" target="_blank">開發人員教學課程</a>
</td><td><strong>Adobe Marketo Engage</strong><br/>
<a href="https://experienceleague.adobe.com/zh-hant/docs/marketo/using/home" target="_blank">使用者檔案</a> - <a href="https://experienceleague.adobe.com/zh-hant/docs/marketo-developer/marketo/home" target="_blank">開發人員檔案</a>
</td>
</tr></table>

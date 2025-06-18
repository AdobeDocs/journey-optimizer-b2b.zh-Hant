---
title: Journey Optimizer B2B Edition 發行說明
description: 了解 Adobe Journey Optimizer B2B Edition 的最新功能和增強功能。
role: User, Admin
exl-id: 7d3f1c26-d8a6-4065-a70f-5b30cb975dc8
source-git-commit: ae2acbde4fbabb5d49a532e8060005acf04f8b26
workflow-type: ht
source-wordcount: '2139'
ht-degree: 100%

---

# Journey Optimizer B2B Edition 發行說明

Adobe Journey Optimizer B2B Edition 持續提供新功能、增強現有功能並修正錯誤。

Journey Optimizer B2B Edition 在 [!DNL Adobe Experience Platform] 以原生方式建置，並繼承其最新的創新功能和改進項目。若要了解更多有關這些變更的資訊，請參閱 [Adobe Experience Platform 發行說明](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/release-notes/latest){target="_blank"}。

請檢視此[產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"}，以了解有關權益、效能護欄及限制的資訊。

## 2025.5 發行說明

**部署日期**：2025 年 6 月 3 日

此版本包括下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 功能 | 與 GenStudio for Performance Marketing 的整合 | (限量開放) 您現在可以將 GenStudio for Performance Marketing 電子郵件體驗與 Journey Optimizer B2B Edition 整合，以提高行銷效率並保持品牌一致性。透過此整合，您就可以將 GenStudio AI 驅動的內容創作與 Journey Optimizer B2B Edition 中的進階協調功能相結合。[了解更多](../content/genstudio-email-workflow.md) |
| 增強功能 | 電子郵件的 Handlebar 語彙基元格式 | 電子郵件內容的個人化語彙基元現在使用了與 Handlebar 指令碼完全相容的更新格式。此格式採用&#x200B;_駝峰式大小寫_&#x200B;或底線，排除了空格。[了解更多](../content/email-authoring.md#content-authoring---personalization) |
| 增強功能 | 清單的顯示總數 | 「_[!UICONTROL 解決方案興趣]_」和「_[!UICONTROL 帳戶歷程]_」清單頁面現在會在搜尋列旁邊顯示總數，讓功能更加完善。 |


## 2025.4 發行說明

**部署日期**：2025 年 4 月 29 日

此版本包括下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 功能 | 帳戶清單 | 現在您可以建立靜態或動態帳戶清單，根據您定義的標準 (例如產業、地點或公司規模) 選定已命名帳戶。<a href="../accounts/account-lists.md">了解更多</a> |
| 功能 | 帳戶清單歷程協調 | 使用歷程動作節點來新增和移除靜態帳戶清單的帳戶。<a href="../accounts/account-lists-journeys.md#take-an-action-node---add-to-account">了解更多</a> |
| 增強功能 | 在 Marketo Engage 中篩選歷程會籍 | 使用 Adobe Journey Optimizer B2B Edition 帳戶清單作為歷程客群，然後使用 Marketo Engage 智慧清單中的「_帳戶清單成員_」篩選器。<a href="../accounts/account-lists-journeys.md#marketo-engage-program---member-of-account-list">了解更多</a> |
| 功能 | 閒置狀態篩選器 | 根據 Marketo Engage 行銷活動和方案 (包括電子郵件閒置狀態、有趣時刻、資料值變更以及造訪過的網頁) 中的閒置狀態來協調歷程。<a href="../journeys/split-merge-paths-nodes.md#activity-filtering">了解更多</a> |
| 增強功能 | 造訪過的網頁篩選器 | 根據所造訪過與 Marketo Engage 行銷活動和方案相關之網頁的活動來協調歷程。<a href="../journeys/split-merge-paths-nodes.md#people-path-conditions">了解更多</a> |
| 增強功能 | 電子郵件清單 | 檢視使用中和草稿狀態的電子郵件全域清單，以便在相關帳戶歷程中搜尋、檢閱與更新這些電子郵件。<a href="../content/emails-list.md">了解更多</a> |

## 2025.3 發行說明

**部署日期**：2025 年 4 月 1 日

此版本包括下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 功能 | 重複帳戶歷程 | 現在可以對帳戶歷程執行重複動作。您可以重複帳戶歷程的詳細資訊，或僅重複流程和路徑架構的基本框架。<a href="../journeys/journey-overview.md#duplicate-journey">了解更多</a> |
| 功能 | 帳戶歷程適用的「我的權杖」 | 現在您可以使用帳戶歷程特定的數值定義一組自訂權杖。這組自訂權杖稱為「_我的權杖_」，而且在製作歷程電子郵件時，任何這些自訂權杖均供個人化使用。<a href="../content/personalization-my-tokens.md">了解更多</a> |
| 功能 | 刪除購買群組階段 | 您可以刪除處於草稿或已發佈狀態的購買群組階段模型。若購買群組階段模型是已發佈 (上線) 狀態，則唯有在其與解決方案無利害關係時，才能刪除。<a href="../buying-groups/buying-group-stages.md#delete-the-buying-group-stages-model">了解更多</a> |
| 增強功能 | 歷程節點數 | 提高在節點層級的已發佈歷程會員數量的可見度。在「_歷程圖_」中，節點顯示「_[!UICONTROL 輸入的帳戶總數]_」。當您選擇並操作節點時，右側的詳細資訊還包括「_[!UICONTROL 尚未採取動作的帳戶]_」。_監聽事件_&#x200B;節點的詳細資訊包括「_[!UICONTROL 此步驟中的帳戶]_」。使用此資訊來驗證已上線、已完成和已中止歷程中的帳戶進度。 |

## 2025.2 發行說明

**部署日期**：2025 年 3 月 11 日

此版本包括下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 功能 | 可自訂欄位 - 內容片段 | 在視覺化片段設計期間，您可以將片段中某個元件的參數指定為可編輯。透過這項功能，電子郵件或範本作者可以根據本身需求指定自訂欄位值。此自訂標幟僅限影像、文字和按鈕視覺元件使用。<a href="../content/fragment-authoring.md#enable-fragment-customization">了解更多</a> |
| 功能 | 歷程重複類型 | 當您重複帳戶歷程時，您可以包含節點詳細資訊，但不包括 Journey Optimizer B2B Edition 中建立的電子郵件和 SMS 訊息。或者，您可以建立結構和路徑流程基本框架的副本，不需要節點詳細資訊和設定。<a href="../journeys/journey-overview.md#duplicate-journey">了解更多</a> |
| 增強功能 | 其他四個電子郵件範本範例 | 電子郵件範本範例資料庫現在包括四個 SecurFinacial 範本，做為重新參與、通知、培養及意見回饋內容範例 |

<!-- | Feature | B2B built-in roles and product permissions | Experience Platform now includes a set of built-in (default) roles that you can use to manage access to the B2B product capabilities. <a href="../admin/user-management.md#b2b-built-in-roles">Learn more</a> <br/>Administrators can now define custom roles in Adobe Experience Platform to include Journey Optimizer B2B Edition product permissions.  <a href="../admin/user-management.md#b2b-product-permissions">Learn more</a> | -->

## 2025.1 發行說明 {#Jan-2025}

**部署日期**：2025 年 2 月 6 日

此版本包括下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 功能 | 體驗事件轉送 | 管理員可以設定基於 Adobe Experience Platform (AEP) 的事件定義。行銷人員可以利用這些設定，建立能回應 AEP 體驗事件的帳戶歷程。<a href="../admin/configure-aep-events.md">了解更多</a> |
| 功能 | 付費媒體目標 | 透過帳戶歷程判斷已知人員是否符合付費媒體行銷活動的資格，以便在 LinkedIn 等廣告平台上進一步與他們互動。在帳戶歷程中使用分割路徑節點，以根據特定行為細分帳戶客群，並找出需要提高參與度的帳戶。然後，透過 Real-time CDP 將這些帳戶中的人員新增至外部客戶客群中，並新增至支援的付費媒體目標。<a href="../journeys/action-nodes.md#journey-optimizer-b2b-actions">了解更多</a> |
| 功能 | 智慧儀表板 | 透過購買群組的帳戶歷程檢視其進度，包括由 AI 產生的深入分析，以便進行智慧化分析和準確的帳戶優先排序。<a href="../dashboards/intelligent-dashboard.md">了解更多</a> |
| 功能 | 購買群組和帳戶詳細資訊 | 檢視購買群組和帳戶層級的深入分析，以便了解更多背景和歷史資料，然後再開始與客戶互動。<p>購買群組詳細資訊包括已偵測到的任何第一方意圖。<a href="../buying-groups/buying-group-details.md">了解更多</a><p>帳戶詳細資訊會加強顯示偵測到參與度的意圖激增情形，以便您可以通知銷售人員注意那些已經準備好接受客製化銷售導向互動的帳戶。<a href="../accounts/account-details.md">了解更多</a> |
| 功能 | 歷程概觀 | 存取帳戶歷程時，「概觀」索引標籤會提供使用中帳戶歷程的綜合概況，並利用圓形圖和長條圖分類及量化完成情況和參與活動，以詳細說明帳戶進度。<a href="../dashboards/journeys-dashboard.md">了解更多</a> |
| 功能 | Adobe Express 影像編輯 | 使用 Adobe Express 快速動作對影像進行簡易編輯 (例如裁切和調整大小)，使內容看起來更精美。<a href="../content/image-edit-adobe-express.md#quick-actions-in-adobe-express">了解更多</a>  <p>為了提供更完整的設計工具組，此整合將完整的 Adobe Express 授權納入 Journey Optimizer B2B Edition。透過此設定，您可以在本機資產工作區內存取完整的 Adobe Express 使用者介面。<a href="../content/image-edit-adobe-express.md#adobe-express-enterprise-license">了解更多</a> |
| 功能 | 購買群組角色的意圖篩選器 | 當您提交意圖關鍵字時，意圖偵測模型會根據某個商機的活動，以足夠高的可信度預測您感興趣的解決方案/產品。<a href="../admin/intent-data.md">了解更多</a> <p>此意圖資料可用於定義購買群組角色條件<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">了解更多</a> |
| 增強功能 | 歷程的 Marketo Engage 事件支援 | _監聽事件_&#x200B;歷程節點現在支援人員層級的兩個 Marketo Engage 事件：_造訪網頁_&#x200B;和&#x200B;_填寫表單_。<a href="../journeys/listen-for-event-nodes.md#listen-for-marketo-engage-event">了解更多</a> |
| 增強功能 | Marketo Engage 智慧清單的購買群組篩選器 | 在 Marketo Engage 中檢視並建立具有購買群組篩選器的智慧清單。這些新增的篩選器可讓您透過 Journey Optimizer B2B Edition 內的帳戶歷程，排除和納入 Marketo Engage 行銷活動和方案中的購買群組成員。<a href="../buying-groups/marketo-engage-smart-list-buying-group-filters.md">了解更多</a> |
| 增強功能 | 歷程和角色的 Marketo Engage 清單成員資格篩選器 | 在 Journey Optimizer B2B 中，選擇 Marketo Engage 清單成員資格做為&#x200B;_根據人員分割路徑_&#x200B;節點的條件，以協助消除歷程活動中的重複項目。<a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">了解更多</a> <p> 針對購買群組角色範本，使用清單成員資格做為角色條件。<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">了解更多</a> |
| 增強功能 | 參與度概觀儀表板 | 此儀表板已更新，可提供參與度的完整檢視。它會透過快照圓形圖表和隨時間變化的趨勢揭露折線圖，展示帳戶和個人互動的即時量度。<a href="../dashboards/engagement-dashboard.md">了解更多</a> |

## 2024 版本

展開以下清單，了解 2024 年發佈的 Journey Optimizer B2B Edition 的功能和增強功能。

+++2024 年 10 月發行說明

**部署日期**：2024 年 10 月 29 日

此版本包括下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 功能 | 電子郵件範本中的條件式內容 | 根據收件者的行為和輪廓特性來製作個人化的電子郵件內容，在帳戶層級或商機層級皆可。 <p>當您在電子郵件視覺化設計空間中為帳戶歷程編寫電子郵件時，請使用條件式規則來定義任何內容元件的多個變體。<a href="../content/conditional-content.md">了解更多</a> |
| 功能 | 歷程中&#x200B;_新增至清單_&#x200B;和&#x200B;_從清單中刪除_&#x200B;的人員動作 | 根據收件者的行為和輪廓特性來製作個人化的電子郵件內容，在帳戶層級或商機層級皆可。<a href="../journeys/action-nodes.md">了解更多</a> |
| 功能 | 內容治理和元件鎖定 | 若要確保遵守已核准的內容設計，請使用內容治理功能來鎖定電子郵件範本內容元件。在電子郵件範本中啟用內容治理後，行銷人員可以僅變更所允許的元素，以確保符合內容策略。<a href="../content/template-content-governance.md">了解更多</a> |
| 功能 | 購買群組階段 | 當您定義並發佈自訂購買群組暫存模型時，您可以透過購買群組生命週期階段來追蹤購買群組進度。使用這些階段來確定購買群組成員的下一步最佳行動。您可以設定轉換規則和歷程節點，以判斷階段進度並根據變更觸發動作。<a href="../buying-groups/buying-group-stages.md">了解更多</a> |
| 增強功能 | 全新現成可用的電子郵件範本 | 此範本範例資料庫現在包括專為 B2B 行銷人員設計的其他電子郵件範本。使用這些範本範例做為起點，並新增您自己的品牌和訊息。<a href="../content/email-templates.md#select-a-design-template">了解更多</a> |
| 增強功能 | 自訂欄位做為人員屬性 | 如果您已在 Experience Platform 的帳戶客群結構描述中定義了自訂人員欄位，則這些欄位也可做為條件中的人員屬性。在下列項目中使用這些自訂屬性： <li>角色範本<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">了解更多</a></li><li>「根據人員分割路徑」歷程節點<a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">了解更多</a></li> |
| 增強功能 | 電子郵件管道設定 | 現在 Journey Optimizer B2B Edition 介面中會顯示電子郵件設定。您可以快速檢視目前設定，且管理員可以按一下「_[!UICONTROL 編輯設定]_」，直接前往 Marketo Engage 中的設定，並根據組織的要求進行更新。<a href="../admin/configure-channels-emails.md">了解更多</a> |

+++

+++2024 年 9 月發行說明

**部署日期**：2024 年 10 月 7 日

此版本包括下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 增強功能 | 中央資產庫 | 增強型&#x200B;_中央資產庫_&#x200B;可讓您在 Design Studio 工作區中使用 Marketo Engage 執行個體中的所有影像資產。內建護欄可防止從 Journey Optimizer B2B Edition 編輯 Marketo Engage 資產，並防止刪除和移動作業。這些保護措施可確保來源資產 (Marketo Engage Design Studio) 獲得妥善維護，同時允許在 Journey Optimizer B2B Edition 中順暢讀取和重複使用。<p>針對專屬 Journey Optimizer B2B Edition 使用的資產，特定的工作區提供完整的資產管理功能。<a href="../content/marketo-engage-design-studio.md">了解更多</a> |
| 功能 | 最近存取的資產 | Journey Optimizer B2B Edition 應用程式中的首頁現在包括「_[!UICONTROL 最近存取]_」區段，為行銷人員或管理員提供最近存取的資產清單。您可以使用此清單直接前往最近處理的資產，不需要導覽一系列的資產頁面及搜尋。 <p>此清單提供有關修改的其他資訊，以便您可以決定上一個工作階段中有哪些資產需要進一步修改。針對電子郵件資產，它顯示使用電子郵件資產的帳戶歷程。<a href="../home-page.md">了解更多</a> |
| 增強功能 | 歷程分割節點 - 重新排序路徑 | 分割路徑節點中的路徑篩選會由上而下進行評估。每位人員或每個帳戶均按照相符的第一條路徑前進。您可以透過點按每個路徑卡右上角的向上鍵和向下鍵來重新排序已定義的路徑，在清單中向上或向下移動。<a href="../journeys/split-merge-paths-nodes.md#split-paths">了解更多</a> |
| 增強功能 | 歷程分割節點 - 其他活動歷史條件屬性 | 當使用條件來定義根據人員分割路徑的路徑篩選時，有兩種附加屬性：_已開啟電子郵件_&#x200B;和&#x200B;_已傳送電子郵件_。這些附加屬性提供更大的彈性，可根據電子郵件活動篩選歷程中的人員。<a href="../journeys/journey-nodes.md#split-paths">了解更多</a> |

+++

+++2024 年 8 月發行說明

**部署日期**：2024 年 8 月 29 日

此版本包括下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 功能 | LinkedIn Account Matched Audiences | 透過 Account Matched Audiences 產生 LinkedIn 廣告客群，以協助您填入購買群組中的空白角色。透過定義一組購買群組篩選器，您可以維護 LinkedIn Matched Audience，以針對符合您的購買群組參數的潛在客戶。 <p>此功能善用 Experience Platform 目標來管理整合的某些部分。<a href="../data/linkedin-account-matched-audiences.md">了解更多</a> |
| 增強功能 | 視覺內容片段的狀態生命週期 | 現在使用狀態生命週期來管理視覺片段。片段狀態決定其是否可用於電子郵件或電子郵件範本，以及您可以對其進行的變更。 <p>此增強型工作流程可讓您輕鬆根據促銷和通訊行事曆來管理重複使用的內容。<a href="../content/fragments.md#fragment-status-and-lifecycle">了解更多</a> |

+++

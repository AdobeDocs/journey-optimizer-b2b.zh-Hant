---
title: 發行說明
description: Adobe Journey Optimizer B2B 版的最新發行說明
exl-id: 7d3f1c26-d8a6-4065-a70f-5b30cb975dc8
source-git-commit: 943dd70a732f8dbcee5c5031c1bc3b15966d66f1
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 9%

---

# Journey Optimizer B2B edition發行說明

Adobe Journey Optimizer B2B edition持續提供新功能、現有功能的增強功能，以及錯誤修正。

Journey Optimizer B2B edition是原生建置在[!DNL Adobe Experience Platform]上，並繼承其最新的創新和改進專案。 欲深入瞭解這些變更，可參閱 [Adobe Experience Platform 發行說明](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/release-notes/latest){target="_blank"}。

檢閱[產品說明](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"}，以取得權益、效能護欄和限制的相關資訊。

## 2025.2版本注意事項

**發行日期**： 2025年3月11日

此版本包含下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 新功能 | 可自訂欄位 — 內容片段 | 作為內容片段設計工具，您可以將片段中元件的引數指定為可編輯。 這可讓電子郵件或範本作者指定其需求專屬的自訂欄位值。 此自訂旗標僅限於影像、文字和按鈕視覺元件。 <a href="../content/fragment-authoring.md#enable-custom-fields">了解更多</a> |
| 新功能 | B2B內建角色和產品許可權 | Experience Platform現在包含一組內建（預設）角色，您可以使用這些角色來管理對B2B產品功能的存取。 <a href="../admin/user-management.md#b2b-built-in-roles">了解更多</a> <br/>管理員現在可以在Adobe Experience Platform中定義自訂角色，以包含Journey Optimizer B2B edition產品許可權。  <a href="../admin/user-management.md#b2b-product-permissions">了解更多</a> |
| 增強功能 | 其他四個範例電子郵件範本 | 範例電子郵件範本資料庫現在包含四個SecureFinacial範本，作為重新參與、通知、培養和回饋內容範例的範例 |



## 2025.1版本注意事項 {#Jan-2025}

**發行日期**：2025年2月6日

此版本包含下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 新功能 | 體驗事件轉送 | 管理員可以設定以Adobe Experience Platform (AEP)為基礎的事件定義。 這些設定可讓行銷人員建立對AEP體驗事件做出反應的帳戶歷程。  <a href="../admin/configure-aep-events.md">了解更多</a> |
| 新功能 | 付費媒體目的地 | 將帳戶歷程中的付費媒體行銷活動限定給已知人員，以便您可以在LinkedIn等廣告平台上進一步與他們互動。 在帳戶歷程中使用分割路徑節點，根據特定行為來細分帳戶對象，並識別需要額外參與的帳戶。 然後，透過Real-time CDP將人員從這些帳戶新增到外部客戶受眾到支援的付費媒體目的地。 <a href="../journeys/action-nodes.md#journey-optimizer-b2b-actions">了解更多</a> |
| 新功能 | 智慧型儀表板 | 透過帳戶歷程檢視購買群組的進度，包括AI產生的深入分析，以獲得更聰明的分析和準確的帳戶優先順序。 <a href="../dashboards/intelligent-dashboard.md">了解更多</a> |
| 新功能 | 購買群組和帳戶詳細資料 | 檢視購買群組和帳戶層級的深入分析，以便在您開始與客戶互動時擁有更多情境和歷史資料。<p>購買群組詳細資訊包括偵測到的任何第一方意圖。 <a href="../buying-groups/buying-group-details.md">了解更多</a><p>帳戶詳細資料帳戶會強調偵測到參與激增的意圖，因此您可以提醒銷售人員注意已準備好進行客製化以銷售為中心的參與的帳戶。  <a href="../accounts/account-details.md">了解更多</a> |
| 新功能 | 歷程概觀 | 當您存取帳戶歷程時，「概觀」標籤會提供作用中帳戶歷程的完整快照，使用圓圈和長條圖來詳細描述帳戶進度，該圖表會分類並量化完成和參與活動。  <a href="../dashboards/journeys-dashboard.md">了解更多</a> |
| 新功能 | Adobe Express影像編輯 | Adobe Express快速動作可讓您對影像進行簡單的編輯（例如裁切和調整大小），以便在內容中呈現更精美的外觀。 <a href="../content/image-edit-adobe-express.md#quick-actions-in-adobe-express">了解更多</a>  <p>如需更完整的設計工具集，此整合可為Journey Optimizer B2B edition啟用完整的Adobe Express授權。 完成此設定後，即可在本機資產工作區中存取完整的Adobe Express使用者介面。 <a href="../content/image-edit-adobe-express.md#adobe-express-enterprise-license">了解更多</a> |
| 新功能 | 購買群組角色的意圖篩選器 | 當您提交意圖關鍵字時，意圖偵測模型會根據潛在客戶的活動，以足夠高的信賴度預測感興趣的解決方案/產品。 <a href="../admin/intent-data.md">了解更多</a> <p>此意圖資料可用於定義購買群組角色條件<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">深入瞭解</a> |
| 增強功能 | 歷程中的Marketo Engage事件支援 | _接聽事件_&#x200B;歷程節點現在支援人員層級的兩個Marketo Engage事件： _造訪網頁_&#x200B;和&#x200B;_填寫表單_。 <a href="../journeys/listen-for-event-nodes.md#listen-for-marketo-engage-event">了解更多</a> |
| 增強功能 | 購買Marketo Engage智慧清單的群組篩選器 | 在Marketo Engage中使用購買群組篩選器來檢視和建立智慧清單。 這些新增的篩選器可讓您從Journey Optimizer B2B edition內的帳戶歷程中，隱藏並包含跨Marketo Engage促銷活動和方案購買群組成員。 <a href="../buying-groups/marketo-engage-smart-list-buying-group-filters.md">了解更多</a> |
| 增強功能 | Marketo Engage列出歷程和角色的成員資格篩選器 | 在Journey Optimizer B2B中，檢查Marketo Engage清單成員資格是否為&#x200B;_依人員_&#x200B;節點分割路徑的條件，以協助消除歷程活動中的重複。 <a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">了解更多</a> <p> 若要購買群組角色範本，請使用清單成員資格作為角色條件。 <a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">了解更多</a> |
| 增強功能 | 參與總覽儀表板 | 此儀表板已更新，以提供參與度的完整檢視。 它會透過快照圓形圖和趨勢顯示折線圖，顯示帳戶和個別互動隨時間變化的即時量度。 <a href="../dashboards/engagement-dashboard.md">了解更多</a> |


## 2024 年 10 月發行說明 {#Oct-2024}

**發行日期**： 2024年10月29日

此版本包含下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 新功能 | 電子郵件範本中的條件式內容 | 根據帳戶和潛在客戶層級的收件者行為和設定檔特性，個人化您的電子郵件內容。 <p>當您在電子郵件視覺化設計空間為您的帳戶歷程撰寫電子郵件時，請使用條件規則來定義任何內容元件的多個變體。 <a href="../content/conditional-content.md">了解更多</a> |
| 新功能 | _新增至清單_&#x200B;和&#x200B;_從清單移除_&#x200B;歷程中的人員動作 | 根據帳戶和潛在客戶層級的收件者行為和設定檔特性，個人化您的電子郵件內容。 <a href="../journeys/action-nodes.md">了解更多</a> |
| 新功能 | 內容控管和元件鎖定 | 為確保遵循核准的內容設計，請使用內容控管功能來鎖定電子郵件範本內容元件。 在電子郵件範本中啟用內容控管後，行銷人員可以僅變更允許的元素，以使其與內容策略一致。 <a href="../content/template-content-governance.md">了解更多</a> |
| 新功能 | 購買群組階段 | 當您定義並發佈自訂購買群組測試模型時，可以透過購買群組生命週期階段追蹤購買群組進度。 使用這些階段來識別購買群組成員的下一個最佳動作。 您可以設定轉變規則和歷程節點，以決定階段進度並根據變更觸發動作。 <a href="../buying-groups/buying-group-stages.md">了解更多</a> |
| 增強功能 | 全新現成可用的電子郵件範本 | 範例範本資料庫現在包含其他針對B2B行銷人員設計的電子郵件範本。 使用這些範例範本作為起點，並新增您自己的品牌和訊息。 <a href="../content/email-templates.md#select-a-design-template">了解更多</a> |
| 增強功能 | 自訂欄位做為個人屬性 | 如果您在Experience Platform的帳戶對象結構描述中定義了自訂人員欄位，這些欄位也可在條件中作為人員屬性使用。 在下列位置使用這些自訂屬性： <li>角色範本<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">深入瞭解</a></li><li>依人員歷程節點分割路徑<a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">瞭解更多</a></li> |
| 增強功能 | 電子郵件通道設定 | 電子郵件設定現在顯示在Journey Optimizer B2B edition介面中。 您可以快速檢閱目前的設定，而管理員可以按一下[編輯設定]，直接移至Marketo Engage中的設定，並根據您組織的需求進行更新。 __<a href="../admin/configure-channels-emails.md">了解更多</a> |

## 2024 年 9 月發行說明 {#Sept-2024}

**發行日期**：2024年10月7日

此版本包含下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 增強功能 | 中央資產庫 | 增強型&#x200B;_中央資產庫_&#x200B;可讓您在Design Studio工作區中，使用Marketo Engage執行個體中的所有影像資產。 有內建的護欄可防止從Journey Optimizer B2B edition編輯Marketo Engage資產，以及執行刪除和移動作業。 這些保護功能可確保維護來源資產(Marketo Engage Design Studio)，同時允許在Journey Optimizer B2B edition中順暢地讀取和重複使用。<p>針對專供Journey Optimizer B2B edition使用的資產，特定工作區提供完整的資產管理功能。 <a href="../content/marketo-engage-design-studio.md">了解更多</a> |
| 新功能 | 最近存取的資產 | Journey Optimizer B2B edition應用程式中的首頁現在包含&#x200B;_[!UICONTROL 最近存取的]_&#x200B;區段，此區段提供行銷人員或管理員最近存取的資產清單。 您可以使用此清單直接前往您最近處理的資產，而不需導覽一連串資產頁面並搜尋。 <p>清單提供有關修改的其他資訊，以便您決定哪些資產需要從上次作業階段進一步修改。 對於電子郵件資產，這會顯示使用電子郵件資產的帳戶歷程。 <a href="../home-page.md">了解更多</a> |
| 增強功能 | 歷程分割節點 — 重新排序路徑 | 在分割路徑節點中，路徑篩選會以由上到下的順序評估。 每個人或帳戶都會沿著第一個相符的路徑前進。 您可以按一下每個路徑卡右上角的向上和向下箭頭，將已定義的路徑重新排序，以在清單中將其向上或向下移動。 <a href="../journeys/split-merge-paths-nodes.md#split-paths">了解更多</a> |
| 增強功能 | 歷程分割節點 — 其他活動歷史記錄條件屬性 | 使用條件來定義依人員分割節點的路徑篩選時，有兩個額外的屬性： _已開啟的電子郵件_&#x200B;和&#x200B;_已傳遞的電子郵件_。 這些新增內容提供更大的彈性，可依據電子郵件活動篩選歷程中的人員。 <a href="../journeys/journey-nodes.md#split-paths">了解更多</a> |

## 2024 年 8 月發行說明 {#Aug-2024}

**發行日期**： 2024年8月29日

此版本包含下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 新功能 | LinkedIn帳戶比對的對象 | 透過帳戶相符對象產生LinkedIn廣告對象，協助您在購買群組中填入空白角色。 透過定義一組購買群組篩選器，您可以維護「LinkedIn相符對象」，以鎖定符合您購買群組引數的潛在客戶。 <p>此功能可運用Experience Platform目的地來管理整合的某些層面。 <a href="../data/linkedin-account-matched-audiences.md">了解更多</a> |
| 增強功能 | 視覺內容片段的狀態生命週期 | 視覺片段現在可使用狀態生命週期來管理。 片段狀態會決定其是否可用於電子郵件或電子郵件範本，以及您可以對其進行的變更。 <p>此增強型工作流程可讓您根據促銷和通訊行事曆，輕鬆管理重複使用的內容。 <a href="../content/fragments.md#fragment-status-and-lifecycle">了解更多</a> |

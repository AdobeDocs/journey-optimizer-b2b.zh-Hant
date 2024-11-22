---
title: 發行說明
description: Adobe Journey Optimizer B2B 版的最新發行說明
exl-id: 7d3f1c26-d8a6-4065-a70f-5b30cb975dc8
source-git-commit: 18a9f073f5c898d01c075611c6808d192d71dbc7
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 10%

---

# Journey Optimizer B2B edition發行說明

Adobe Journey Optimizer B2B edition持續提供新功能、現有功能的增強功能，以及錯誤修正。

Journey Optimizer B2B edition是原生建置在[!DNL Adobe Experience Platform]上，並繼承其最新的創新和改進專案。 欲深入瞭解這些變更，可參閱 [Adobe Experience Platform 發行說明](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/release-notes/latest){target="_blank"}。

檢閱[產品說明](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"}，以取得權益、效能護欄和限制的相關資訊。

## 2024 年 10 月發行說明 {#Oct-2024}

**發行日期**： 2024年10月29日

此版本包含下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 新功能 | 電子郵件範本中的條件式內容 | 根據帳戶和潛在客戶層級的收件者行為和設定檔特性，個人化您的電子郵件內容。 <p>當您在電子郵件設計工具中針對您的帳戶歷程製作電子郵件時，請使用條件規則來定義任何內容元件的多個變體。 <a href="../content/conditional-content.md">了解更多</a> |
| 新功能 | _新增至清單_&#x200B;和&#x200B;_從清單移除_&#x200B;歷程中的人員動作 | 根據帳戶和潛在客戶層級的收件者行為和設定檔特性，個人化您的電子郵件內容。 <a href="../journeys/journey-nodes.md#action-nodes">了解更多</a> |
| 新功能 | 內容控管和元件鎖定 | 為確保遵循核准的內容設計，請使用內容控管功能來鎖定電子郵件範本內容元件。 在電子郵件範本中啟用內容控管後，行銷人員可以僅變更允許的元素，以使其與內容策略一致。 <a href="../content/template-content-governance.md">了解更多</a> |
| 新功能 | 購買群組階段 | 當您定義並發佈自訂購買群組測試模型時，可以透過購買群組生命週期階段追蹤購買群組進度。 使用這些階段來識別購買群組成員的下一個最佳動作。 您可以設定轉變規則和歷程節點，以決定階段進度並根據變更觸發動作。 <a href="../buying-groups/buying-group-stages.md">了解更多</a> |
| 增強功能 | 全新現成可用的電子郵件範本 | 範例範本資料庫現在包含其他針對B2B行銷人員設計的電子郵件範本。 使用這些範例範本作為起點，並新增您自己的品牌和訊息。 <a href="../content/email-templates.md#select-a-design-template">了解更多</a> |
| 增強功能 | 自訂欄位做為個人屬性 | 如果您在Experience Platform的帳戶對象結構中定義了自訂人員欄位，這些欄位也可在條件中作為人員屬性使用。 在下列位置使用這些自訂屬性： <li>角色範本<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">深入瞭解</a></li><li>依人員歷程節點分割路徑<a href="../journeys/journey-nodes.md#add-a-split-path-by-people-node">瞭解更多</a></li> |
| 增強功能 | 電子郵件通道設定 | 電子郵件設定現在顯示在Journey Optimizer B2B edition介面中。 您可以快速檢閱目前的設定，管理員可以按一下[編輯設定]，直接移至Marketo Engage中的設定，並根據您組織的需求進行更新。 __<a href="../admin/configure-channels-emails.md">了解更多</a> |

## 2024 年 9 月發行說明 {#Sept-2024}

**發行日期**：2024年10月7日

此版本包含下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 增強功能 | 中央資產庫 | 增強型&#x200B;_中央資產庫_&#x200B;可讓您在Design Studio工作區中，使用Marketo Engage執行個體中的所有影像資產。 有內建的護欄可防止從Journey Optimizer B2B edition編輯Marketo Engage資產，以及執行刪除和移動作業。 這些保護功能可確保維護來源資產(Marketo Engage Design Studio)，同時允許在Journey Optimizer B2B edition中順暢地讀取和重複使用。<p>針對專供Journey Optimizer B2B edition使用的資產，特定工作區提供完整的資產管理功能。 <a href="../content/marketo-engage-design-studio.md">了解更多</a> |
| 新功能 | 最近存取的資產 | Journey Optimizer B2B edition應用程式中的首頁現在包含&#x200B;_[!UICONTROL 最近存取的]_&#x200B;區段，此區段提供行銷人員或管理員最近存取的資產清單。 您可以使用此清單直接前往您最近處理的資產，而不需導覽一連串資產頁面並搜尋。 <p>清單提供有關修改的其他資訊，以便您決定哪些資產需要從上次作業階段進一步修改。 對於電子郵件資產，這會顯示使用電子郵件資產的帳戶歷程。 <a href="../home-page.md">了解更多</a> |
| 增強功能 | 歷程分割節點 — 重新排序路徑 | 在分割路徑節點中，路徑篩選會以由上到下的順序評估。 每個人或帳戶都會沿著第一個相符的路徑前進。 您可以按一下每個路徑卡右上角的向上和向下箭頭，將已定義的路徑重新排序，以在清單中將其向上或向下移動。 <a href="../journeys/journey-nodes.md#split-paths">了解更多</a> |
| 增強功能 | 歷程分割節點 — 其他活動歷史記錄條件屬性 | 使用條件來定義依人員分割節點的路徑篩選時，有兩個額外的屬性： _已開啟的電子郵件_&#x200B;和&#x200B;_已傳遞的電子郵件_。 這些新增內容提供更大的彈性，可依據電子郵件活動篩選歷程中的人員。 <a href="../journeys/journey-nodes.md#split-paths">了解更多</a> |

## 2024 年 8 月發行說明 {#Aug-2024}

**發行日期**： 2024年8月29日

此版本包含下列新功能和增強功能：

| 類型 | 項目 | 說明 |
| ---- | ---- | ----------- |
| 新功能 | linkedIn帳戶比對的對象 | 透過帳戶相符對象產生LinkedIn廣告對象，協助您在購買群組中填入空角色。 透過定義一組購買群組篩選器，您可以維護「LinkedIn相符對象」，以鎖定符合您購買群組引數的潛在客戶。 <p>此功能可運用Experience Platform目的地來管理整合的某些層面。 <a href="../data/linkedin-account-matched-audiences.md">了解更多</a> |
| 增強功能 | 視覺內容片段的狀態生命週期 | 視覺片段現在可使用狀態生命週期來管理。 片段狀態會決定其是否可用於電子郵件或電子郵件範本，以及您可以對其進行的變更。 <p>此增強型工作流程可讓您根據促銷和通訊行事曆，輕鬆管理重複使用的內容。 <a href="../content/fragments.md#fragment-status-and-lifecycle">了解更多</a> |

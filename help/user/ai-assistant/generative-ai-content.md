---
title: 內容的Generative AI
description: 瞭解如何在 [!DNL Journey Optimizer B2B Edition]中使用generative AI建立個人化電子郵件和登陸頁面，包括提示最佳實務。
feature: AI Assistant, Generative AI, Content
level: Beginner
topic: Artificial Intelligence
role: User
exl-id: 36baf7f9-2fff-4c33-bca0-7d43ec48e74a
source-git-commit: ce4df9a2726cf842c088738521b3e5dd88dd768f
workflow-type: tm+mt
source-wordcount: '2506'
ht-degree: 2%

---

# 內容的Generative AI {#generative-ai-content}

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-settings"
>title="AI內容產生"
>abstract="完成版面設計後，您可以在[!DNL Journey Optimizer B2B Edition]中使用創作AI工具來增強您的內容。 此功能會根據您的描述性提示微調內容，以簡化個人化和內容改善的程式。"

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-reference-context"
>title="參考內容"
>abstract="使用&#x200B;_參考內容_&#x200B;上傳包含內容的資產檔案，該內容為[!DNL Journey Optimizer B2B Edition]中的產生AI提供額外的內容，或是選取先前上傳的檔案。 此選項可確保提供所有必要的素材，以提高產生內容的品質和相關性。"

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-start"
>title="Adobe generative AI辭彙"
>abstract="要存取此功能，您必須同意 Adobe Experience Cloud 生成式 AI 使用者準則。 請檢閱此功能的任何輸出是否準確，並確定其適合您的使用案例。"
>additional-url="https://www.adobe.com/tw/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html" text="Adobe 生成式 AI 使用者準則"

由Microsoft Azure OpenAI和Adobe Firefly提供技術支援的[!DNL Adobe Journey Optimizer B2B Edition]內容創作AI，可提供文字和影像的主動式內容變化建議。 透過實驗不同的主要標題和影像，最佳化您的內容影響力。

在[!DNL Journey Optimizer B2B Edition]中使用創作AI功能來建立內容，以利用Adobe的創作AI功能。 製作電子郵件、SMS訊息、登陸頁面等的個人化文字和視覺效果。 當您建立完整的行銷活動或只是修訂特定資產時，這些功能可幫助您順暢地將內容與品牌准則保持一致，同時節省寶貴的時間。

<!--
Generate multiple variants and build an experiment to compare them. Leveraging Journey Optimizer Content Experiment, you can define multiple message treatments to measure which one performs best for your target audience. You can choose to vary the delivery content, or subject. The message audience is randomly allocated to each treatment to determine which one works best in terms of the specified metric. Learn more about Content Experiment in this section. -->

>[!IMPORTANT]
>
>若要在[!DNL Journey Optimizer B2B Edition]中存取這些功能，您必須擁有&#x200B;_[!UICONTROL AI小幫手]_ > _[!UICONTROL 產生內容]_&#x200B;許可權。 如需產品管理員如何授與功能許可權的詳細資訊，請參閱[編輯產品許可權的角色](../admin/user-management.md#edit-roles-for-product-permissions)。

以下資產型別支援用於產生內容的AI助理工具：

* [電子郵件](../content/ai-assistant-emails.md)
* [!BADGE Beta] [登陸頁面](../content/ai-assistant-landing-pages.md)

## 一般准則和限制 {#general-guidelines-and-limitations}

您對generative AI功能的使用須遵守[Adobe Experience Cloud Generative AI使用指南](https://www.adobe.com/tw/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}。 由於Adobe承諾在使用創作AI工具建立媒體時保持透明度，因此Adobe會在下載或匯出內容或專案時，針對包含[!DNL Firefly]產生的資產的任何內容或專案套用[內容認證](https://helpx.adobe.com/firefly/web/get-started/learn-the-basics/content-credentials-overview.html){target="_blank"}。

檢閱針對[!DNL Journey Optimizer B2B Edition]中的內容使用創作AI的一般准則：

* 為產生式AI模型使用定義良好的提示，以精確解釋。 您提供的行銷目標或提示強烈會影響產生內容的品質。

* 上傳內容參考檔案，以擁有正確的品牌內內容。 否則，內容會以公開可得的資訊為基礎。 上傳的內容可以採用以下檔案格式：PDF、JPEG、PNG或ZIP （包含支援的檔案格式）。 上傳檔案的大小上限為50MB。 大型檔案或大量影像可以運作，但這會增加處理時間。

* 使用品牌特定或自訂範本來建立您的電子郵件內容。 建議使用最多8至10個影像的電子郵件範本。

* 選擇變體時，請務必使用向上縮圖、向下縮圖或標幟圖示來報告任何有問題的輸出。

## 提示創作AI的最佳實務 {#generative-ai-prompting-guide}

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai_content_prompt"
>title="即時指南"
>abstract="探索[!DNL Journey Optimizer B2B Edition]檔案，瞭解如何建立有效的提示，以產生高轉換率的品牌上行銷內容。"

本指南可協助您建構請求、清楚傳達意圖，並確保AI產生的訊息符合您的品牌指引、受眾需求和行銷活動目標。

瞭解如何撰寫有效提示，讓AI助理產生為您的目標量身打造的高品質品牌行銷內容。

### 使用CO-STAR架構 {#costar-framework}

為了獲得產生內容的最佳結果，請使用CO-STAR框架組織您的提示。 這種結構化的方法能讓您清楚瞭解確切的需求。

| 元件 | 其含義 | 為何這項能力很重要 |
| --- | ---- | ------ |
| **C — 內容** | 有關您的行銷活動、產品或情況的背景 | 有助於瞭解整體情況 |
| **O — 目標** | 您的特定行銷目標 | 推動內容應達到的目標 |
| **— 樣式** | 您想要如何溝通 | 設定方法 |
| **T — 音調** | 情感風格和聲音 | 塑造您訊息的感受 |
| **A — 對象** | 您正在定位的對象 | 確保訊息可與適當的人產生共鳴 |
| **R — 需求** | 特定限制或必備條件 | 定義邊界和關鍵元素 |

{style="table-layout:fixed"}

### 提示要點 {#key-takeaways}

<table style="table-layout: fixed; width: 100%; border: 0;">
<thead style="border: 0; background-color: #FFFFFF;">
<tr>
<th>執行</th>
<th>不要</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<ul><li>使用CO-STAR架構進行結構
<li>明確說明最新內容和現有內容
<li>透過特定的摘取指南提供檔案使用的焦點
<li>選取色調、策略和區域設定
<li>匹配行銷目標與內容型別功能
<li>產生A/B測試的多個變體</ul>
</td>
<td>
<ul><li>在提示中要求結構變更、樣式或影像編輯
<li>在提示中提及膚色/策略（如果選項中有的話）
<li>使用模糊的目標，例如_promote產品_
<li>要求條件元素選取專案
<li>透過提示預期版面修改</ul>
</td>
</tr>
</tbody>
</table>

### 提示中不支援的內容

>[!TIP]
>
>使用設計工具或[!DNL Adobe Express]進行視覺/影像修改。

下列要求&#x200B;**_不受支援_**，應該透過其他工具處理：

<table style="table-layout: fixed; border: 0;">
<thead style="border: 0; background-color: #FFFFFF">
<tr>
<th><img src="../../assets/do-not-localize/check-box-red.svg" alt="紅色劃線">  電子郵件結構修改</th>
<th><img src="../../assets/do-not-localize/check-box-red.svg" alt="紅色劃線">  視覺樣式變更</th>
<th><img src="../../assets/do-not-localize/check-box-red.svg" alt="紅色劃線">  影像編輯作業</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<ul>
<li>選取要變更的特定區段</li>
<li>刪除或複製元素</li>
<li>條件式選取專案</li>
<li>新增或移除配置區段</li>
</ul>
</td>
<td>
<ul>
<li>文字格式（粗體、斜體、字型大小）</li>
<li>色彩修改</li>
<li>版面樣式（框線、邊框間距、邊界）</li>
<li>視覺效果（陰影）</li>
</ul>
</td>
<td>
<ul>
<li>背景變更</li>
<li>新增文字覆蓋圖或標誌</li>
<li>影像裁切或調整大小</li>
<li>色彩調整</li>
<li>影像取代</li>
</ul>
</td>
</tr>
</tbody>
</table>

### 品質檢查清單 {#quality-checklist}

在產生內容之前，請先確定下列事項：

![綠色核取記號](../../assets/do-not-localize/check-box-green.svg){width="20"} **清除目標**：清楚說明動作、產品/服務、值和內容。

![綠色核取記號](../../assets/do-not-localize/check-box-green.svg){width="20"} **已定義的目標對象**：指定人口統計、角色或區段。

![綠色核取記號](../../assets/do-not-localize/check-box-green.svg){width="20"} **內容型別對齊方式**：目標符合選取的管道或格式。

![綠色核取記號](../../assets/do-not-localize/check-box-green.svg){width="20"} **檢閱選取專案**：已選取音調、策略和地區設定，請勿將其納入提示中。

![綠色核取記號](../../assets/do-not-localize/check-box-green.svg){width="20"} **已指定檔案焦點**：強調要參考的內容或區段。

![綠色核取記號](../../assets/do-not-localize/check-box-green.svg){width="20"} **已套用品牌**：已選取適當的品牌准則。

![綠色核取記號](../../assets/do-not-localize/check-box-green.svg){width="20"} **實際範圍**：避免請求配置變更、樣式或結構編輯。

### 有效的行銷目標 {#marketing-objectives}

制定行銷目標時，請確定目標清晰、可操作且可衡量。 避免使用模糊或泛型陳述式。

**好目標的範例：**

![綠色核取記號](../../assets/do-not-localize/check-box-green.svg){width="20"}「新增AI支援的分析儀表板的免費30天試用期硬碟註冊」

![綠色勾號](../../assets/do-not-localize/check-box-green.svg){width="20"} 「3月15日進行『減少40%的雲端成本』的B2B網路研討會潛在客戶」

![綠色勾號](../../assets/do-not-localize/check-box-green.svg){width="20"} 「促銷進階訂閱的限定時間25%折扣，截止於12月25日」

**要避免的範例：**

![紅色劃線](../../assets/do-not-localize/check-box-red.svg){width="20"} 「促銷產品」（太模糊）

![紅色劃線](../../assets/do-not-localize/check-box-red.svg){width="20"} 「讓人簽署交易」（價值不明）

![紅色劃線](../../assets/do-not-localize/check-box-red.svg){width="20"} 「關於新功能的電子郵件」（缺乏目的）

#### 建構您的目標

一律提供內容與價值主張，以產生相關內容。 使用下列公式來協助您撰寫有效目標： **動作+產品/服務+值/利益+緊急事項/內容**

**好目標的範例：**

![綠色勾號](../../assets/do-not-localize/check-box-green.svg){width="20"} 「鼓勵下載新的行動應用程式，透過個人化的環保建議，協助使用者追蹤可持續的生活習慣」

![綠色核取記號](../../assets/do-not-localize/check-box-green.svg){width="20"} 「推廣行銷專業人員進階資料視覺化技術專屬研討會的報名」

![綠色核取記號](../../assets/do-not-localize/check-box-green.svg){width="20"} 「推動產品上市活動的出席率，展示革命性的AI撰寫助理，每週可節省5小時以上的時間」

**要避免的範例：**

![紅色劃線](../../assets/do-not-localize/check-box-red.svg){width="20"} 「宣告新的應用程式」（缺少值主張和內容）

![紅十字會](../../assets/do-not-localize/check-box-red.svg){width="20"} 「讓人員報名參加工作坊」（缺乏對象和權益的特定性）

![紅色劃線](../../assets/do-not-localize/check-box-red.svg){width="20"}「促銷活動」（無明確的動作、值或緊急程度）

#### 依據管道型別的提示範例 {#channel-type-practices}

<table style="table-layout: auto; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>頻道</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>電子郵件</strong></td>
<td>「透過詳細ROI指標展示三個客戶成功案例，以培育企業潛在客戶(Oracle：成本降低45%、Accenture：銷售機會增加200%、Microsoft：節省時間60%)。 針對擁有1000名以上員工的公司的IT主管」</td>
</tr>
<tr>
<td><strong>登陸頁面</strong></td>
<td>「透過展示企業安全性解決方案如何防止99.9%的網路攻擊，利用《財富》500強推薦和免費的安全性稽核，將B2B訪客轉化為合格的銷售機會」</td>
</tr>
</tbody>
</table>

<!-- channels not yet supported
<tr>
<td><strong>SMS</strong></td>
<td>"Alert VIP customers about a 4-hour flash sale on premium electronics with 40% discount, limited to the first 100 customers"</td>
</tr>
<tr>
<td><strong>Push Notifications</strong></td>
<td>"Re-engage users who haven't opened the app in 7 days with personalized content recommendations based on their reading history"</td>
</tr> -->

<!-- Wait on more B2B specific examples

### Industry-specific approaches {#industry-approaches}

<table style="table-layout: fixed; border-collapse: collapse; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>Industry</th>
<th>Example Prompt</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>B2B Technology</strong></td>
<td>"Demonstrate ROI and technical specifications while addressing security concerns for IT decision-makers evaluating our cloud infrastructure solution, emphasizing 99.9% uptime SLA, SOC 2 compliance, and 40% cost savings."</td>
</tr>
<tr>
<td><strong>E-commerce Retail</strong></td>
<td>"Create urgency around limited-stock holiday items while highlighting free shipping and easy returns for last-minute shoppers, emphasizing limited quantities (less than 50 remaining) and 24-hour shipping cutoff."</td>
</tr>
<tr>
<td><strong>Financial Services</strong></td>
<td>"Educate clients about investment portfolio diversification strategies while maintaining regulatory compliance, featuring certified financial advisor insights and risk disclaimers."</td>
</tr>
<tr>
<td><strong>Healthcare & Wellness</strong></td>
<td>"Promote preventive care benefits and annual health screenings while maintaining medical accuracy, featuring board-certified physician recommendations and patient privacy assurances."</td>
</tr>
<tr>
<td><strong>Education & Training</strong></td>
<td>"Emphasize career advancement outcomes and industry certifications while showcasing instructor expertise, highlighting 92% job placement rate and project-based curriculum."</td>
</tr>
<tr>
<td><strong>SaaS Platforms</strong></td>
<td>"Highlight time savings and automation benefits with specific metrics while addressing integration concerns, featuring average 25-hour weekly time savings and integration with 200+ popular tools."</td>
</tr>
</tbody>
</table>
 -->

### 新內容與修改現有內容的比較 {#new-vs-modify}

清楚指出您的請求是否涉及產生新內容或更新現有資料。 這種區分很重要，因為它會引導AI選取適當的方法，並確保獲得更準確和有用的結果。

#### 建立新內容

當您啟動行銷活動、推出新解決方案或起始更新/重新整理的通訊時，請套用此策略。 這可確保您的訊息開始強有力並與目標一致。

**如何提示** ➤建立新內容時，請專注於您的行銷目標，而不參考現有內容。

>[!BEGINSHADEBOX 「範例」]

* **SaaS試用版**：「向小型企業所有者推出新的CRM軟體，強調可節省50%的時間、加快90%的銷售機會認證，並提供30天的免費試用版並提供個人化入門」
* **功能宣告**：「宣佈新的API整合功能，將企業客戶的開發時間縮短60%，目標鎖定於技術決策者」
* **活動促銷活動**： 「推動『Digital Marketing Trends 2024』網路研討會的註冊，邀請Google、Meta和Adobe的專家參加，強調可操作的深入分析和有限的座位（最多500個）」

>[!ENDSHADEBOX]

#### 修改現有內容

>[!TIP]
>
>若要進行標準修改，例如精緻、摘要或簡化，請選取&#x200B;**_調整_**，而非撰寫自訂提示。

當您需要更新、重新整理或調整目前的行銷活動時，請使用修改提示。 此方法支援漸進式改進，可確保您的傳訊保持相關性，而不從頭開始。

**如何提示** ➤修改現有內容時，請明確指定您要變更的內容及變更方法。

>[!BEGINSHADEBOX 「範例」]

* **行銷活動重新整理**：「修改方案啟動電子郵件，以專注於企業安全性功能，而非一般生產力優勢，並以符合規範認證的IT決策者為目標」
* **對象樞紐**：「調整軟體示範邀請以專門針對醫療保健，取代一般範例與醫療保健使用案例及HIPAA法規遵循權益」
* **季節性更新**：「更新第4季節日購物的第3季促銷活動，將焦點從開學到送禮轉換到強調快速送貨的節日禮物贈送」

>[!ENDSHADEBOX]

## 進階文字設定 {#text-settings}

除了使用清楚且格式正確的提示外，AI助理員內容工具中的文字設定還包括可用來最佳化產生輸出的文字設定。

>[!TIP]
>
>在&#x200B;_[!UICONTROL 文字設定]_&#x200B;中使用&#x200B;_[!UICONTROL 通訊策略]_&#x200B;和&#x200B;_[!UICONTROL 色調]_&#x200B;選項，而不是在提示中提及這些特性。

### 通訊策略型別

您的溝通策略會決定如何呈現訊息，以發揮最大影響力。 不同的策略對於不同的目標會有更好的效果，無論您是要建立緊迫感、建立信任，還是要立即採取行動。 選擇最符合您的行銷活動目標和對象心態的策略。

| **策略** | **最適合** | **傳訊樣式** | **範例** |
| ------------ | ------------ | ------------------- | ------------ |
| **緊急** | 時效性要求高的優惠、截止日期、立即行動 | 使用以時間為基礎的語言建立立即的壓力 | <li>「立即行動：優惠方案將於午夜到期」 <li>「在積分填滿前立即報名」 <li>「48小時閃電優惠開始啦」 |
| **FOMO （害怕遺漏）** | 有限的優惠、事件、獨佔存取 | 使用急迫性、稀缺性和時間壓力提示 | <li>「只剩下24小時了！ 有限公司現享40%優惠」 <li>「最後機會：早鳥定價明天結束」 <li>「只剩下100個Beta測試版位置」 |
| **社交校訂** | 建立信任、口碑、熱門產品 | 運用其他人的體驗和驗證 | <li>「加入50,000多個滿意的客戶」 <li>「業界專業人士評為4.9/5顆星」 <li>「受《財富》500強企業信任」 |
| **稀缺** | 有限存貨、獨佔核發、高需求料號 | 強調可用性有限和專屬性 | <li>「庫存只剩下5隻」 <li>「限量版：100個可用單位」 <li>「獨家發行：先到先得」 |
| **獎勵** | 促銷活動、獎勵計畫、特殊優惠 | 強調實實在在的好處和回報 | <li>「第一筆訂單優惠20%」 <li>「本週末可賺到兩分」 <li>「超過$50美元的訂單提供免運費」 |
| **排他性** | 進階產品、VIP體驗、僅限成員的選件 | 使用高階定位與特殊存取語言 | <li>「私人預覽的專屬邀請」 <li>「菁英會籍開啟進階分析」 <li>「加入使用我們的精選《財富》500強公司」 |
| **Gamification** | 參與行銷活動、忠誠度方案、互動式內容 | 使用遊戲機制與成就語言 | <li>「解鎖您的下一個獎勵等級」 <li>「贏取徽章的完整挑戰」 <li>「攀登獨家獎項的排行榜」 |
| **資訊** | 教育、研究、複雜產品、思想領導力 | 使用事實、資料、見解和說明 | <li>「分析10,000多個互動獲得5個深入見解」 <li>「最新研究揭示3種突破性方法」 <li>「在行銷中實作AI的完整指南」 |
| **教育與見解** | 學習內容、產業趨勢、最佳實務 | 提供寶貴的知識和可操作的外包 | <li>「透過專家指南學習進階技術」 <li>「探索7大行銷人員使用的策略」 <li>「瞭解如何在5個步驟中最佳化您的工作流程」 |

### 設定正確的色調 {#tone}

語調會決定您的對象如何看待和回應您的訊息。 請一律選取符合您品牌語調和個人資料歷程階段的語調。

檢閱可用的色調選項，包括每種樣式運作最佳的時機，以及適合每種樣式的內容範例。

| 色調 | 最適合 | 內容範例 |
| ---- | ----- | ----- |
| 專業 | B2B通訊，正式公告 | 「我們很高興宣佈我們的策略夥伴關係……」 |
| 同理心 | 客戶支援，敏感主題 | 「我們瞭解此問題對您而言是多麼令人沮喪……」 |
| 幽默 | 參與行銷活動，輕鬆呈現內容 | 「警告：可能會大幅提升生產力！」 |
| 令人興奮 | 產品啟動、事件促銷 | 「這是您期待已久的時刻！」 |
| 勵志 | 動機行銷活動，品牌目的 | 「攜手共進，我們就能改變世界……」 |
| 有說服力 | 銷售行銷活動、轉換 | 「不要錯過這個限時機會……」 |
| 易記 | 客戶參與度，歡迎訊息 | 「很高興您能來到這裡！」 |
| 正式 | 法律通訊、官方通知 | 「此為下列變更的通知……」 |
| 歉意 | 服務復原、問題解決 | 「Bodea對於造成的不便深表歉意……」 |
| 主觀 | 領導力內容，權威訊息 | 「以下是您現在需要做的事……」 |
| storytelling | 品牌敘事、情感聯絡 | 「這都是從一個簡單的問題開始……」 |
| 對話 | 培養行銷活動，建立關係 | 「讓我們談談此計畫可如何協助您……」 |

## 最佳化的參考內容 {#reference-content}

>[!TIP]
>
>如果您已透過&#x200B;**[!UICONTROL 參考內容]**&#x200B;功能表上傳資產，則不需要在提示中參考該資產。 系統會自動使用任何選取的檔案。

參考內容檔案會提供真實資訊，以具體準確的詳細資料豐富您產生的內容。 當您上傳檔案（例如產品手冊或白皮書）時，會變更提示，加入焦點在哪些部分：

* **請避免使用** _「使用產品手冊」_ **您應該使用** _「著重於進階安全性功能與法規遵循認證，尤其是SOC 2法規遵循與資料加密」_

* **不要** _「參考個案研究」_ **您應該使用** _「強調醫療保健客戶的ROI結果，特別是地區醫療中心的40%成本降低」_

* **請避免使用** _「包含技術細節」_ **您應該使用** _「強調API整合功能與開發人員權益，著重於REST API端點和99.9%的運作時間SLA」_

### 內容細分

產生內容後，請使用&#x200B;**_[!UICONTROL Refine]_**&#x200B;功能，以下列選項來反複處理並增強內容：

* **[!UICONTROL 精心設計]** - AI助理可以協助您展開特定主題，提供其他詳細資訊，以增進瞭解及參與。

* **[!UICONTROL 摘要]** — 冗長的資訊可能會使頁面檢視器超載。 使用AI Assistant將要點濃縮為清晰、簡潔的摘要，以吸引注意並鼓勵他們進一步閱讀。

* **[!UICONTROL 重新寫字]** — 重新寫入郵件，同時保留其意義。 此選項可協助您產生替代用語、改善流量或調整詞句，而不變更核心訊息。

* **[!UICONTROL 使用較簡單的語言]** — 簡化語言，確保更廣大的受眾能夠清楚無誤地使用。

* **[!UICONTROL 翻譯]** — 將文字翻譯成其他語言。 （目前，英文是唯一受支援的語言。）

* **[!UICONTROL 變更音調]** — 調整訊息的音調以符合您的通訊風格，例如讓訊息更友善、專業、緊急或勵志。

* **[!UICONTROL 變更通訊策略]** — 根據您的目標修改訊息傳送方式，例如建立急迫性或強調令人興奮的吸引力。

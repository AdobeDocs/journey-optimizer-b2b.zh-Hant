---
title: AI 助手的問題指南
description: 預留位置
feature: AI Assistant
level: Beginner
exl-id: 65541246-7f4f-442f-8293-df036ea1c4ac
source-git-commit: f09f3f5b7d4419ead5308e4c5be3b518b4e16ff5
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 1%

---

# Journey Optimizer B2B edition中AI助理的問題指引

檢閱以下一組在Journey Optimizer B2B edition中查詢AI Assistant的範例問題。 此資訊也包含如何表述您的問題以從AI助理取得最佳回應的提示。

## 基於目標的問題

以下範例問題根據使用 AI 助手時可以完成的目標進行分組：

| 目標 | 說明 | 範例 |
| --- | --- | --- |
| 學習理念和繼續工作流程 | 身為新手使用者，您可以使用AI Assistant來瞭解Real-Time CDP和Adobe Journey Optimizer B2B edition概念，並且將自己帶入你不熟悉的產品和功能。 <br>身為經驗豐富的使用者，您可以使用AI Assistant解決可能阻礙工作流程的邊緣案例。 | <li>告訴我一些Real-Time CDP的使用案例。 <li>向我說明購買群組的概念。 |
| 疑難排解 | 使用AI助理瞭解如何偵錯工作流程中可能遇到的基本錯誤。 | <li>此錯誤&lt;ERROR_MESSAGE>代表什麼意思？ <li>我為何刪除不了名為「……」的對象？ |
| 沙箱衛生 | 使用AI助理來識別任何重複專案或未使用的物件，以便您能夠有效地維護您的沙箱。 | <li>您可以顯示類似的帳戶對象嗎？ <li>是否有任何架構沒有關聯的資料集？ |
| 值分析 | 使用 AI 助手辨識最常用的數據物件，並評估任何性能指標或查找最有價值的數據物件。 | <li>我們的「……」區段定義中有多少帳戶？ <li>對象何時啟用至Experience Cloud對象目的地？ |
| 搜尋 | 使用 AI 助手查找受支援的 Experience Platform 並Adobe Systems Journey Optimizer B2B Edition 物件，例如帳戶受眾、數據集、目標、架構、源、帳戶旅程、購買群組範本和解決方案興趣 | <li>列出名稱中包含「Luma」且在帳戶歷程中使用的物件。 <li>「Luma： Custom Actions」XDM 綱要中有哪些屬性？ |
| 影響分析 | 使用 AI 助手識別已在某些工作流程中使用的數據物件，以便您可以評估任何更改的影響。 | <li>在「B2B Person」結構描述中，哪些帳戶對象使用`workEmail.address`？ <li>`jobTitle`儲存在哪些資料集？ |

## 用詞說明問題

您必須用清楚的語境向AI Assistant提問，才能儘可能獲得準確的回應。 請參閱下列提示清單，以取得如何透過內容提出明確問題的指引：

* 以簡明的方式陳述您的任務和/或問題。
* 避免使用含糊不清的語言或過於複雜的語法，以方便理解。
* 提供有關您任務和/或問題的相關內容，因為內容可協助AI助理產生更相關的回應。

下表提供使用AI助理時您可以遵循的一些最佳實務：

| 執行 | 範例 |
| --- | --- |
| <li>請指定要擷取或分析的物件或資訊的特定資訊。 <li>嘗試將數據物件名稱放在引號中。 <li>如果您只知道物件名稱的一部分，您也可以在問題中指定。 | <li>哪些資料集使用「B2B帳戶」結構描述？ <li>顯示名稱中有「帳戶」的已啟動對象。 依成員人數將他們排名。 |
| <li>請避免模稜兩可，並使用清楚的語言。 <li>使用精確術語，確保查詢內容更清楚。 <li>在詢問有關Adobe Experience Platform和Adobe Journey Optimizer B2B edition的問題時，請嘗試使用Experience Platform或Adobe Journey Optimizer B2B edition的特定術語，以改善回應的相關性。 | <li>「我的帳戶對象」中有幾個成員？ <li>有多少帳戶歷程使用帳戶對象「我的帳戶對象」？ |
| <li>提供內容或指定條件以篩選結果。 <li>在問題中使用篩選條件來限制回應中的資料量。 | <li>顯示尚未啟用且建立日期超過6個月且從未修改過的帳戶對象。 <li>顯示過去7天內發佈的帳戶歷程，並使用超過1000個成員的帳戶對象 |

| 不要 | 範例 |
| --- | --- |
| 使用模糊或不明確的語言。 | <li>提供有關數據集的資訊。 <li>旅程 x 有什麼作用？ <li>「ACME 物件」中有多少使用者？ <li>顯示区段。 <li>清單屬性。 |
| 提出不完整的請求。 | <li>「Luma - 忠誠度數據集」 |
| 假設知識而不內容。 | <li>過去 6 個月內Audiences。 <li>為我建立一個查詢。 <li>建立我的旅程 |
| 制定過於複雜的查詢。 | <li>提供跨所有物件及其相依性之資料譜系的全面分析。 |
| 省略條件或引數。 | <li>顯示資料集。 |

## 不支援的問題範例

下列清單包含Journey Optimizer B2B edition中的AI助理目前不支援的問題範例：

* 哪些帳戶對象在條件中使用……欄位群組的workEmail.address欄位？ 
* 在發佈視覺效果中，使用超過10,000、5000-10,000、1000-5000及低於1000的帳戶對象來顯示作用中歷程的數量
* 誰進行了帳戶歷程x的最後一次更新？
* 有多少進行中歷程會針對解決方案興趣x新增購買群組成員？
* 針對解決方案興趣x新增購買群組成員？
* 購買群組範本最常見的決策者標題是什麼？
* 誰是購買 群組 x 範本的決策者？

## 後續步驟

如需在工作流程中如何使用AI助理員功能的相關資訊，請參閱[在Journey Optimizer B2B edition中使用AI助理員](./use-ai-assistant.md)。
